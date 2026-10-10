# 第十轮内核研究：VergeOS 两条发布身份与源码边界

核验日期：2026-10-10。目录基线：320b1f6904747bd8afcbb0c1d3655d965ed53ed3。

## 结果与计数

- 本轮深入 2 组：VergeOS（TX 工作室／FendosPE）与 VergeOS Open（NewEra Studio／新启年工作室）。
- 新发现并整理 2 组，正式新增 0 项，新待核实 2 组，旧候选补证 0 项。
- 第九轮曾把 BV1UaHp6KEYx 留作初筛背景，并明确其尚未计入深入、正式与 pending 数量。本轮首次深入该身份链。
- VergeOS Open 来源于该原片的公开推荐入口，本轮首次取得其发布账号、仓库与固定源码。
- 两条发布身份分别记录，合作、同源、派生和改名关系继续待核实。计数按发布身份组，项目合并依据待核实。
- 明确中国开发者／中国社区公开自述是两组的共同待核事项。正式内核目录保持 8 项。
- 编剧笨笨 AI Rust 系统保持 Issue #29 的既有资料；本轮初始背景检索后，深入范围收束到上述两组。
- 正式条目数据为空数组；本轮成果进入研究与待核材料。HTML 详情和内核首页中文 URL 列表的新增条件为正式收录，因此本轮保持现有目录。

## 起点与排重

