# 第五轮内核核验：OpenXJ380 与 NeoAetherOS

核验日期：2026-10-10；研究时段：16:31–16:39 UTC。研究结果为 1 项可新增条目、1 项新待核实线索。现有 DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel 五项完成去重。

开工前读取了根目录 AGENTS.md、data/kernels.json、research/2026-10-10/round-4-kernels.md、[Issue #13](https://github.com/yuyan-lang/chinese-programming-languages/issues/13) 及现存两条评论。公开文本使用直接事实陈述，证据缺口标为待核实。

## 1. OpenXJ380：可新增条目

### 原始来源与公开归属

- [XINGJI Studios 组织主页](https://github.com/xingji-studio) 明确自述来自中国，所在地字段为中国，并链接工作室官网和 Bilibili 频道。条目使用工作室名称和公开中国归属。
- [官方开源介绍](https://www.xingjisoft.com/open-source/) 将 OpenXJ380 定义为 XJ380 的开源版本，链接 [原始仓库](https://github.com/xingji-studio/OpenXJ380)。
- [贡献者名单](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/CONTRIBUTOR.md) 保存共同维护记录。
- [作者原视频](https://www.bilibili.com/video/BV1ku376JE2h/) 简介直链该仓库。视频页面 DOM 的发布时间为 2026-07-26T05:48:44.000Z；简介说明视频已换源。当前片源的替换日期待核实。

### 固定版本与时间

核验快照为 [d585f42d79b4c2990d1eb57d981a488f97103cef](https://github.com/xingji-studio/OpenXJ380/commit/d585f42d79b4c2990d1eb57d981a488f97103cef)，提交时间 2026-10-04T15:29:06Z。

[仓库元数据](https://api.github.com/repos/xingji-studio/OpenXJ380) 的 created_at 为 2026-08-01T05:17:35Z。[现存根提交](https://github.com/xingji-studio/OpenXJ380/commit/b9d7ac1a03270b41335a90348a8130a5a95db29a) 为 2026-08-01T05:17:36Z，parents 为空，内容为 LICENSE。[源码导入提交](https://github.com/xingji-studio/OpenXJ380/commit/4224bec3ab0bbffb41ecb5af27127314c240f63a) 时间为 2026-08-01T12:24:58Z。

[Releases 集合](https://api.github.com/repos/xingji-studio/OpenXJ380/releases?per_page=100) 本轮返回空数组。当前[构建版本头文件](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/kernel/build_settings.h) 默认字符串为 XSK 2.1.0、BetaVersion。仓库创建、提交日期、视频稿件发布日期及正式版本分别记录。最早公开日期待核实。

搜索同时召回该作者的 [2022-12-02 XJ380 历史视频](https://www.bilibili.com/video/BV1Kg411H7mn/)；该记录作为早期同名项目的沿革线索。本次技术结论使用 2026 年 OpenXJ380 固定快照。

### 技术事实与短源码依据

- 架构与语言：[构建生成器](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/tools/gen_ninja.py#L581-L588) 分别定义 C11、GNU++17、汇编参数，含 -m64、-ffreestanding、-nostdlib。UEFI 引导源码为 C，内核主要路径为 C++。
- 启动：[bootx64.c](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/boot/bootx64.c#L1013-L1034) 读取 kernel.krl，按 ELF 头计算装载范围；[1234–1252 行](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/boot/bootx64.c#L1234-L1252) 调用 ExitBootServices 并交接入口。
- 内核入口：[KernelMain](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/kernel/main.cpp#L513-L552) 初始化 CPU、中断、HPET、APIC、页帧、堆、VFS 和 PCI；[683–694 行](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/kernel/main.cpp#L683-L694) 创建 shell 用户进程并启动调度。
- 调度：[scheduler.cpp](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/kernel/task/scheduler.cpp#L302-L426) 包含 EEVDF 风格的虚拟时间、截止时间、资格检查与下一任务选择；源码同时维护每 CPU 抢占深度。实际调度正确性与性能待运行核验。
- 内存：[buddy.cpp](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/kernel/memory/buddy.cpp#L157-L219) 包含按阶空闲块查找、分裂与伙伴合并，文件定义 DMA、DMA32、Normal 区域。
- 文件系统：[VFS](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/driver/fs/vfs/vfs.cpp) 包含节点、引用、文件系统、路径别名和加锁操作；KernelMain 包含 FatFs、tmpfs、pipefs、procfs、socketfs 接入。
- 驱动：[AHCI](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/driver/ahci/ahci.cpp#L443-L475) 使用 PCI 类码 0x010601 查找控制器，映射 BAR5，并访问控制器寄存器。
- [架构说明](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/docs/ARCHITECTURE.md) 定义 UEFI、内核核心、内建驱动、VFS、用户态 ELF 与可加载模块的分层，并记述 Linux 兼容系统调用与 XAPI。

上述代码事实的证据等级为“源码可见”；作者定位和设计目标使用“作者声明”。

### 自身实现、共享代码与上游

[THIRD_PARTY_NOTICES](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/THIRD_PARTY_NOTICES.md) 列出 FatFs、lwIP、musl ELF 定义、Rust 运行库、talc、BusyBox、libutf、Linux UAPI 等，并标注 MikanOS 字体及帧缓冲头文件来源。

VFS 文件头保存 min0911Y、zhouzhihao、copi143 署名。具体上游提交和完整许可沿革待核实。[LICENSES.md](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/LICENSES.md) 另规定外部二进制分发所需的精确版本、许可与对应源码材料。根项目许可证为 Apache-2.0。技术条目按具体实现和各组件来源保存。

### 原片与版本边界

原视频 01:10 暂停帧显示 QEMU 窗口、中文控制中心、系统信息、设备规格和右下运行日志，产品栏可读 XJ380 操作系统。该观察等级为“作者演示”。视频内核版本前三字母在可读画面中较小，继续待核实。归档截图文件待补。

[2026-08-04 提交](https://github.com/xingji-studio/OpenXJ380/commit/26d454c6739bc5230d3ae3013849bad2e4e2a68c)，时间 2026-08-04T02:45:10Z，记录移除 GUI 相关代码。[当前 README](https://github.com/xingji-studio/OpenXJ380/blob/d585f42d79b4c2990d1eb57d981a488f97103cef/README.md) 保留同一阶段说明。稿件7月发布日期、当前片源的GUI画面、8月源码调整和10月固定快照分别记录；GUI画面的拍摄及换源日期待核实。视频与当前源码的一一对应、独立构建、虚拟机及实机运行保持待核实。

结构化条目沿用 data/kernels.json 的顶层结构及 text/evidence_level/source_ids 证据结构。

## 2. NeoAetherOS：新待核实线索

建议议题标题：内核资料待核实：NeoAetherOS 的公开归属、原片与源码沿革

可直接使用的议题内容：

- [naos 系统仓库](https://github.com/aether-os-studio/naos) README 将其说明为 NeoAetherOS 用户态与系统构建工程，并直链 [na-kernel 内核仓库](https://github.com/aether-os-studio/na-kernel)。
- 内核核验快照：[2c45649144afa3dd2e32147d7029e354dc9fc518](https://github.com/aether-os-studio/na-kernel/commit/2c45649144afa3dd2e32147d7029e354dc9fc518)，提交时间 2026-08-24T05:49:13Z。GitHub 将该提交关联到 lihanrui2913。
- [仓库元数据](https://api.github.com/repos/aether-os-studio/na-kernel) 的 created_at 为 2025-04-26T06:33:04Z，许可证字段为 GPL-3.0。[现存 Releases 集合](https://api.github.com/repos/aether-os-studio/na-kernel/releases?per_page=100) 本轮返回空数组。
- [固定 README](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/README.md) 定义 freestanding 内核与可加载模块边界，文档记述 Rust 内核模块。
- [构建文件](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/kernel/GNUmakefile) 列出 x86_64、aarch64、riscv64、loongarch64 目标与 Limine、SBI、laboot、Linux boot protocol 条件；各目标运行状态待核实。
- [kmain](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/kernel/src/init/main.c#L78-L139) 包含页帧、页表、设备、VFS、initramfs 与任务初始化；[init_thread](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/kernel/src/init/thread.c#L36-L87) 调用 task_execve 加载 /init。
- [调度源码](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/kernel/src/task/sched.c) 含 nice 权重、调度队列及 sched_pick_eevdf_locked；[伙伴分配器](https://github.com/aether-os-studio/na-kernel/blob/2c45649144afa3dd2e32147d7029e354dc9fc518/kernel/src/mm/buddy.c) 含按阶页块和每 CPU 页缓存结构。
- [2025-10-12 README 快照](https://github.com/aether-os-studio/na-kernel/blob/6b18ceb2b95590ac2d5385dd142416dbd1d63ebf/README.md) 将项目定位为 Linux 兼容操作系统，并声明 SMP、ACPI、网络及 Weston 等软件支持。相应运行能力属于作者声明。
- Bilibili 搜索索引召回“一个能跑 JVM 的自制操作系统 - NeoAetherOS”（2025-09-26，VOID2913）和桌面环境视频（2025-07-18，XIAOYI80386）。本轮原视频直链、作者与仓库的直接互链、视频帧和时间点继续待核实。
- [组织主页](https://github.com/aether-os-studio) 与 [提交作者主页](https://github.com/lihanrui2913) 本轮可读资料中的中国开发者或社区公开归属依据继续待核实。
- 后续补齐：中国公开归属、作者视频与仓库互链、原片时间点、旧 aether-os 与当前 na-kernel 的沿革、上游组件及许可来源、独立运行记录。

本轮将其列为新待核实线索，正式条目数量按 OpenXJ380 一项增加。

## 3. NeoRunST 有界复查

复查 [Issue #13](https://github.com/yuyan-lang/chinese-programming-languages/issues/13) 既有 2026-07-06 [TheseusOS 标题视频](https://www.bilibili.com/video/BV1APTR6yEzo/)、NeoRunST 名称和公开源码入口。

GitHub 仓库检索 NeoRunST 与 TheseusOS 热土 本轮返回空结果。公开网页检索继续召回既有二次汇编文章。原视频和 Bilibili 搜索页本轮网页文本工具返回不可访问；已保存的 TheseusOS 沿革结论保持原有证据级别。当前内核来源、源码入口、重写过程和版本对应继续待核实。本轮完成了有界复查，新增确定沿革结论为 0。KunOS 沿用第四轮记录，本轮未重复追查停滞的归属问题。

## 检索范围、关键词与限制

平台：只读 GitHub 仓库、内容、提交、树及 Releases API；公开网页检索；Bilibili 原视频与作者页面；项目官网。第二来源检索召回 OSDev、项目文档、聚合文章及 DeepWiki，技术结论回溯到原始仓库或作者材料。聚合文章用于发现线索。

日期窗口：优先寻找 2024-01-01 至 2026-10-10 的公开项目或持续开发记录；实际主证据集中于 OpenXJ380 2026-07 至 2026-10、NeoAetherOS 2025-04 至 2026-08。2022–2023 年 XJ380 同名视频只作沿革线索。

实际检索组合：
- site:bilibili.com/video 自制 操作系统 内核 github 2025
- site:bilibili.com/video 自制 操作系统 内核 开源 2026
- site:bilibili.com/video 自制操作系统 开源 2024
- site:bilibili.com/video 自制操作系统 github；结合 -Linux、-字幕、-课程、-KunOS、-CoolPotOS、-LuminaOS
- site:github.com kernel China bilibili；结合既有项目排除词
- site:bilibili.com/video 操作系统 github.com 2024/2025 自制；结合 -字幕、-课程、-LinuxFromScratch
- NeoAetherOS github、NeoAetherOS VOID2913、NeoAetherOS China、NeoAetherOS 国产、NeoAetherOS site:bilibili.com/video
- NeoAetherOS 自制 JVM、NeoAetherOS 桌面环境 XIAOYI80386、aether-os-studio China、lihanrui2913 中国、lihanrui2913 bilibili、VOID2913 操作系统 开源
- OpenXJ380 开源 第30集、XJ380 第30集、site:bilibili.com/video XJ380 开源 2026 08
- NeoRunST、NeoRunST TheseusOS github、NeoRunST 内核、NeoRunST Theseus、NeoRunST 热土 TheseusOS、NeoRunST site:github.com、BV1APTR6yEzo、热土工作室 源码
- 辅助发现：Plant-OS 中国 github、PlantOS 2025 bilibili、自制操作系统 2026 开源；Plant-OS 仅作来源关系和后续候选线索

GitHub 精确仓库检索：NeoRunST、TheseusOS 热土、NeoAetherOS。另外沿已核实仓库读取 README 历史与截至 2026-08-02 的提交集合，以区分创建、导入和版本变更。

召回边界：
- 泛词搜索混合教程、Linux 发行版、译制视频、网页模拟项目与同名软件。技术结论按自主内核路径、具体上游和作者材料逐项确认。
- 网页搜索对长项目名的精确召回较少，部分结果仅为 Bilibili 搜索索引；该层信息保留为发现线索。
- Bilibili 文本抓取对部分原页返回 412 或不可访问。OpenXJ380 的原片画面已通过原视频核对，NeoAetherOS 与 NeoRunST 对应缺口保持待核实。
- GitHub contributors API 请求返回工具不支持；OpenXJ380 作者归属采用组织自述和仓库贡献者文档。
- 页面索引可能保留早期描述。当前技术状态以固定提交为准；作者原片按自身发布时间和片源情况记录。
- 本轮研究采用只读网页与 GitHub 核验，交付文件为研究资料。独立编译、下载项目执行、虚拟机和实机测试留待后续授权任务。
