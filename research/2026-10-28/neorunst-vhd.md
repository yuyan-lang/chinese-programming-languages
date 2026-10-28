# NeoRunST v0.13.0 官方VHD：独立内核阶段静态核验

核验日期2026-10-28；基线`ac01037f4a328e3849fa565a557b27181798f9ea`（114语言、23内核）。分支`contrib/neorunst-vhd-20261028`。本次为#13尚余NeoRunST子项的明确新发行物路径；原23个内核对象及HTML原样保留。

## 原件、哈希及只读方法

采用已保存的[官方v0.13.0发布元数据](https://api.github.com/repos/CN-RTStudio/NeoRunST-DEV-KIT/releases)所给[直接资产URL](https://github.com/CN-RTStudio/NeoRunST-DEV-KIT/releases/download/v0.13.0/disk.vhd)，先请求HTTP Range末尾512字节。服务器返回206、`Content-Range: bytes 423731712-423732223/423732224`。VHD footer为`conectix`、动态类型3、逻辑容量1GiB。

本轮随后下载完整423,732,224字节，SHA256为`c41552de8ab94fab53563220d768f23ffce233a57d9cb141d9baf0b1b8489e15`，与官方asset digest完全相同。[正式发布](https://github.com/CN-RTStudio/NeoRunST-DEV-KIT/releases/tag/v0.13.0)时间2026-10-24T11:54:12Z，发布者RETUSTU。发布标签、VHD文件哈希、文件系统目录时间分别记录，目录时间采用FAT原字段，时区和实际构建时间待核。

解析工具为本机已有qemu-img info、7zz、LLVM及自写Python字节读取。镜像和分区仅作为普通文件读取。候选代码/工具/脚本执行、安装、构建、启动、虚拟机运行及宿主磁盘挂载次数均为0。qemu-img仅用于文件格式元数据。

## 分区、文件与引导链

动态VHD块大小2MiB、逻辑容量1,073,741,824字节，内含GPT：EFI分区329,219,072字节，Basic data分区743,440,384字节。EFI分区可用7zz枚举为FAT32；数据分区的FAT32 BPB可读，7zz直接读取失败。本次以BPB、FAT链和目录项显式读取文件，保留原始字节，未修复镜像。独立审阅又从原VHD的BAT/GPT/FAT链直接读取两项核心文件，并与缓存逐字节核对一致。

EFI分区`boot/grub/grub.cfg`原文：

```text
menuentry "NeoRunst" {
    search --no-floppy --file --set=root /runst/system/runstload.efi
    chainloader /runst/system/runstload.efi
}
```

数据分区核心原件：

| 文件 | 大小 | SHA256 |
| --- | ---: | --- |
| RUNST/SYSTEM/runstload.efi | 66,102字节 | 35c23188fd322815cc97fcff9da2a1f3ce0f8dd4f69a69bdd934cd48c6d13eaf |
| RUNST/SYSTEM/RUNSTKNL.NEP | 1,217,032字节 | b64968c30e552487e73fd3e180f4e9880be6e64c02890de790cbcd0b5752c30e |

runstload.efi为PE32+ x86-64 EFI应用，保留GNU-EFI库函数/协议符号及`efi_main`。RUNSTKNL.NEP实际为未剥离ELF64、x86-64、ET_EXEC，入口`0x02000000`，含3个PT_LOAD、12个节；高半区代码段从`0xffff800002007000`映射。

加载器RVA0x3dba从EFI System Table的BootServices字段取表，RVA0x3dbe间接调用表内0xe8偏移；按EFI ABI识别为ExitBootServices，随后检查返回值并在失败分支重新读取内存映射。成功分支RVA0x42ea设置RDI参数，RVA0x42ef取已解析入口，RVA0x42f4调用该入口。这里记录静态路径，实际固件返回与成功运行待核。

## 自身内核实现的机器码依据

证据同时使用未剥离符号定位和具体指令、调用目标核对：

- `_start`在0x02000048写CR3，随后在0x0200006d加载`kmain`高半区地址并跳转。
- `kmain`（0xffff800002008f0f）包含GDTInit、IDTInit、IRQ_INIT、init_timer、ReadEFIMemoryMap、RequestPage、MapMemory、switchPML4、init_heap、fs_init、task_init、nep_init及主循环nep_sched的调用。GNU large-model间接call以紧邻movabs常量和符号地址相互核对。
- `IDTInit`在0xffff8000020111b2执行lidt。内核另含GDT/TSS、中断处理、PIC/PIT实现。
- `timer_handler`在0xffff800002012146调用`nep_preempt_check`；该路径保存任务上下文并调用抢占返回汇编。`nep_preempt_asm`从g_kernel_cr3恢复CR3、恢复内核RSP；`nep_resume_asm`从g_nep_task_cr3装入CR3、恢复寄存器并执行iretq。相关代码在`.data`中，采用LLVM `-D`显式核对。
- fs_init调用块设备/分区初始化；FAT32目录与文件读写、VFS、AHCI、NVMe、e1000等有符号和机器码。此次据此记录实现路径，具体设备覆盖、数据一致性、权限及网络安全正确性继续待核。
- 编译单元名包含kernel.c、nep.c、syscall.c、idt.c、gdt.c、timer.c、vfs.c、fat32.c等，`.comment`保存GCC 15.2.0标记。当前发行物按C与汇编内核阶段记录，公开完整源码入口继续待核。

这条官方发行物链提供独立的引导器、内核ELF与内核侧资源管理/调度实现，满足按v0.13.0有限内核阶段收录的技术依据。SDK文档的Ring 3/隔离声明与本轮页表切换、iretq机器码分别记录；完整地址空间隔离和恶意程序边界继续待核。

## 公开关联、继承与许可边界

此前已取得的[工作室官网](https://rtstu.com/)同时直链[CN-RTStudio](https://github.com/CN-RTStudio)与原作者B站UID3546925078940468，本轮沿同一组织的官方Release取得原件。公开作者/中文开发社区关联成立；个人国籍待核。

2026-07-06的[TheseusOS历史原片](https://www.bilibili.com/video/BV1APTR6yEzo/)继续作为独立阶段保存。本轮能够确认v0.13.0自己的C/汇编内核文件与资源管理路径。TheseusOS到当前阶段的逐文件继承和完整来源仍待核；编译语言、字符串或当前目录均不足以排除派生。

[固定SDK](https://github.com/CN-RTStudio/NeoRunST-DEV-KIT/blob/477078db66e35cb23b9eed20e7228b605f29ea83/readme.md)说明开发包采用MIT许可；该范围与VHD内核、GRUB、GNU-EFI及字体等组件的许可分别保存。内核源码入口和许可证、组件精确上游版本继续待核；本次收录不声明全部代码原创或整体MIT。

完整大小、哈希、ELF程序头与数据目录见[neorunst-vhd-static.json](neorunst-vhd-static.json)；有界指令摘录见[neorunst-static-excerpts.txt](neorunst-static-excerpts.txt)。原始镜像、两分区及完整反汇编保留于`/tmp/kernels-b-20261028/`，仓库只保存研究和短摘录。

## 议题结论及评论草稿

新增data/kernels.json对象`neorunst`与`内核/neorunst.html`，保留各项后续核验字段。#13的KunOS已由#79收录；NeoRunST的公开身份链、当前自身内核及已知引导资源分工已补齐，独立来源审阅通过并合并后可关闭#13。完整历史和独立运行不作为无限门槛。

> NeoRunST已取得官方v0.13.0发行物的独立内核证据：disk.vhd为423,732,224字节，SHA256与Release完全一致。GRUB链式加载runstload.efi，后者交接到独立ELF64 RUNSTKNL.NEP；入口→高半区kmain、GDT/IDT、页表/堆、FAT32/VFS及NEP调度均有静态调用与机器码依据，用户任务恢复/抢占路径可见CR3切换和iretq。条目按当前C/汇编内核阶段收录，TheseusOS历史逐文件继承、内核/组件许可和独立运行继续按后续待核字段保存。候选执行、启动和挂载均为0。KunOS此前已收录；本次独立审阅通过并合并后完成剩余NeoRunST子项，可关闭本议题。

本组未推送、创建PR、发表评论或关闭议题；后续外部操作由root汇总。Safari/TX待定UI动作保持停止，本次使用新的明确官方发行物HTTP路径。