已读取基线 [AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/320b1f6904747bd8afcbb0c1d3655d965ed53ed3/AGENTS.md)、[data/kernels.json](https://github.com/yuyan-lang/chinese-programming-languages/blob/320b1f6904747bd8afcbb0c1d3655d965ed53ed3/data/kernels.json)、[第九轮内核日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/320b1f6904747bd8afcbb0c1d3655d965ed53ed3/research/2026-10-10/round-9-kernels.md)。

正式 8 项为 DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380、NeoAetherOS、TextOS。

开放内核 [Issue #13](https://github.com/yuyan-lang/chinese-programming-languages/issues/13)、[#18](https://github.com/yuyan-lang/chinese-programming-languages/issues/18)、[#23](https://github.com/yuyan-lang/chinese-programming-languages/issues/23)、[#29](https://github.com/yuyan-lang/chinese-programming-languages/issues/29)正文及当时全部评论已读取，评论数量分别为 2、2、2、1，共 7 条。

旧 pending 为 KunOS、NeoRunST、QuantumNEC、racaOS、BearOS、OS002 以及编剧笨笨 AI Rust 系统；NeoAetherOS 已正式收录并保留沿革跟进议题。两条 VergeOS 发布身份与这些资料分别保存。

## 检索平台、词组与范围

研究使用普通公开网页检索、GitHub 只读连接器与 公开网页浏览器。浏览器读取 B站原片、作者频道、两个工作室官网及官网直达的公开 ISO 分享页。

普通网页词组包括：

- “VergeOS” “BV1UaHp6KEYx”
- “VergeOS” 自制 操作系统 github
- “VergeOS” “Fendos”
- “VergeOS” “新启年”
- “VergeOS” “TX工作室”
- “VergeOS” “新启年工作室” 中国
- “max257026-svg” “China”
- “FendosPE” “VergeOS” 源码
- site:newera2625.top 中国
- site:txgzsgw.mysxl.cn 中国
- “新启年工作室” “国产”
- “FendosPE” “国产”

GitHub 仓库检索使用 VergeOS -user:verge-io、“VergeOS” “Fend”、“VergeOS” “TX”、“FendOSPE”。后三组返回空列表。初始背景检索还包含“编剧笨笨” “Rust” 操作系统 github 与“编剧笨笨” “操作系统”，之后按本轮两组上限收束。

搜索结果包含 Verge.io 企业虚拟化产品及其集成工具。企业同名项目、B站两条发布身份和名称带 VoidOS 的源码工程分别辨识。名称、汉字、B站发布或账号昵称均仅作为检索线索，中国归属依明确公开自述判定。搜索结果属于可见样本，空结果反映本次检索范围。

## 1. VergeOS：TX 工作室／FendosPE

### 原片、作者与分发身份

[原片 BV1UaHp6KEYx](https://www.bilibili.com/video/BV1UaHp6KEYx/) 的标题为“全网首个支持双启动自研操作系统VergeOS”，发布账号为 FendosPE系统官方，UID 3493125223877029。页面显示日期时间 2026-10-05 12:42:06，频道标示时长 03:00。

简介直接给出 txgzsgw.mysxl.cn。[TX工作室官网](https://txgzsgw.mysxl.cn/#vergeos)公开列出“VergeOS自研操作系统Beta版”，并提供下载入口。关于页署名 TX工作室，另列 FendOSPE 和软件工具。

官网直达的[公开分享页](https://1817497108.share.123pan.cn/123pan/nvdTjv-DG3ih?pwd=1234#)显示文件名 VergeOS.iso、分享时间 2026-10-05 11:58:03。该记录的层级是分发页元数据；镜像内容、构建时间、哈希、源码对应及运行结果待核实。页面时间的时区继续待核实。

### 内核与中国归属

原片标题的“双启动”“自研”属于作者声明。双启动所指 BIOS、UEFI 或其他具体路径，以及内核、固件、现成组件和图形界面的职责边界待核实。调度、内存、文件系统、驱动、实现语言、架构、原始源码、上游和许可均继续待核实。

原片、频道与官网已读材料中的明确中国开发者或中国社区归属自述继续待核实。账号开展 PE 系统相关活动仅用于区分项目入口；其与 VergeOS 的具体代码关系继续按项目资料核对。

### 视频证据

作者发布页与官网关联已取得。原片后续 DOMSnapshot.captureSnapshot 和截图 Page.getLayoutMetrics 连续超时，本轮在这一点收束。可靠功能画面、时间点与对应版本继续待核实。宣传标题中的“全网首个”继续采用原始标题记录，项目描述使用中性名称。

## 2. VergeOS Open：NewEra Studio／新启年工作室

### 原片与作者链

[原片 BV1fPTj6FEcb](https://www.bilibili.com/video/BV1fPTj6FEcb/)于页面显示的 2026-07-02 18:33:07 发布，账号新启年工作室-NES，UID 3546976190728987。[频道](https://space.bilibili.com/3546976190728987/)将其列作代表作，标示 00:36。简介直接链接 [max257026-svg/VergeOS-Open-VoidOS-](https://github.com/max257026-svg/VergeOS-Open-VoidOS-)，并说明 x86、C、汇编及 MIT。

固定 README 署名 NewEra Studio，根 LICENSE 署名 2026 NewEra Studio（新启年工作室）。公开 [GitHub账号](https://github.com/max257026-svg)显示技术昵称 SYSTEM-WinDF-114514 并列出该仓库。频道公告直接关联 [工作室官网](https://www.newera2625.top/)。

官网[时间轴](https://www.newera2625.top/#timeline)记载 2026-06-27 启动 VergeOS 开发计划、2026-07-02 发布 VergeOS Open。官网成立日期为 2026-02-05。项目最早公开日期仍按待核实保存，开发计划、仓库创建、提交和原片发布日期分别记录。

明确中国开发者或中国社区公开自述继续待核实。核验范围覆盖作者频道、原片、GitHub主页、README以及官网团队、产品与时间轴。

### 固定版本与自身内核

固定提交：[d6041c2f2c2a95d73b22a7df8142a0d7d345f319](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/commit/d6041c2f2c2a95d73b22a7df8142a0d7d345f319)，时间 2026-07-02T07:36:55Z，parents 为空。仓库 created_at 为 2026-07-02T07:36:37Z。提交标题称 VergeOS Open v0.2，源码 banner 使用 VoidOS v0.2。核验时 main 指向该提交，GitHub Releases 集合返回空数组。

[boot.asm](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/boot/boot.asm)含 BITS 32、Multiboot 头、16KiB 栈和 kernel_main 调用。[build.sh](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/build.sh)以 i686-elf、C11、freestanding、nostdlib 与 NASM ELF32 编译，链接 voidos.bin。

[kernel_main](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/kernel/kernel.c)初始化 GDT、IDT、异常、PIC/IRQ、PIT、物理页、分页、堆、TSS、系统调用和任务，再处理 Multiboot 模块、framebuffer、键鼠、桌面与 Shell。这些源码支持自身内核工程的定位。全体代码的原创范围和上游继承另列待核实。

### 功能边界

- 调度：[task.c](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/kernel/task.c)含32任务槽、4KiB栈、就绪链表和主动 task_yield，通过ESP切换进入下一任务；[PIT](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/drivers/pit.c)回调累加计数器。抢占、退出任务回收和上下文切换正确性继续待核实。
- 内存：[物理页管理](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/kernel/mem.c)以位图管理4KiB页，跟踪上限32MiB；[分页](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/kernel/paging.c)建立0—32MiB恒等映射并设置CR3、CR0。
- 内核堆：[kmalloc.c](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/kernel/kmalloc.c)采用first-fit、块分裂与空闲块合并；[配置](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/kernel/kmalloc.h)为1MiB初始、16MiB上限。
- 文件系统：[initrd.c](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/kernel/initrd.c)解析ustar内存盘，最多64项，提供查找、读取和列举。持久化磁盘文件系统与块设备路径待核实。
- 驱动：PS/2键盘、鼠标分别注册IRQ1、IRQ12；[图形驱动](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/drivers/vbe.c)接收Multiboot帧缓冲并提供BGA寄存器、PCI BAR0查询、1024×768×32bpp路径。
- 应用加载：[ELF32](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/kernel/elf.c)核对EM_386和PT_LOAD，页面以supervisor参数映射；[PE32](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/kernel/pe.c)解析i386文件及有限Win32桩。Shell把加载入口交给task_create与task_yield。完整用户态隔离、Windows应用兼容范围与实际程序运行待核实。

官网当前产品页将 VergeOS 标作开发中，声明 Legacy BIOS、CLI与基础网络，并提到文件系统和驱动持续开发。当前官网阶段与该固定源码的逐项对应继续待核实。

### 上游与许可

根 [LICENSE](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/LICENSE)为 MIT。固定[工具配置](https://github.com/max257026-svg/VergeOS-Open-VoidOS-/blob/d6041c2f2c2a95d73b22a7df8142a0d7d345f319/scripts/setup_tools.bat)引用 lordmilko/i686-elf-tools 13.2.0、NASM 2.16.03、QEMU及可选GRUB。脚本内容采用只读方式核对。

完整源码树返回85个文件及目录条目、truncated=false。原始代码来源、参考教程及第三方代码继承范围、工具和分发包的完整许可继续待核实。仓库的MIT、作者“从零”声明和独立代码来源核验分层保存。

### 与 TX 的关系

两条原片分别由不同公开账号发布，分别关联 TX官网与NewEra源码。TX官网也列有QV软件链接；NewEra官网时间轴记述QV相关活动。这些产品文字提供后续关系检索线索，项目代码继承与共同作者结论仍待原始资料确认。同名和邻近推荐关系保留为检索背景。

## 证据等级与访问边界

1. 作者声明：原片标题、简介、频道、官网、README和版本文字。
2. 源码可见：固定提交内的启动、内存、任务、FS、驱动和加载器；静态结构与可定位调用。
3. 作者演示：已取得原片发布页；可靠功能画面时间点继续待核实。
4. 独立运行：待核实。

本轮使用只读公开访问和本地研究产物编写。核验范围包含网页、GitHub文件与元数据；构建、安装、运行候选程序、镜像内容、私有资料及桌面任务保持本轮范围之外。外部发布由后续整合步骤处理。

普通网页工具对两条B站原片及TX官网返回不可访问；公开网页浏览器成功读取初始页面和作者资料。原片的后续DOM和截图超时后已收束。新启年官网产品“查看详情”触发“模态框未找到”提示，关闭提示后继续核对可见产品摘要与时间轴。GitHub用户元数据URL在连接器被标为不支持的公开端点，随后通过公开主页核对可见档案字段。

## 结构化产物

- round10-kernel-entry.json：正式新增数组，0项。
- round-10-kernel-pending.json：2组完整待核条目，逐项source_ids与sources对应。
- 本日志：检索范围、计数、证据分层及访问风险。


