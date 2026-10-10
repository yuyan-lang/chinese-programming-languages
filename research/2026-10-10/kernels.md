# 操作系统内核板块首轮记录

核验日期：2026-10-10。范围：中国开发者及中国社区在B站、源码平台、官网和技术社区公开发布的内核项目。

## 结果

- 收录3项：DragonOS、xbook2、LuminaOS。
- 保存2项待核线索：KunOS、NeoRunST，见[Issue #13](https://github.com/yuyan-lang/chinese-programming-languages/issues/13)。
- 官网资料和固定源码快照用于核实DragonOS、xbook2；LuminaOS兼有原作者视频、公开档案和内核源码依据。
- 结构化资料与完整来源索引见[data/kernels.json](../../data/kernels.json)；网页目录为[内核板块](../../内核/index.html)。

## 首批证据

### DragonOS

社区[公开档案](https://github.com/DragonOS-Community)标记所在地China，官网[项目介绍](https://dragonos.org/archives/46)给出负责人龙进。作者[首版发布文](https://dragonos.org/archives/52)与[周年回顾](https://dragonos.org/archives/62)形成历史资料链。
固定源码提交：c369843d9ed1985d34c90f40aa1f5788c69463d3。阅读范围包括架构模块、启动参数、公平调度数据结构、伙伴分配器、文件系统入口和AHCI设备结构。
正式发布字段采用[V0.4.0发布记录](https://github.com/DragonOS-Community/DragonOS/releases/tag/V0.4.0)，日期2025-12-22。功能文档中的CFS/FIFO/RR属于作者说明；fair.rs的虚拟运行时间、截止时间和队列字段属于源码观察，按各自来源标注。

### xbook2

[胡自成署名技术文章](https://www.kerneltravel.net/blog/2021/bookos/)介绍国产32位内核xbook2及BookOS关系；[作者公开档案](https://github.com/hzcx998)标记所在地Shenzhen。
固定源码提交：1450d228ce538ae8ad1a2f96e442b8da22e06950。阅读范围包括Multiboot2启动、调度、虚拟/物理内存、FatFs接入和IDE驱动。
v0.2.1标签目标提交日期为2021-10-13，GitHub最近Release记录为v0.1.7。标签、提交及发布日期各有独立字段。

### LuminaOS

[原作者视频](https://www.bilibili.com/video/BV1ET3R6jEWv/)发布于2026-08-02，并关联GitHub账号Lumina-hc。[作者公开档案](https://github.com/Lumina-hc)所在地为Shanxi Province, China。
视频00:36展示mem/ver输出，01:01展示图形桌面。视频版本为v0.7.0；固定源码1014c8fb1a7e8ded72f6ed82ebb41fd9cae21aa2包含v0.7.1字串。
BIOS引导证据来自boot/boot.asm，保护模式及kernel_main调用来自kernel/arch/i386/boot.asm；内核初始化与分页分别来自main.c和paging.c。公开页面链接原视频，关键帧用于本轮人工核对。

## 研究方式与覆盖

平台：GitHub、Gitee、项目官网、作者署名技术社区文章、Bilibili搜索与原视频、公开网页搜索。
时间覆盖：xbook2从2020年的仓库历史起，DragonOS从2022年的开源记录起，个人视频项目重点2026年公开演示。
检索围绕自制操作系统、自研内核、国产内核、项目名称、作者账号及源码入口展开。检索与目录交叉核对覆盖DragonOS、xbook2、LuminaOS、KunOS和NeoRunST。
来源核验采用只读资料、源码静态阅读和作者录屏观察；独立构建、实机兼容及完整来源审计为待核实项。低关注度投稿、作者动态、评论和历史镜像仍有资料补充空间。

## 后续方向

继续跟进Issue #13的项目归属和内核沿革，发现原作者公开展示的个人/教学/AI辅助项目。每项能力标注具体版本与依据，资料维护遵循根目录AGENTS.md的直接肯定式写作规范。

## 复核补充

DragonOS官网一周年文章关联[2022年进展回顾视频](https://www.bilibili.com/video/BV1a8411N7XS/)，原页面发布日期2023-01-15。该来源作为历史作者发布材料保存。
NeoRunST历史阶段原视频为[BV1APTR6yEzo](https://www.bilibili.com/video/BV1APTR6yEzo/)，日期2026-07-06，提及转向TheseusOS；后续重写与当前来源由Issue #13继续核实。
