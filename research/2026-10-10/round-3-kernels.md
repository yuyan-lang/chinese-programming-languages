# 内核板块本轮补充资料

核验日期：2026-10-10。目标目录：[yuyan-lang/chinese-programming-languages](https://github.com/yuyan-lang/chinese-programming-languages)。

## 结果

本轮收录 CoolPotOS、Uinxed-Kernel 两项资料。结构化记录保存在 data/kernels.json。两项均有作者归属、自有内核定位、固定源码、架构、调度、内存、文件系统、设备驱动、许可证和发布记录依据。

- CoolPotOS：XIAOYI12 发起并与 plos-clan 成员共同开发。原作者于 2025-02-21 发布 AMD64 视频，标题明确使用国产自研表述，简介直链项目仓库。GitHub 作者档案所链 Bilibili 账号与视频 UP 主账号一致。2025-09-17 LINUX DO 原帖说明项目从个人裸机程序发展而来。
- Uinxed-Kernel：ViudiraTech 社区维护的 x86-64 类 UNIX 宏内核。社区公开介绍明确自述来自中国。CREDITS、README 与内核入口文件提供贡献者和实现定位依据。

## 防重与文档规范

开工前读取：
- [AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/AGENTS.md)
- [data/kernels.json](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/data/kernels.json)
- [首轮核验记录](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/kernels.md)
- [Issue #13](https://github.com/yuyan-lang/chinese-programming-languages/issues/13) 及[现存补充评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/13#issuecomment-6099005974)

核验时正式目录包含 DragonOS、xbook2、LuminaOS；Issue #13 跟进 KunOS 与 NeoRunST。本轮两项与这些记录互异。公开条目采用直接肯定式事实陈述，资料缺口按待核实标注。

## CoolPotOS 证据链

### 归属、项目定位与历史

1. [GitHub 作者档案](https://github.com/xiaoyi1212/xiaoyi1212/blob/3deb32e62c876625746065519088426fe6d2239a/README.md) 明确链接 [Bilibili 账号 3537113156946497](https://space.bilibili.com/3537113156946497) 与 plos-clan 社区。
2. [2025-02-21 原视频](https://www.bilibili.com/video/BV1EEAZeoEks/) 的 UP 主为 XIAOYI80386，UP 主链接对应上述账号。标题有国产自研表述。简介列出 AMD64、x2APIC、PCIe、SMP、devfs，并链接仓库 x86_64 分支。
3. [2025-09-17 作者原帖](https://linux.do/t/topic/964568) 说明个人裸机程序起点及合作开发，记录当时 IA32/AMD64、80+ Linux syscall、initramfs、devfs 与 EEVDF。正文属于作者声明。
4. 同帖第 7 楼，作者回顾第一次仓库提交日期为 2024-01-11。[仓库 API](https://api.github.com/repos/plos-clan/CoolPotOS) 给出的 created_at 为 2023-12-30T05:54:36Z。这两个字段各自保存。最早公开发布日为待核实。
5. [2026-03-24 更新原帖](https://linux.do/t/topic/1805284?tl=en) 说明服务管理器及 OverlayFS/SquashFS 根文件系统组合。

### 固定源码与发布

快照：[0ef305ef854476d8e7cda63f4293ebe4638d0604](https://github.com/plos-clan/CoolPotOS/commit/0ef305ef854476d8e7cda63f4293ebe4638d0604)，rebuild 分支，提交时间 2026-04-26T12:33:55Z。

- 启动：src/arch/x86_64/boot/limine_req.c 定义 Limine 协议请求；src/arch/x86_64/main.c 的 kmain 接通内存、GDT/IDT、驱动、任务系统及 init 进程。
- 调度：src/task/eevdf.c 可见 vruntime、deadline、资格计算及红黑树队列；src/task/scheduler.c 按 EEVDF_SCHEDULER 编译开关接入。
- 内存：src/mem/buddy.c 含页块分裂、合并及 DMA/DMA32/Normal 分区；src/arch/x86_64/mem/page_x64.c 含四级页表。
- 文件系统：src/fs/vfs.c 含路径、节点、回调和文件操作；main.c 注册 tmpfs、devtmpfs、overlayfs、pipefs、sysfs。
- 驱动：src/driver/ahci/ahci.c 含设备信息、命令槽和命令表处理。
- 语言：CMakeLists.txt 声明 C/ASM；src/arch/x86_64/dt/entry.S 含 iretq 中断返回。
- [最新正式 Release re440](https://github.com/plos-clan/CoolPotOS/releases/tag/re440)，名称 CoolPotOS SIMA，published_at 为 2026-03-16T13:35:54Z，资源名包含 0.4.40。
- LICENSE 为 MIT。README 单列社区组件与 ACPICA、libfdt、Zstd 等来源。

### 版本边界

- 2025-02 视频采用宏内核表述，2025-09 原帖采用混合内核表述。结构化条目分别保留阶段信息，跨版本内核类型沿革列为待核实。
- 快照 CMake 接受 x86_64、riscv64、loongarch64。README 参数列出 x86_64、riscv64、aarch64。条目把源码构建目标、历史作者架构声明与待核对应关系分别呈现。
- 官网时间线的公开网页索引列出 2024-09-23 宣发节点；Bilibili 搜索索引显示另一个早期视频为 2024-09-27。早期视频页面抓取失败，两项日期均留在研究记录，正式 first_public 保持待核实。
- 原视频本轮核验范围为页面标题、简介、UP 主与源仓库关联。视频关键帧、构建和实机运行属于待核实。

## Uinxed-Kernel 证据链

### 归属与项目定位

- [社区公开介绍](https://github.com/ViudiraTech/.github/blob/de574fec752dc1e42f42c0f48fd1b2df05ea3fc3/profile/README.md) 明确自述来自中国，将 Uinxed-Kernel 列为核心项目。
- [CREDITS](https://github.com/ViudiraTech/Uinxed-Kernel/blob/ba4c809852a357378ab6058da5f514cceb8819c3/CREDITS) 列出 MicroFish/FengHeting、Rainy101112、JiTianYu391 等贡献者，并说明共同维护。
- [固定 README](https://github.com/ViudiraTech/Uinxed-Kernel/blob/ba4c809852a357378ab6058da5f514cceb8819c3/README.md) 说明 x86-64、C、自建类 UNIX 宏内核和 Linux 兼容 ABI。
- [仓库 API](https://api.github.com/repos/ViudiraTech/Uinxed-Kernel) 给出 created_at 为 2024-07-23T11:13:17Z。最早公开发布日为待核实。

### 固定源码与发布

快照：[ba4c809852a357378ab6058da5f514cceb8819c3](https://github.com/ViudiraTech/Uinxed-Kernel/commit/ba4c809852a357378ab6058da5f514cceb8819c3)，master 分支，提交时间 2026-10-03T16:36:51Z。

- 启动：boot/limine_request.c 的入口请求指向 kernel_entry；init/main.c 完成内存、平台、设备和进程初始化，加载 PID 1 后调用 sched_start。
- 调度：kernel/sched/sched.c 可见 EEVDF 运行队列、虚拟运行时间、截止时间、资格判定和红黑树入队逻辑。
- 内存：mem/buddy.c 实现按阶页块分配、分裂、合并、释放与一致性检查。
- 文件系统：fs/core/vfs.c 含节点、权限、路径及页缓存后端；main.c 注册多类文件系统。
- 驱动：drivers/block/ata/sata/ahci.c 含 PCI 匹配、MMIO、命令槽及端口启停。
- 构建：Makefile 收集 C 源文件，配置 freestanding 编译与无标准库链接，提供 x86-64 QEMU 目标。
- [v0.4.0 Release](https://github.com/ViudiraTech/Uinxed-Kernel/releases/tag/v0.4.0) published_at 为 2026-07-22T16:29:17Z。发布说明列出 EEVDF、ELF 加载器、IPC、DRM、evdev 等。
- 现存 Releases 集合里时间最早条目为 v0.1.1，发布日期 2026-05-19。该字段描述本轮观察到的发布集合。
- LICENSE 为 Apache-2.0；NOTICE 列出 Limine、OVMF、FatFs 及点阵字体来源和各自许可。

### 版本边界

- Linux syscall 编号 0–462 是 ABI 编号范围。README 将实现覆盖描述为子集，逐项兼容测试为待核实。
- README 记述 Alpine Linux 3.23 用户环境、Xfce/X11 及 Dell PowerEdge R410 运行情况；条目标记为作者声明。
- 搜索发现第三方目录把内核标为 Microkernel。正式条目采用作者固定 README 的 monolithic 表述。
- 搜索发现 2025 年 Reddit 推广帖子提到 GPLv3。当前条目许可证采用固定源码的 Apache-2.0，历史许可沿革和完整来源审计为待核实。
- 原作者演示录屏的账号关联、镜像对应和独立运行记录为待核实。

## 平台、关键词与时间范围

本轮发现路径采用 Gitee/GitCode 与中文技术社区轮换。随后沿项目原帖和作者链接进入 GitHub、Bilibili 与社区官网交叉核验。

主要检索：
- site:gitee.com 自制操作系统 2025
- site:gitee.com 内核 2024 个人 操作系统
- site:gitee.com 自研 操作系统 内核，并排除 openEuler/OpenHarmony/Linux 大型发行版关键词
- site:gitee.com 内核 玩具 操作系统
- site:gitee.com 操作系统 个人开发
- site:gitcode.com 自制 操作系统
- site:gitcode.com 自研内核
- 自制操作系统 2025 开源
- 自制操作系统 2024 gitee
- 自研内核 2025 gitee
- site:cnblogs.com 自制操作系统 2025/2026
- CoolPotOS 作者 开源
- site:linux.do/t/topic CoolPotOS
- plos-clan 中国
- xiaoyi1212 中国
- CoolPotOS 哔哩哔哩 / Gitee
- Uinxed kernel 作者
- ViudiraTech China
- Uinxed site:gitee.com / site:bilibili.com

时间重点：2024–2026 原作者公开发布。历史字段回溯到 CoolPotOS 仓库创建的 2023-12-30 与作者回顾的 2024-01-11，Uinxed 仓库创建的 2024-07-23。

## 覆盖与遗漏风险

- Gitee 检索主要返回《30天自制操作系统》学习仓库、课程材料、镜像与大型发行版。GitCode 返回教材镜像推广文。此次正式补充来自中文社区与作者原始来源链。
- Gitee/GitCode 搜索引擎索引的召回范围有限；低关注仓库、近期建立项目、站内独有页面和登录可见资料仍有覆盖空间。
- 部分官网页面返回 502，原视频早期页面返回抓取失败。正式收录依靠成功读取的原作者页面和固定源码。
- 搜索引擎相对发布日期仅用于发现；正式日期使用原页绝对日期或 GitHub published_at/commit 元数据。
- 源码静态阅读验证具体实现结构；作者声明、视频页面信息和独立运行核验采用独立证据级别。
- 本轮范围为只读资料研究与研究文件整理。

