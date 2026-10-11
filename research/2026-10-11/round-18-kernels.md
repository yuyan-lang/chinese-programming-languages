# 第十八轮内核有限批次：MimicryOS 与 Causenix OS

核验日期：2026-10-11。研究基线随 PR #51 合并更新为 65be26668334bf92009e87cc275b729c81e7342d，语言91项、内核9项。

## 结果

- 本批深入2项来源线索：MimicryOS（Annihilation006）、Causenix OS（FRCREEPER）。两项均保存为待核候选；正式内核新增0项，目录保持9项。
- 原始公开来源35项：MimicryOS 22项，Causenix OS 13项。固定文件静态阅读分别16项及7项，共23项。
- 中国作者／中国社区的明确原始归属声明是两项共同缺口。中文README、用户名、QQ群入口各按公开原信息记录。
- 已读根AGENTS.md、当前内核目录、第16轮总记录和内核专项记录。初查开放列表含25个Issue及1个PR（#51）；逐项读取标题，读取全部8个内核议题正文及11条评论。#51随后合并，合并后的开放状态另行复核。
- 第17轮关于计划关闭 #35 的计数以实际状态校正：#35保留开放，原有6项待核要求继续跟进；第18轮不重复计为关闭。

## 去重与来源选择

正式目录的 DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380、NeoAetherOS、TextOS、HOS 保持现有对象。hudos、HanOS、lgc-os、CoreZ、VergeOS、Halo、QuantumNEC、racaOS、BearOS、OS002、KunOS、NeoRunST沿用已有议题身份。VimtuOS、MikuOS属于前轮筛选背景，本批读取VimtuOS README作范围选择，深入候选只计本批两项。

搜索覆盖B站2024—2026“自制操作系统”“开源”“国产”及作者／项目精确词。B站结果以已有项目、教学与转载为主。一条标注AI生成的第三方聚合页给出MimicryOS、Causenix名称，仅用于发现。技术和归属判断全部回到作者仓库、固定源码、公开主页和GitHub元数据。两项原作者B站账号、原片与可引用画面继续待补。

### MimicryOS

[原仓](https://github.com/Annihilation006/MimicryOS)创建于2026-08-27T10:33:05Z，当前固定提交[b2ed7ca8392c91c0386aeee055e242ee0c433b2d](https://github.com/Annihilation006/MimicryOS/commit/b2ed7ca8392c91c0386aeee055e242ee0c433b2d)，提交时间2026-10-02T14:28:18Z。完整树23文件，truncated=false；保留历史6提交，Releases为空集合。根提交自带时间早于建库时间约33分钟，作为Git提交时间保存。

[README](https://github.com/Annihilation006/MimicryOS/blob/b2ed7ca8392c91c0386aeee055e242ee0c433b2d/README.md)自述AI辅助开发、逐渐转向人工开发，公开文件为旧阶段；声明64位、FAT12、模块、Shell，明确致谢CoolPot部分文件及XIAOYI80386。[根MIT许可](https://github.com/Annihilation006/MimicryOS/blob/b2ed7ca8392c91c0386aeee055e242ee0c433b2d/LICENSE)署名2025 annihilation006。许可年份和date命令的2025常量分别记录，首发时间待核。

[Makefile](https://github.com/Annihilation006/MimicryOS/blob/b2ed7ca8392c91c0386aeee055e242ee0c433b2d/Makefile)使用gcc -m64、-ffreestanding和ld -m elf_x86_64，生成独立kernel.elf。[链接脚本](https://github.com/Annihilation006/MimicryOS/blob/b2ed7ca8392c91c0386aeee055e242ee0c433b2d/linker.ld)定义高地址PT_LOAD与_start，保留BOOTBOOT上游MIT署名；bootboot.h同属该上游。内核入口执行cli、设栈后进入kernel_main，读取BOOTBOOT帧缓冲并进入Shell。该路径支持自身内核入口工程的定位；完整上游继承与启动行为仍按阶段核验。

[kernel.c](https://github.com/Annihilation006/MimicryOS/blob/b2ed7ca8392c91c0386aeee055e242ee0c433b2d/kernel.c)可见固定1MiB堆、链表分割分配、ATA PIO、PS/2键盘轮询、Shell命令及标为FAT12的固定扇区访问。文件系统路径使用LBA2880、2885、2890，目录项与文件内容写入具体扇区；通用簇链、分区布局和完整一致性待核。filesystem.mod.c另为内存链表文件层。图形窗口、鼠标模块与stb_image PNG调用分别有静态源文件。

当前Makefile列font.o为链接输入，固定树对应字体与生成步骤待补。task/IDT头文件保存32位字段；tasks.mod.c采用另一组module成员名，当前构建对象与启动路径的调度接入待核。对这些阶段差异保留静态观察；独立构建、启动、调度和功能通过记录继续待核。后续授权运行应限定可恢复测试盘，因为format和文件命令含磁盘写路径。

### Causenix OS

[原仓](https://github.com/FRCREEPER/causenix)创建于2026-10-06T06:15:52Z，固定提交[f7ab3f38bac9b944b184e9226a6e8da5d65dde2e](https://github.com/FRCREEPER/causenix/commit/f7ab3f38bac9b944b184e9226a6e8da5d65dde2e)，提交时间2026-10-06T15:46:44Z。完整树11项，含9文件和2目录，truncated=false；17个保留提交均为10月6日，Releases为空集合。

[README](https://github.com/FRCREEPER/causenix/blob/f7ab3f38bac9b944b184e9226a6e8da5d65dde2e/README.md)自述x86-64自制系统、Limine、LIFS/FAT32、桌面与e1000网络栈；这些整体能力保持作者声明级。[index.html](https://github.com/FRCREEPER/causenix/blob/f7ab3f38bac9b944b184e9226a6e8da5d65dde2e/index.html)已进入apt风格软件源阶段，manifest列snake、conway两项0.1.0应用及大小/哈希。当前完整树只含这两项ELF和4个网络/接口源文件；README下载中心阶段所列内核及应用产物、完整构建和内核入口继续补证。

[netcmd.c](https://github.com/FRCREEPER/causenix/blob/f7ab3f38bac9b944b184e9226a6e8da5d65dde2e/src/netcmd.c)实现64槽、256字节命令的环形队列与白名单分派。白名单包含mkdir、rm、mount等命令；安全权限和网络输入验证待核。netcmd.h顶部注释指向shell_run消费者，drain注释另称timer上下文，实际调用方源码待补。当前片段的读取支持命令队列实现；e1000、UDP解析、调度、内存、文件系统、自身内核边界与UEFI/Linux依赖继续等待完整源链。

GitHub license字段为空，完整树许可证及应用源码授权待补。二进制只核对树/清单元数据；文件内容、哈希实算和执行分别待核。

## 归属、演示与证据边界

两名维护账号的公开GitHub主页成功按普通网页读取，简介和所在地均为空；FRCREEPER同名个人README仓库为空。精确项目/账号搜索尚未取得明确中国归属的作者自述。项目的中文描述、中文讨论入口与中国归属要求分字段记录。两项继续保留待核候选。

本批仅公开网页及GitHub只读资料，使用本地文件保存研究材料。项目安装、构建、运行、镜像启动及第三方联系均属后续范围。作者声明、源码可见、发行元数据、作者功能演示和独立复现逐层记录；本批原片画面与独立运行证据待补。

全部35项原始URL及字段见[待核资料](round-18-kernels-pending.json)。两项候选由[Issue #52](https://github.com/yuyan-lang/chinese-programming-languages/issues/52)跟进，正式内核计数保持9。
