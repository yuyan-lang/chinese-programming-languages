# 第十三轮旧背景首次深入：lgc-os 与配套 lgc

核验日期：2026-10-10；研究时间20:31—20:38 UTC。百科基线：65e45d07d80a36412625665931ce4a4402641480。

## 结论与计数

- 旧背景首次深入1项内核：lgc-os。
- 真正新发现0项；内核正式新增0项；新增结构化待核记录1项。
- 配套语言核验1项：lgc，归类为英文语法的自制编译语言／配套编译工具；中文语言正式新增0项。
- 两条原片、作者账号、两个源码仓库的关联已经成立。
- 中国开发者或中国社区的明确公开归属自述继续待核实，lgc-os保留待核状态。
- CoreZ-OS保持Issue38的已有记录。本轮围绕lgc-os及其配套lgc深入。

详细来源保存于[待核记录](round-13-kernel-pending.json)和[配套语言研究](round-13-lgc-language-research.json)。

## 基线与排重

已读基线[AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/65e45d07d80a36412625665931ce4a4402641480/AGENTS.md)、[data/kernels.json](https://github.com/yuyan-lang/chinese-programming-languages/blob/65e45d07d80a36412625665931ce4a4402641480/data/kernels.json)、[data/languages.json](https://github.com/yuyan-lang/chinese-programming-languages/blob/65e45d07d80a36412625665931ce4a4402641480/data/languages.json)、[第十二轮内核日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/65e45d07d80a36412625665931ce4a4402641480/research/2026-10-10/round-12-kernels.md)，以及[Issue38正文和全部1条评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/38)。

现有8项内核为DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380、NeoAetherOS／na-kernel、TextOS。76项语言中，名称、别名及来源字段均未匹配lgc或lightfl0w。lgc-os及语言原片已经作为第十二轮背景入口保存，本轮按旧背景首次深入计数；名字“lgc os”为原片简介的写法。

## 两片与源码的关系

1. [BV166at6hEgN](https://www.bilibili.com/video/BV166at6hEgN/)标题为“[自制微内核] 自制的微内核实现了自举”，作者Lightfl0w，UID3690980152707649，简介给出lightfl0w/lgc-os。
2. [BV1pghX6NEE8](https://www.bilibili.com/video/BV1pghX6NEE8/)标题为“[自制编程语言] 一个可以写微内核的编程语言？”，同一作者与UID，简介同时给出lightfl0w/lgc和lightfl0w/lgc-os。
3. [OS固定README](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/README.md#L1-L25)明确写明使用lgc编译器，并直接链接语言仓库。

因此，lgc是语言／编译器工程，lgc-os是使用该语言的内核实例。两个工程各自有仓库和版本历史；本轮名称分别记录。与CoreZ-OS的具体源码继承、改名或共享实现关系继续待核实。

## 自身内核及架构

OS固定快照为[ba606a063fd557bf28ad13a4c16f9e214b0deddd](https://github.com/lightfl0w/lgc-os/commit/ba606a063fd557bf28ad13a4c16f9e214b0deddd)，main，提交时间2026-09-27T09:55:16Z。

- [kernel/os.lg](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/os.lg)使用@boot入口，初始化VGA、键盘、内存、GDT、IDT、分页、系统调用、PIC/PIT和进程表，再载入RAMFS并进入shell。
- [core.lg](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/core.lg#L65-L158)实现GDT/TSS、PML4/PDPT/PD/PT基础页表、IDT门、PIC及PIT端口操作；[系统调用段](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/core.lg#L451-L522)设置x86-64 MSR并保存64位寄存器，包含sysret机器码。
- [build.py](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/build.py)把kernel/os.lg编译为lgc-os.img，附加用户程序和源码后交给qemu-system-x86_64。

源码支持自身内核工程与x86-64目标。整体原创范围与独立运行结果各自待核。

“微内核”来自原片标题与作者README。源码中ATA、RAMFS、shell直接通过@import进入@boot内核，README标注ring0 shell；严格微内核所涉及的用户态系统服务、IPC、隔离边界继续待核实，公开记录保持作者定位层级。

## 功能、边界及文档阶段

### 源码可见

- [调度](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/core.lg#L160-L449)：8个任务槽，FREE/READY/RUN/ZOMBIE状态；pick_next按顺序轮转寻找READY任务；IRQ0进入sched_irq；切换每任务CR3、内核栈和寄存器帧。
- [内存](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/mm.lg)：4KiB页帧递增分配、每地址空间页表建立、[缺页中断处理](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/core.lg#L1142-L1150)读取保存的缺页错误码与地址并调用as_map_user。页面权限位和控制寄存器设置可见；完整W^X保证和隔离效果待独立验证。
- [RAMFS](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/fs.lg)：32槽，每个新文件预留1MiB；[ATA PIO](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/ata.lg)读写扇区并flush。
- [VGA与键盘](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/vga.lg)：0xB8000文本缓冲、0x60/0x64键盘轮询、COM1串口。
- [ELF64加载](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/elf.lg)：读取入口和program headers，对PT_LOAD段复制并清零BSS；[shell](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/shell.lg#L200-L291)提供save、exec、bg、ps。
- [系统调用分发](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/kernel/core.lg#L1058-L1104)：实现一组Linux x86-64编号，mprotect／munmap等编号返回0，未知编号返回-38；具体兼容范围逐项核验。

### 作者声明与阶段对照

README将静态glibc程序、自举编译器运行、自举往返等列为完成项。固定完整Git树可见BusyBox、hello_c、spin_c及lgc.elf二进制；它们的来源构建和运行覆盖待核实。

README仍使用16MB内存布局，并保留调度策略待办。较新build.py把RAMFS预载地址设为0x4000000，core.lg已实现IRQ0抢占和轮转任务选择，mm.lg建立独立地址空间。上述阶段采用各自来源分别记录。

## 自举的具体含义

[tools/selfhost_test.sh](https://github.com/lightfl0w/lgc-os/blob/ba606a063fd557bf28ad13a4c16f9e214b0deddd/tools/selfhost_test.sh)给出以下流程：

1. 在lgc-os客体内运行预置lgc.elf，编译os.lg为os.bin。
2. 客体shell将os.bin写入磁盘指定扇区。
3. 宿主脚本从磁盘提取新镜像并复制原来的预载文件区，核查55AA引导标志。
4. 宿主再次启动QEMU，尝试运行hello_c及a.lg编译测试。

这是内核重新编译与引导的自举往返设计。其源码可读与作者演示分别记录。编译器自身源码lgc.lg的自编译、二进制一致性和完整流程的本轮独立复现结果待核实。

## 语言、版本与许可

配套lgc固定为[0f92930ead271723e615623d5e85d488903ea3fa](https://github.com/lightfl0w/lgc/commit/0f92930ead271723e615623d5e85d488903ea3fa)，提交时间2026-10-05T11:19:41Z。

- [C版完整词法表](https://github.com/lightfl0w/lgc/blob/0f92930ead271723e615623d5e85d488903ea3fa/src/main.c#L68-L95)含22个英文关键词，如let、func、if、while、return、for、struct、enum。
- [自举版词法表](https://github.com/lightfl0w/lgc/blob/0f92930ead271723e615623d5e85d488903ea3fa/src/lgc.lg#L1850-L1881)同样使用英文关键词；两个实现各自的关键词覆盖分别保存。
- [fac.lg连续完整原例](https://github.com/lightfl0w/lgc/blob/0f92930ead271723e615623d5e85d488903ea3fa/tests/fac.lg#L1-L8)及[@boot完整原例](https://github.com/lightfl0w/lgc/blob/0f92930ead271723e615623d5e85d488903ea3fa/examples/hello.lg#L1-L20)逐字核对后保存在语言研究JSON。

lgc归为英文语法的自制编译语言／配套工具，中文语言formal文件为空。

OS构建从外部LGC_SRC路径取得lgc.lg，再生成usr/lgc.elf；固定OS树仅保存该编译器二进制，blob为08baf7259a8b0cf4d7718978b2fec13ae8843ad1。精确编译器源码版本绑定继续待核实。

lgc [LICENSE](https://github.com/lightfl0w/lgc/blob/0f92930ead271723e615623d5e85d488903ea3fa/LICENSE#L1-L8)明确声明GPL-3.0-or-later，加入日期为2026-10-05。lgc-os固定完整树共有28项，许可文件待取得，仓库API license为null。OS源码、编译器及预置第三方二进制的许可范围分别核实。

OS仓库创建时间为2026-09-25T13:23:09Z；当前Git历史最早作者提交时间为2026-09-20T13:28:25Z。二者各按元数据意义记录。核验时OS与语言的Release及标签集合均为空，版本采用固定提交标识。

## 原片观察与日期

公开网页浏览器直接打开两个原片：

- 微内核原片00:18／00:45：截图自身的播放器时间可见；画面有QEMU窗口、lgc-os命令提示符与启动字幕。
- 微内核原片约00:34／00:45：同次AX读数为00:34；随后截图有selfhost_test.sh、终端save输出和镜像提取流程，截图控制条隐藏。该相邻观察保留异步时间边界。
- 语言原片约00:12／00:43：AX读数00:12；截图有C版编译器代码和终端、语言特性测试字幕。语法细节按固定源码记录。

两片的规范日期各有同日两组时刻显示：微内核初始网页为2026-09-27 15:00:06，客户端为2026-09-27 00:00:06；语言片初始网页为2026-09-26 15:12:35，客户端为2026-09-26 00:12:35。作者主页投稿列表分别显示9月27日与9月26日。按日日期可保存；规范时间戳及其时区解释待核实。

最终二次启动及视频二进制的固定提交对应待核实。上述全部属于作者演示，本轮独立运行结果待核实。

## 归属核验与有限收束

核对范围包括两个视频简介／公开标签、B站公开主页、GitHub主页、固定个人README与两个项目README。个人README只自述“我是lightfl0w”，B站简介为QWQ。中国作者／中国社区的明确公开归属证据继续待核。

普通搜索采用“lightfl0w lgc”“BV166at6hEgN”“BV1pghX6NEE8”“Lightfl0w 中国”“lgc-os 中国”“3690980152707649”。“筑梦社区”检索结果中有同handle帖子；账号身份与项目组织关系待核实，未据此确定国别。中文文本、账号名称和时区按其各自属性记录。

普通网页工具对B站原页与公开元数据URL均返回不可访问；转公开网页浏览器读取原页和播放画面成功。后续视频尾部观察出现DOMSnapshot／布局读取超时，保留已取得的00:18与约00:34证据。独立构建运行保持待验证。

遗漏风险集中在公开归属、严格微内核分类、规范时刻、原片与源码版本对应、README阶段滞后、OS和预置二进制许可、自举完整输出及独立运行。检索于本轮限定时间内收束，保持最多一内核和一配套语言。
