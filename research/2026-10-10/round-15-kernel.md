# 第十五轮内核研究：HanOS（jjwang）

核验日期：2026-10-10。研究时段：21:30—21:38 UTC。百科基线：[757ddd0d875cb114b7261e389aa9a8a002f86c80](https://github.com/yuyan-lang/chinese-programming-languages/tree/757ddd0d875cb114b7261e389aa9a8a002f86c80)。

## 结果与计数

- 真正新候选1项：HanOS（jjwang）。
- 正式新增0项；旧线索补证0项；既有正式条目修改0项。
- 自身内核、作者关系及原始发布资料已取得；中国作者或中国社区的明确公开归属继续待核实。
- 正式数组为空；待核数组保存1个项目、45项原始来源。正式内核目录保持9项。
- 独立构建、启动、硬件和功能运行结果：待核实。


## 基线与排重

读取固定根AGENTS.md、data/kernels.json、第十四轮总日志和内核日志；取得24项开放Issues及63条评论，按项目名、作者账号、原仓和别名核对。9项正式内核为DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380、NeoAetherOS／na-kernel、TextOS与HOS（HuangCheng72）。

检索前轮保存的Markdown／JSON中的HanOS与jjwang/HanOS，和当前正式目录、全部开放议题及评论进行对照，计为本轮真正新候选。2021年属于项目历史；本轮发现年份属于百科调查记录。

PlantOS、LunaixOS、XinhaoOS、VimtuOS及CoreZ-OS、lgc-os、Halo、VergeOS、QuantumNEC、racaOS、BearOS、OS002、KunOS、NeoRunST沿用既有背景或议题身份。本轮深入范围收束为HanOS一个项目。

## 作者与归属

[GitHub主页](https://github.com/jjwang)显示JW／jjwang并自填Beijing, China。[根LICENSE](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/LICENSE)署名JW, HanOS developer。OSDev账号junjie在[2021公告](https://forum.osdev.org/viewtopic.php?p=337922)和[2026开发帖](https://forum.osdev.org/viewtopic.php?p=354923&sid=535017e25b52f0a529c280ec212dcb07)直接关联同一原仓。

所在地资料按所在地保存；中国人身份、来自中国或中国社区发起／维护的直接公开声明继续待补。中文文档和账号拼写分别保留语言与名称的证据含义。

[中文Wiki讨论](https://forum.osdev.org/viewtopic.php?sid=61e6c66d37d5a36397f44efb721c0a25&t=56187)中的native Chinese speaker原话属于zhang3，junjie在回复中引用该段并称赞网站。引文说话人已逐项核对，HanOS作者归属保持待核。

同账号HanOS-rs仅取得简短README；C项目、Rust项目以及2007—2008年周海汉相关同名HanOS的关系分别待核。名字相同仅用于消歧。

## 自身内核边界

固定mainline：[089ce1cd9e9684fb79c91c8036e62476978fe150](https://github.com/jjwang/HanOS/commit/089ce1cd9e9684fb79c91c8036e62476978fe150)；提交时间2026-10-10T13:55:52Z。完整树284项，246文件，truncated=false。

[内核构建](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/GNUmakefile)使用x86_64-elf-gcc、GNU11、freestanding、nostdlib与NASM，独立链接hanos.elf。[链接脚本](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/linker.ld)指定elf64-x86-64、i386:x86-64、ENTRY(kmain)及高地址布局。

[kmain](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/kmain.c)接收Limine帧缓冲、内存图、RSDP与initrd信息，自行初始化GDT／IDT、物理／虚拟内存、APIC、SMP和调度，再启动用户态服务。[设计文档](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/attic/hanos-microkernel-design-zh.md)称为混合微内核；[VFS服务适配](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/srv/vfs_srv.c)经sched_execve装载用户进程，并授予initrd和endpoint。[调度装载链](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/proc/sched.c#L834-L873)建立PROC_USER_MODE进程并载入ELF。

[musl文档](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/musl/README.md)记述对齐Linux x86-64调用编号与HanOS专用调用。当前可见源码支持自身内核与兼容接口的分层。Linux接口覆盖范围继续按实际实现核实。

## 来源与上游关系

2021年作者公开回应记述ToaruOS启发及早期文件调整。当前历史根提交保存简短README。具体继承文件、固定版本与许可保留范围继续待核实。公开对话与当前源码分别记录。

[根构建](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/GNUmakefile)取Limine v8.x-binary；内核规则取trunk的limine.h；UEFI配置使用OVMF nightly入口。[musl](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/musl/README.md)指定1.2.5，[libvterm](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/libvterm/README.md)指定0.3.3，两者源码按文档另行准备。[光标文档](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/attic/2026/2026-09-23-hardware-cursor-zh.md)标注DMZ-White left_ptr；原作者帖描述光标来自Ubuntu。外部组件、字体、光标的固定版本和完整许可清单继续核实。

## 固定源码功能

- [调度](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/proc/sched.c)：每CPU队列、默认1ms时间片配置、睡眠唤醒、就绪选择及地址空间切换。[APIC定时器](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/arch/x64/timer.c)提供周期设置。实际精度与并发正确性待核。
- 内存：伙伴分配、PML4映射与共享页对象；[memobj](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/mm/memobj.c)按用户权限映射对象。
- IPC：[endpoint队列](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/ipc/ipc.c)、等待键、句柄转移与路由；[对象实现](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/ipc/object.c)检查句柄代数及请求权限。隔离安全性继续待核。
- [块服务](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/block.c)：AHCI／DMA及GPT分区，处理读写。
- [FAT32](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/fat32.c)：读取接口与长名称片段；非ASCII名称字符转换为问号。
- [ext2](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/ext2.c#L1215-L1384)：已含创建、写入、截断及删除分支。大文件写入范围、错误恢复与文件系统一致性待核。
- [输入](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/input.c)、[console](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/console.c)及[net](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/net.c)有独立用户态文件。网络包含e1000e、ARP／IPv4／ICMP／UDP／TCP、DHCP与DNS路径；TCP发送和乱序缓存各4项。
- [系统调用](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/proc/syscall.c)包含文件、网络、fork／exec及信号入口，k_clone具有CLONE_VM共享地址空间线程创建路径。

### 文档阶段与源码差异

1. 设计文档及ext2文件头保留只读描述；固定文件后部已含EXT2_CREATE／WRITE／TRUNC／UNLINK。
2. musl说明保留CLONE_VM限制；当前k_clone接受该标志。完整pthread及信号运行结果待核。
3. 设计文档保留单个服务崩溃停止描述；[svc_monitor](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/srv/svc_monitor.c)已有重启回调。[引入提交](https://github.com/jjwang/HanOS/commit/636185208110f9a0b01f4531d433a60e9410c018)说明endpoint重建及打开文件、管道、缓存状态的边界。
4. FAT32设计说明列8.3名称；当前dir_scan已解析长名称片段并保留ASCII范围。
5. [block_server_probe](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/srv/block_srv.c)在启动探测中向LBA40写HANOS-BLOCK并读回。后续运行需界定可恢复试验磁盘。

## 作者测试、演示与AI

[2026-09-22固定文档](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/attic/2026/2026-09-22-skylake-edp-modeset-zh.md)记述HD520的1366×768面板与QEMU测试；[次日文档](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/attic/2026/2026-09-23-hardware-cursor-zh.md)记述PS/2、USB HID指针和硬件光标测试。[9月30日作者帖子](https://forum.osdev.org/viewtopic.php?p=354923&sid=535017e25b52f0a529c280ec212dcb07)称已在实机接通Intel HD520显示管线，并明确AI工具辅助源码及寄存器调试。具体模型、工具、文件比例及人工复核范围继续待核。

证据按四层保存：
- 作者声明：设计、阶段测试、硬件结果与AI辅助
- 源码可见：固定内核、服务及构建逻辑
- 原始演示：帖子图片入口已定位，像素内容、视频时间点及构建版本待核
- 独立运行：构建、启动、硬件与功能复核待核

## 历史、版本、许可及活动

仓库创建2021-10-15T12:42:18Z；保留根提交2021-10-15T12:42:19Z。原作者公告显示2021-10-15 4:45 am，时区与最早公开时刻待核。基础VERSION为0.1.2，version.sh追加构建当天YYMMDD，两个层级分别记录。

Releases与Git标签引用集合核验时均为空。根MIT署名Copyright (c) 2022 JW, HanOS developer。当前mainline在2026-10-10提交；pushed_at为同日15:29:22Z。53 stars为读取时平台值。

main.yml工作流生成代码量徽章。构建可复现性及运行测试证据按专门层级继续核实。依赖分支、nightly入口和外部组件版本需要后续锁定。

## 检索与访问范围

发现窗口以2024—2026为主，候选历史追至2021。平台包括普通网页、Bilibili索引、GitHub及OSDev原作者论坛。

查询组：
- site:bilibili.com/video 自制 操作系统 内核 2026 github，排除已重点调查项目
- GitHub：操作系统 自制 created:2024-01-01..2026-10-10（首50项）
- GitHub：国产 内核 stars:<100；中国 自制 操作系统；kernel Chinese stars:<100 language:C
- babyos2；onix os；dionysus kernel；HanOS
- HanOS jjwang 作者 中国；HanOS 操作系统 作者；HanOS bilibili
- HanOS 中国人；HanOS 国产；HanOS China developer；jjwang HanOS 作者
- site:forum.osdev.org junjie China；site:forum.osdev.org junjie Chinese
- HanOS junjie from；HanOS junjie Chinese；jjwang 中国 开源 laibot

筛选读取lyajpunov/os、zhummq/eehf-os、JanSky520/MikuOS、Samael-Z/SmallOS、Titroupast/fufuos、Kiritouse/OhMyOS等短README及公开作者入口。FufuOS明确用于《30天自制操作系统》学习记录；SmallOS当前提交作者与仓库拥有者不同，继承关系待核。筛选命中用于范围选择，深入候选计数仅含HanOS。

GitHub原始文件与仓库元数据成功取得。部分作者主页和OSDev原帖直接open返回Cache miss；OSDev搜索索引提供原帖正文，按这一访问层级保存。商业聚合页仅用于发现路由；技术结论使用原仓与原作者资料。GitHub的languages、contributors通用端点返回URL范围错误，语言依据改由固定源码与构建配置核对。

## 静态审阅与后续

研究稿采用肯定式事实和待核字段。JSON语法、唯一ID、引用闭合及固定SHA链接接受静态审阅；项目源码保持只读，独立构建及执行另列待核。

后续优先取得明确中国作者／社区归属；核对ToaruOS历史及组件许可；取得原作者图像／视频与对应版本；对齐ext2、线程、FAT长名称和服务恢复的文档阶段。未来运行须先明确LBA40写探测的试验盘范围。

## 原始来源索引

- hn1：[作者GitHub公开主页](https://github.com/jjwang)（作者自述）
- hn2：[固定中文README](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/README.zh-cn.md)（固定作者文档）
- hn3：[HanOS仓库元数据](https://api.github.com/repos/jjwang/HanOS)（平台元数据）
- hn4：[核验时mainline提交](https://github.com/jjwang/HanOS/commit/089ce1cd9e9684fb79c91c8036e62476978fe150)（固定提交元数据）
- hn5：[当前历史的根提交](https://github.com/jjwang/HanOS/commit/87ebbba9f4f5e8248853c4e288d3e07bbe4edd06)（固定提交元数据）
- hn6：[作者2021年OSDev项目发布帖](https://forum.osdev.org/viewtopic.php?p=337922)（原作者论坛帖（搜索索引正文））
- hn7：[根MIT许可证](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/LICENSE)（固定源码或作者文档）
- hn8：[内核构建](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/GNUmakefile)（固定源码或作者文档）
- hn9：[内核ELF链接脚本](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/linker.ld)（固定源码或作者文档）
- hn10：[内核入口与服务启动](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/kmain.c)（固定源码或作者文档）
- hn11：[每核调度实现](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/proc/sched.c)（固定源码或作者文档）
- hn12：[用户与内核进程建立](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/proc/process.c)（固定源码或作者文档）
- hn13：[IPC实现](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/ipc/ipc.c)（固定源码或作者文档）
- hn14：[对象与句柄实现](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/ipc/object.c)（固定源码或作者文档）
- hn15：[虚拟内存实现](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/mm/vmm.c)（固定源码或作者文档）
- hn16：[伙伴分配器](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/mm/buddy.c)（固定源码或作者文档）
- hn17：[共享内存对象](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/mm/memobj.c)（固定源码或作者文档）
- hn18：[内核VFS服务启动适配](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/srv/vfs_srv.c)（固定源码或作者文档）
- hn19：[块服务启动与探测](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/srv/block_srv.c)（固定源码或作者文档）
- hn20：[用户态块驱动](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/block.c)（固定源码或作者文档）
- hn21：[用户态FAT32实现](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/fat32.c)（固定源码或作者文档）
- hn22：[用户态ext2实现](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/ext2.c)（固定源码或作者文档）
- hn23：[用户态网络服务](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/net.c)（固定源码或作者文档）
- hn24：[用户态输入服务](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/input.c)（固定源码或作者文档）
- hn25：[用户态console实现](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/servers/console.c)（固定源码或作者文档）
- hn26：[系统调用实现](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/proc/syscall.c)（固定源码或作者文档）
- hn27：[混合微内核设计说明](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/attic/hanos-microkernel-design-zh.md)（固定源码或作者文档）
- hn28：[musl移植说明](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/musl/README.md)（固定源码或作者文档）
- hn29：[libvterm移植说明](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/libvterm/README.md)（固定源码或作者文档）
- hn30：[用户态构建](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/userspace/GNUmakefile)（固定源码或作者文档）
- hn31：[镜像及外部组件构建配置](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/GNUmakefile)（固定源码或作者文档）
- hn32：[源码版本](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/VERSION)（固定源码或作者文档）
- hn33：[版本字符串脚本](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/scripts/version.sh)（固定源码或作者文档）
- hn34：[公开Releases集合](https://api.github.com/repos/jjwang/HanOS/releases?per_page=100)（平台元数据）
- hn35：[Git标签引用集合](https://api.github.com/repos/jjwang/HanOS/git/matching-refs/tags/)（平台元数据）
- hn36：[完整固定源码树](https://api.github.com/repos/jjwang/HanOS/git/trees/089ce1cd9e9684fb79c91c8036e62476978fe150?recursive=1)（源码树元数据）
- hn37：[作者HD520实机与AI辅助开发帖](https://forum.osdev.org/viewtopic.php?p=354923&sid=535017e25b52f0a529c280ec212dcb07)（原作者论坛帖（搜索索引正文））
- hn38：[Skylake eDP阶段文档](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/attic/2026/2026-09-22-skylake-edp-modeset-zh.md)（固定源码或作者文档）
- hn39：[硬件光标阶段文档](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/attic/2026/2026-09-23-hardware-cursor-zh.md)（固定源码或作者文档）
- hn40：[服务重启监控](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/srv/svc_monitor.c)（固定源码或作者文档）
- hn41：[中文Wiki讨论中的引文署名](https://forum.osdev.org/viewtopic.php?sid=61e6c66d37d5a36397f44efb721c0a25&t=56187)（原始论坛对话（搜索索引正文））
- hn42：[Skylake显示驱动源码](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/device/display/skl_display.c)（固定源码或作者文档）
- hn43：[默认内核配置](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/kernel/kconfig.h)（固定源码或作者文档）
- hn44：[代码量徽章工作流](https://github.com/jjwang/HanOS/blob/089ce1cd9e9684fb79c91c8036e62476978fe150/.github/workflows/main.yml)（固定源码或作者文档）
- hn45：[服务重启引入提交](https://github.com/jjwang/HanOS/commit/636185208110f9a0b01f4531d433a60e9410c018)（固定提交说明）

