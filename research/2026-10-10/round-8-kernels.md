# 第八轮个人内核核验：BearOS 与 OS002

核验日期：2026-10-10。目录基线：`48e7a753e30e8059b0c617a1c38f5385c54e3b4f`。

## 结果

- 旧线索深化 2 项：BearOS／小熊操作系统、OS002。
- 新发现项目计数 0；正式内核目录新增建议 0。
- 两项均保留 pending：中国开发者或中国社区归属的明确公开自述继续待核实。
- BearOS 补齐官网与原作者频道互链、4 条原 BV、x86/32 位保护模式定位、V0.20 版本资料及功能分层。
- OS002 补齐原作者视频与公开仓库的直接关联、固定源码、GPLv3 根许可、UEFI 与自身内核边界。
- 关键版本事实：OS002 的 2026-04-03 提交新增 ExitBootServices，3 月原片与 4 月源码分阶段记录。
- BasC 为 BearOS 附属语言线索，本轮新增语言计数 0。中文语法原例待核实。
- 正式候选文件为 `round8-kernel-entry.json`（空数组），待核实文件为 `round8-kernel-pending.json`（2 项完整记录）。

## 起点与排重

已阅读 [AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/48e7a753e30e8059b0c617a1c38f5385c54e3b4f/AGENTS.md)、[7 项内核目录](https://github.com/yuyan-lang/chinese-programming-languages/blob/48e7a753e30e8059b0c617a1c38f5385c54e3b4f/data/kernels.json)、[第七轮日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/48e7a753e30e8059b0c617a1c38f5385c54e3b4f/research/2026-10-10/round-7-kernels.md)、[第七轮待核实数据](https://github.com/yuyan-lang/chinese-programming-languages/blob/48e7a753e30e8059b0c617a1c38f5385c54e3b4f/research/2026-10-10/round-7-kernel-pending.json)，以及 [Issue #23](https://github.com/yuyan-lang/chinese-programming-languages/issues/23)和[原有评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/23#issuecomment-6100431744)。

正式目录 7 项为 DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380、NeoAetherOS／na-kernel。BearOS 与 OS002 已在第七轮和 Issue #23 保存，本轮继续沿用既有 id。搜索出现 SCSLaboratory/BearOS 等同名项目；这些入口按独立作者和项目关系区分，未计入本轮发现。

## BearOS／小熊操作系统

### 作者与公开归属

[作者官网](https://www.medaifan.net/)自述姓名宁净、网名嘟嘟熊。[BearOS 项目页](https://www.medaifan.net/bearos.html)直接嵌入四条视频；视频上传者为胖嘟嘟的超级熊，原片简介指向官网；[作者频道](https://space.bilibili.com/111781531/)公告明确写明个人网站为 www.medaifan.net。这组互链建立了 MedAIFan、BearOS 与该 B站频道的直接关联。

已核对的官网、项目页、频道和原片简介中，明确中国开发者或中国社区归属自述继续待核实。记录仅保留公开技术身份与项目关系，归属判断继续等待直接证据。

### 版本与架构

官网首页仍展示 V0.10；项目详情页同时包含 V0.1 与 V0.2 开发历程，并提供 V0.10、V0.20 发布包入口。当前版本资料以项目详情页为依据：

- [V0.10 官网分发链接](https://pan.baidu.com/s/1Ca-J8UpR1VB8FIIz-8gx0Q?pwd=abcd)
- [V0.20 官网分发链接](https://pan.baidu.com/s/1d_e6mLHk6QuZvbVpeVjgcg?pwd=abcd)

发布包内容和精确发布日期待核实。官网使用“今年春节后”回顾开工时间，成文日期待核实。

[P4 原片简介](https://www.bilibili.com/video/BV1ttHC6bE9g/)明确自述 x86 架构、从零开发操作系统。官网记录早期 16 位实模式阶段，随后转为 32 位保护模式。项目文档列出 QEMU 软件模拟和 WHPX 加速的启动脚本。

### 作者声明层的功能

官网 V0.1/V0.2 开发历程给出以下实现说明：

- 自定义文件系统与磁盘程序加载
- C 类库、文本编辑器、Shell、中文显示和拼音输入
- 1024×768 图形模式，窗口重叠、拖动和关闭
- 内存动态分配/回收、时钟中断驱动的任务切换
- 应用进程、专属栈与内存、控制台结束进程
- 独立 Shell 与输入法进程
- DMA 磁盘访问、AC97 音频及 WAV 播放器
- 浮点数、立方体、字符雨和 BasC 应用

上述功能均按作者声明记录。内核源代码、源码固定快照、具体隔离机制、功能正确性及稳定性待核实。作者关于 DOS 与早期 Windows 的叙述按设计动机保存；实际代码继承关系、引导器和驱动来源待核实。BearOS 项目专属许可及第三方组件许可待核实。

### 原视频与观察范围

1. [P1 系统内核及文件管理](https://www.bilibili.com/video/BV13oj66LEnk/)：BV13oj66LEnk，2026-06-19，06:59。已观察 00:16 开场字幕和宿主桌面，该片段讲述开发动机。核心功能画面的时间点待核实。
2. [P2 文本编辑器与中文输入法](https://www.bilibili.com/video/BV1goj665EC6/)：BV1goj665EC6，2026-06-19，02:10。官网嵌入与频道/合集信息已交叉核对。
3. [P3 自制编程语言](https://www.bilibili.com/video/BV1goj665EXe/)：BV1goj665EXe，2026-06-19，04:34。原片页面与作者关联已核对。
4. [P4 图形界面、音乐播放与机器学习](https://www.bilibili.com/video/BV1ttHC6bE9g/)：BV1ttHC6bE9g，2026-10-07，19:49。原片简介给出 x86 自制系统定位。

P1 日期在页面初次加载和浏览器重绘后显示不同的时分秒，日历日期一致。当前以日期精度保存。播放器出现匿名试看提示；后续部分视频页面的 DOM/截图读取超时。可靠功能时间点、完整原片内容及与 V0.20 发布包对应关系继续待核实。

### BasC 附属线索

作者说明 BasC 是为 BearOS 创建的解释型语言，设计参考 BASIC，并加入 C 风格类型定义、Python 风格多返回值。官网列出 bc 解释器、hi.bc、sum.bc、string.bc、tet.bc、train.bc 等程序，以及字符串、数学和文件库。V0.2 资料描述窗口、多任务与浮点支持。

这些内容支持保存“作者自制语言”的附属线索。中文关键字、完整语法原例、解释器源码和许可仍待核实；本轮语言新增计数为 0。

## OS002

### 身份链、时间与版本

[原作者视频](https://www.bilibili.com/video/BV1sTwtzuEP8/)为 BV1sTwtzuEP8，日期 2026-03-14，时长 04:02，上传者 [Liu_Chunyi](https://space.bilibili.com/3546765877840766/)。简介直接链接 [Chunyi1031/OS002-UEFI](https://github.com/Chunyi1031/OS002-UEFI)。固定 README 署名 Liu Chunyi、日期 2026/3/14，视频与源码关联成立。

[仓库元数据](https://api.github.com/repos/Chunyi1031/OS002-UEFI)记录创建时间 2026-03-14T06:27:44Z。固定 main 提交为 [be37cce6b0963e35d4481ea22d7688b76e19e80c](https://github.com/Chunyi1031/OS002-UEFI/commit/be37cce6b0963e35d4481ea22d7688b76e19e80c)，时间 2026-04-03T11:36:44Z。核验时页面显示 0 个标签，[Releases 集合](https://api.github.com/repos/Chunyi1031/OS002-UEFI/releases)为空；正式版本待核实。

已核对作者公开主页、README 和视频简介；明确中国开发者或中国社区归属自述继续待核实。

### 自身内核与启动边界

固定源码前缀为：
`https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/`

- [Kernel/Makefile](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/Kernel/Makefile#L64-L65)：freestanding、-nostdlib、-m64 和 _start 入口。
- [Kernel/kernel/main.c](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/Kernel/kernel/main.c#L36-L81)：接收 BootShare，初始化物理内存、串口与多任务，进入命令循环。
- [Bootloader/main/main.c](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/Bootloader/main/main.c#L166-L194)：读取内核、组织启动参数、调用 ExitBootServices 后跳转内核。
- [4月3日提交差异](https://github.com/Chunyi1031/OS002-UEFI/commit/be37cce6b0963e35d4481ea22d7688b76e19e80c)新增 ExitBootServices 调用。当前快照与3月14日演示之间有明确版本变化。退出启动服务的实际返回状态、后续可运行性和原片对应提交继续待核实。

### 源码可见的实现

- [Task.c](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/Kernel/kernel/Task.c)：线程控制块、内核栈、上下文切换、就绪与睡眠队列、互斥锁和信号量。
- [IDT.c](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/Kernel/kernel/interrupt/IDT.c)：中断表、lidt 与 IRQ/PIC 初始化。
- [PIC.c](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/Kernel/kernel/interrupt/PIC.c)：8259 PIC 与 PIT；IRQ0 更新时钟计数并调度，IRQ1 读取键盘端口。
- [PMemory.c](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/Kernel/kernel/mm/PMemory.c)：根据 UEFI 内存映射建立位图、分配和释放连续页。
- [Bootloader/main/Tools.c](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/Bootloader/main/Tools.c#L47-L189)：文件读取属于 UEFI 引导阶段，使用 EFI_SIMPLE_FILE_SYSTEM_PROTOCOL。
- [完整源码树](https://api.github.com/repos/Chunyi1031/OS002-UEFI/git/trees/be37cce6b0963e35d4481ea22d7688b76e19e80c?recursive=1)包含显示、任务、ACPI、键盘、时间、中断和物理内存组件。内核文件系统、块设备、用户态及完整虚拟内存机制继续待核实。

[README](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/README.md)要求 x86_64、单核、256MB RAM 和 128MB 磁盘，列出 Linux/GNU GCC 与 QEMU 环境，并提示实体机运行可能异常。

### 上游与许可

[根 LICENSE](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/LICENSE)为 GPLv3。

[引导构建配置](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/Bootloader/Makefile#L54-L56)直接链接 GNU-EFI 的 crt0、libefi 与 libgnuefi；[随附 GNU-EFI 文档](https://github.com/Chunyi1031/OS002-UEFI/blob/be37cce6b0963e35d4481ea22d7688b76e19e80c/Bootloader/GNU-EFI/README.gnuefi.md#L71-L90)给出上游和版权说明。仓库还包含 OVMF.fd 与预编译对象/静态库。各二进制的精确上游版本与完整第三方许可清单继续待核实。

IDT、PIC 与 PMemory 源码注释列出学习视频；PIC.c 标注 [OSDev 8259 PIC](https://wiki.osdev.org/8259_PIC)为参考。具体代码继承范围继续待核实。平台 fork 字段、当前提交数与完整原创性分别判断。

### 演示与独立运行

原片页面、作者、日期、时长与仓库链接已经核对。匿名播放器显示试看提示，后续页面读取超时；可可靠引用的启动、多线程、中断功能时间点待核实。本轮独立构建与运行保持待核实。

## 方法、范围与限制

- 方法：普通公开网页检索、只读 GitHub 仓库/文件/提交元数据、dot 云公开浏览器。
- 关键词围绕 BearOS、MedAIFan、胖嘟嘟的超级熊、BasC、OS002、Liu_Chunyi 与已发现仓库；技术深查收束在两项旧候选。
- 时间范围：现存公开页面与固定仓库快照；区分作者回顾时间、仓库创建时间、视频日期、提交时间和发布包版本。
- GitHub 仓库搜索接口在该连接器返回不支持端点；普通网页检索继续用于同名排重。
- 普通网页抓取无法读取 BearOS 详情页及部分 B站原片，dot 云浏览器成功取得作者页面与原片元数据；部分播放器后续读取超时。
- 已完成的研究输出为本地资料文件。操作范围保持公开只读；运行代码、下载执行、桌面执行及外部写入属于后续授权范围。
- 证据层严格分列：作者声明、源码可见、作者演示、独立运行。公开源码和作者的“可运行”描述分别记录。
- 明确中国归属仍是两项正式收录缺口；源码上游、功能正确性与许可保持各自核验边界。

