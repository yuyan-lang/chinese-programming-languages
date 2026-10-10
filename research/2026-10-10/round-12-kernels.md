# 第十二轮内核新线索：CoreZ-OS

核验日期：2026-10-10，研究时间20:01—20:08 UTC。目录基线：9776f45bed00a6f1c9a594eb8142dd5b4428095d。

## 结果

- 深入新项目1项：CoreZ-OS。
- 正式新增0项，新增待核1项，旧待核补证0项。
- 原作者视频与源码的直接关联成立；固定自身内核、x86-64架构和引导入口可见。
- 中国开发者或中国社区的明确公开归属自述继续待核实，因此本项保留pending。
- 原片01:01截图可见终端和几何绘图测试窗口，按作者演示记录。

[结构化待核资料](round-12-kernel-pending.json)包含稳定id corez-os及29项来源。

## 基线与排重

已读基线[AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/9776f45bed00a6f1c9a594eb8142dd5b4428095d/AGENTS.md)、[data/kernels.json](https://github.com/yuyan-lang/chinese-programming-languages/blob/9776f45bed00a6f1c9a594eb8142dd5b4428095d/data/kernels.json)的现有项目身份、源码和来源字段，以及完整[第十一轮内核日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/9776f45bed00a6f1c9a594eb8142dd5b4428095d/research/2026-10-10/round-11-kernels.md)。现有8项DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380、NeoAetherOS及TextOS均排除。

已读开放内核议题正文与全部评论：[Issue13](https://github.com/yuyan-lang/chinese-programming-languages/issues/13)、[Issue18](https://github.com/yuyan-lang/chinese-programming-languages/issues/18)、[Issue23](https://github.com/yuyan-lang/chinese-programming-languages/issues/23)、[Issue29](https://github.com/yuyan-lang/chinese-programming-languages/issues/29)、[Issue32](https://github.com/yuyan-lang/chinese-programming-languages/issues/32)。评论数依次为2、2、2、2、1。KunOS、NeoRunST、QuantumNEC、racaOS、BearOS、OS002、Halo OS及两组VergeOS保持各自旧议题，本轮新项目核验集中于CoreZ-OS。

## 发现过程与作者关联

初步检索优先2024—2026年的B站自制、手写、手搓与AI操作系统。普通搜索中的[AIGC聚合页](https://post.smzdm.com/p/arzqxqpq/)提供CoreZ-OS与原BV的发现入口；该页面仅作导航资料。技术和作者结论来自原作者页面、固定仓库及视频画面。

原片为[BV1krYP6iEv5](https://www.bilibili.com/video/BV1krYP6iEv5/)，标题说明fish shell移植和简易WinGDI程序支持。上传者为Lightfl0w，UID3690980152707649。简介直接给出https://github.com/lightfl0w/CoreZ-OS，因此视频与源码关联成立。[作者投稿列表](https://space.bilibili.com/3690980152707649/upload/video)显示4条视频，其中本片时长01:08；同作者其他工程仅作身份与消歧背景，本轮技术深入范围为CoreZ-OS。右栏及作者投稿列表提供两条后续背景入口：[自制微内核自举视频BV166at6hEgN](https://www.bilibili.com/video/BV166at6hEgN/)、[自制编程语言视频BV1pghX6NEE8](https://www.bilibili.com/video/BV1pghX6NEE8/)。前者简介给出lightfl0w/lgc-os；二者作为后续轻量入口保存，代码关系和中文语言定位待核实。

中国归属核验覆盖[GitHub主页](https://github.com/lightfl0w)、该账号公开README、项目固定README、原片简介与标签、B站主页、投稿及[公开动态](https://space.bilibili.com/3690980152707649/dynamic)。当前明确公开归属自述待取得。原片公开可读评论中，有第三方表达对国产系统的期待；其内容采用第三方观点层级。中文文档、账号名称、时区和第三方期待各自按原有属性记录。

## 自身内核与架构证据

固定提交：[8016bb2e8cf39001a7d2a89ece8c2ecf8381522e](https://github.com/lightfl0w/CoreZ-OS/commit/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e)，main，提交时间2026-10-02T09:01:56Z。

1. [独立链接目标](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/linker/kernel.ld#L1-L9)明确elf64-x86-64、i386:x86-64和entry_start。
2. [汇编入口](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/arch/x86/asm/entry.asm#L1-L89)为bits 64；第87行调用kmain。
3. [内核初始化](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/kernel/init/main.c#L58-L157)执行内存、内核堆、GDT/TSS、IDT、系统调用、线程、驱动、文件系统、SMP与网络准备，第152行启动/bin/shell.elf。
4. [BIOS主引导](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/arch/x86/boot/boot.asm)具有0x7C00入口、活动分区选择、INT13磁盘读取和55AA标志；loader.asm提供后续FAT32、VBE、内存探测及长模式路径。
5. [UEFI入口](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/arch/x86/uefi/main.c#L680-L803)加载内核、建立页表和获取固件内存映射。第776行调用exit_boot_services；成功后生成Multiboot2参数，并在第800行进入landing路径。
6. [构建源码](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/build.py)第148行采用freestanding C选项，第1000—1003行独立链接kernel.elf。构建文本按静态资料阅读。

上述源码支持具有自身内核工程的定位。整体原创范围、上游继承与功能稳定性分别待核实。

## 功能与文档阶段

- [thread.c](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/kernel/sched/thread.c#L595-L692)维护每CPU就绪位图、队列权重、虚拟运行时间和deadline，并完成上下文切换。[timer/IPI路径](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/arch/x86/interrupt/interrupt.c#L244-L282)调用调度器。
- pool.c包含物理页池、四级页表、MMIO映射与COW处理；fsapi.c定义ext2、ext4的VFS操作表及根分区探测。
- PE加载器检查AMD64类型并处理导入；win32.c提供限定API映射，未解析导入使用占位处理。GDI代码设置4应用、4窗口、12设备上下文等资源上限。兼容范围以具体API和示例为边界。
- README列fish移植、键鼠、磁盘、网络和图形功能；各项作者声明与已读源码分别标注，设备兼容与运行覆盖继续待核实。

固定README仍记录AP启动阶段及多核调度路线项。2026-10-01的[7cdbd4f](https://github.com/lightfl0w/CoreZ-OS/commit/7cdbd4f226e602ac865ce951985db82041c2f9f3)提交说明基础AP调度；当前thread.c具有每CPU选取，smp.c的ap_main切入idle任务上下文。README、提交说明与较新源码采用阶段对照，完整多核运行验证待核实。

## 版本、历史和许可

[仓库元数据](https://api.github.com/repos/lightfl0w/CoreZ-OS)记录创建时间2026-08-30T04:51:40Z。[公开提交列表](https://api.github.com/repos/lightfl0w/CoreZ-OS/commits?per_page=100&page=1)提供fish、UEFI、PE/GDI、ext4和AP调度等阶段信息；Git历史中的作者提交日期与仓库对外公开日期分别处理。最早公开时间继续待核实。

核验时[Releases集合](https://api.github.com/repos/lightfl0w/CoreZ-OS/releases?per_page=100)返回空数组；正式版本与发行物对应待核实。main和dev各有独立分支指针，本轮静态记录固定在main的8016bb2e。

[根LICENSE](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/LICENSE)为GPLv3全文。[2026-09-13许可修改](https://github.com/lightfl0w/CoreZ-OS/commit/689bb08d0587e921fbb3d895d6a62cbbdc23345a)把署名CoreZ Team、采用GPLv3或更新版本的简短声明替换为许可证全文。此历史与当前根文件各自保留。

[.gitmodules](https://github.com/lightfl0w/CoreZ-OS/blob/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e/.gitmodules)及[完整固定Git树](https://api.github.com/repos/lightfl0w/CoreZ-OS/git/trees/8016bb2e8cf39001a7d2a89ece8c2ecf8381522e?recursive=1)记录6个gitlink：

- flanterm：3e311fe2ce4f663273c22d1a229745bc53afa930
- BusyBox：fc71374dfccd46448c62947269a35f1420d7ee28
- fish：35fd72ad034e8e75451debe29535240bbd689980
- libc-testsuite：4dbca0ae3eafb9e21f2cdb2305395e7976feacb4
- musl：c4e1bb3994c14ed5112c894d15a451bf00f0d501
- PCRE2：09eb19dc1102b34e7557408f33318364cb97d2b0

README对上述模块分别声明MIT、GPL-2.0-only或BSD-3-Clause许可。该部分采用作者文档与gitlink证据。完整第三方许可、资源字库、源码继承和分发范围继续待核实。

## 作者演示与时间记录

公开网页浏览器直接读取原片页面并观察播放器：

- 00:14：编辑器显示Win32相关示例代码。
- 00:26：QEMU窗口中可见TianoCore标志。
- 01:01：截图中可见终端和包含矩形、椭圆、斜线的测试窗口，图案与win_gui.c相符。原片二进制与固定提交的对应继续待核实。

01:01记录采用截图自身的播放器可见读数；同次AX文本已推进至01:02。两者异步读取的差异已记录。原视频链接和时间点作为公开证据入口。

原片日期显示存在差异：首次网页文本为2026-10-01 11:17:06；后续客户端为2026-09-30 20:17:06；投稿列表为9月30日。规范时间戳与时区解释待核实，结构化记录保存原值。评论区显示8条总数，公开可读两条顶级评论；登录后的其余评论继续待核实。

## 检索范围与限制

普通网页检索采用“自制操作系统 2025 github”“AI 操作系统 开源 2026”“手搓 内核 2024”“自制操作系统 国产”“手搓操作系统 bilibili”“CoreZ-OS”“CoreZ WinGDI”“lightfl0w China／中国”“3690980152707649”等词。主检索目标期为2024—2026；搜索未统一强加日期过滤，以保留作者主页和较早沿革。

GitHub仓库搜索使用“操作系统 自制”和“操作系统 自制 created:>=2024-01-01”。XinhaoOS、VimtuOS只查看仓库元数据作为发现筛选；后续深入收束CoreZ-OS。LunaixOS与PlantOS识别为前轮发现路径，保持已有记录。

普通网页工具读取B站原片失败，转公开网页浏览器成功。B站直接搜索CoreZ-OS／CoreZ返回大量低相关结果，随后从聚合页面公开引用取得原BV。GitHub tags列表端点被工具URL范围拒绝，Git refs/tags返回404；正式版本保持待核实。资料读取只用普通网页、GitHub文本与元数据、公开网页浏览器公开页面。

遗漏风险包括：搜索索引不足、评论登录限制、跨页面日期差异、原视频与固定源码对应缺口、README阶段滞后、作者中国归属自述缺口、完整上游与许可覆盖。证据分为作者声明、源码可见、作者演示及独立运行四层，独立运行继续待核实。
