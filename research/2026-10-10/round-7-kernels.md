# 第七轮个人内核普查：QuantumNEC 与 racaOS

核验日期：2026-10-10。起点为目录固定提交 `697f78bd2d10a85a0c0c8cce9444bf03bdbf415a`。本轮使用公开网页检索、只读 GitHub 内容和 dot 云浏览器读取作者及社区页面。

## 结果与收录建议

- 本轮新增项目线索 4 项：QuantumNEC、racaOS、BearOS／小熊操作系统、OS002。
- 深入核验 2 项：QuantumNEC、racaOS。
- 正式内核目录新增建议 0 项。两项深查对象的自身内核定位与固定源码已经取得，明确中国开发者或中国社区归属自述继续待核实。
- BearOS、OS002 各保存一个待核实记录，保留已定位入口。
- Issue #13 的 KunOS 归属缺口做了有界复核，新实质进展为 0。
- 独立构建、下载执行项目、虚拟机与实机运行属于后续核验范围。
- 交付包含空的正式候选数组、5 项待核实数组和本日志。两项深入候选按现有内核条目结构完整保存，便于取得归属证据后继续整理。

## 去重与起点

已阅读 [AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/697f78bd2d10a85a0c0c8cce9444bf03bdbf415a/AGENTS.md)、[7 项内核目录](https://github.com/yuyan-lang/chinese-programming-languages/blob/697f78bd2d10a85a0c0c8cce9444bf03bdbf415a/data/kernels.json)、[Issue #13](https://github.com/yuyan-lang/chinese-programming-languages/issues/13)及评论、[Issue #18](https://github.com/yuyan-lang/chinese-programming-languages/issues/18)，并对照第六轮内核日志和更早内核发现记录。

正式目录中的 DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380、NeoAetherOS／na-kernel 已排重。NeoAetherOS 为第六轮完成的旧线索核实，本轮保持已有结果。PlantOS、LunaixOS 在早轮日志中出现，本轮仅用于识别来源关系和候选发现路径。

## QuantumNEC

### 作者与归属

[社区项目页固定快照](https://github.com/plos-clan/docs/blob/fc84dc13f484e8a0bc87e62d1956312b6a9a6a46/docs/project/QuantumNEC.md)明确写明 SegmentationFaultCD 使用现代 C++ 开发 QuantumNEC，并直接链接 [B站账号段错误核心已转储](https://space.bilibili.com/1226480503)。[组织主页](https://github.com/plos-clan)把 SegmentationFaultCD 列入公开管理员。

作者 [GitHub 主页](https://github.com/SegmentationFaultCD)的地域字段为 “The earth”。已读取其当前个人 README 及少量历史 README；这些页面提供技术兴趣和项目联系，明确中国归属自述继续待核实。[社区关于页](https://plos-clan.org/about/)同样留有归属资料缺口。上述结论只覆盖已检查页面。作者国籍、社区所在地、账号中的文字和平台使用习惯分别处理。

### 时间与版本

- [仓库元数据](https://api.github.com/repos/SegmentationFaultCD/QuantumNEC)：仓库 ID 857944900，created_at 为 2024-09-16T02:12:45Z。
- [README](https://github.com/SegmentationFaultCD/QuantumNEC/blob/6216373689baa6302cdb2a3b4656955063510b1e/README.md)：作者回顾开发起点 2023-01-01。
- [现存根提交](https://github.com/SegmentationFaultCD/QuantumNEC/commit/576ef489e45e30ea8088751b9edd97e3add25a89)：2024-09-16T02:29:14Z，parents 为空。
- [固定快照](https://github.com/SegmentationFaultCD/QuantumNEC/commit/6216373689baa6302cdb2a3b4656955063510b1e)：limine 分支，2026-07-27T15:30:53Z。
- [Releases 集合](https://api.github.com/repos/SegmentationFaultCD/QuantumNEC/releases?per_page=20)返回空数组。正式版本待核实。
- [分支集合](https://api.github.com/repos/SegmentationFaultCD/QuantumNEC/branches?per_page=100)包含 Edk2、LegacyBIOS、limine。[plos-clan/QuantumNEC](https://api.github.com/repos/plos-clan/QuantumNEC)是另一个公开仓库，默认 Edk2。其复制、迁移与继承范围继续待核实。

固定提交说明为 “Used Opencode to rebuild arch”。这支持记录该次提交的 AI 辅助开发声明；项目整体的 AI 使用范围继续待核实。

### 当前源码层

固定前缀：`https://github.com/SegmentationFaultCD/QuantumNEC/blob/6216373689baa6302cdb2a3b4656955063510b1e/`

- [xmake.lua](https://github.com/SegmentationFaultCD/QuantumNEC/blob/6216373689baa6302cdb2a3b4656955063510b1e/xmake.lua)：x86-64、C23/C++26、micro_kernel.elf 和独立 filesystem 服务目标。
- [source/kernel/boot/kloader.cpp](https://github.com/SegmentationFaultCD/QuantumNEC/blob/6216373689baa6302cdb2a3b4656955063510b1e/source/kernel/boot/kloader.cpp)：Limine base revision 3；串口、IDT、GDT、内存、显示、ACPI、APIC 与任务相关初始化。
- 固定入口中 SMP、系统调用、模块加载和开中断调用处于注释状态；入口后半部执行内存分配和 C++ 容器测试。这些源码事实为当前快照的运行核验提供具体检查点。
- [source/kernel/task/schedule/Muqss.cpp](https://github.com/SegmentationFaultCD/QuantumNEC/blob/6216373689baa6302cdb2a3b4656955063510b1e/source/kernel/task/schedule/Muqss.cpp)：时间片、nice、虚拟截止时间、实时/普通队列、yield 和 wake_up。
- [source/kernel/memory/allocator/page.cpp](https://github.com/SegmentationFaultCD/QuantumNEC/blob/6216373689baa6302cdb2a3b4656955063510b1e/source/kernel/memory/allocator/page.cpp)：Limine 内存映射、页面区域、位图、红黑树与空闲统计。
- [内核文件服务](https://github.com/SegmentationFaultCD/QuantumNEC/blob/6216373689baa6302cdb2a3b4656955063510b1e/source/kernel/syscall/services/filesystem.cpp)与[服务进程](https://github.com/SegmentationFaultCD/QuantumNEC/blob/6216373689baa6302cdb2a3b4656955063510b1e/source/module/filesystem/fs_servicer.cpp)包含接口骨架；完整 VFS 与持久文件系统能力待核实。

### 原视频层

社区作者页、B站账号和原片页面建立了直接作者关联：

- [当现代 C++ 遇上操作系统](https://www.bilibili.com/video/BV1yuWFzSEbi/)，原片日期 2025-09-20。
- [成长日志 #1：异常处理](https://www.bilibili.com/video/BV13M411u7yc/)，作者频道列出 2023-04-02。
- [成长日志 #2：内存](https://www.bilibili.com/video/BV14s4y1i7YS/)，作者频道列出 2023-05-31。
- [成长日志 #3：任务、调度、ACPI、分页](https://www.bilibili.com/video/BV1a1421f755/)，2024 年原片。

本轮读取了原片标题、频道和部分简介，并观察 #3 的作者说明画面。运行效果、功能画面时间点、拍摄版本和固定源码的对应继续待核实。#3 页面在重绘前后显示跨自然日日期，精确发布时间待标准元数据核对。功能依据保持“作者声明”“源码可见”“作者演示待进一步核验”“独立运行待核实”四层。

### 上游与许可证

[根 LICENSE](https://github.com/SegmentationFaultCD/QuantumNEC/blob/6216373689baa6302cdb2a3b4656955063510b1e/LICENSE)为 GPLv3 文本。[.gitmodules](https://github.com/SegmentationFaultCD/QuantumNEC/blob/6216373689baa6302cdb2a3b4656955063510b1e/.gitmodules)列出 Limine、fmt 与 libos-terminal。完整源码树固定：

- Limine：0765b5db055680471cea3180e8277dcf701847dc，[BSD-2-Clause 文本](https://github.com/Limine-Bootloader/Limine/blob/0765b5db055680471cea3180e8277dcf701847dc/LICENSE)
- fmt：e9ddc97b9aa8acf323212d55f45f1d6e6e4f8ab3，[MIT 文本及可选嵌入例外](https://github.com/fmtlib/fmt/blob/e9ddc97b9aa8acf323212d55f45f1d6e6e4f8ab3/LICENSE)
- libos-terminal：该快照保存静态库和头文件，上游二进制版本待核实
- 随附固件与完整第三方许可清单待核实

## racaOS

### 作者与归属

[社区固定项目页](https://github.com/plos-clan/docs/blob/fc84dc13f484e8a0bc87e62d1956312b6a9a6a46/docs/project/racaos.md)将 racaOS 归于 UEFIer，直接链接 [zzjrabbit/racaOS](https://github.com/zzjrabbit/racaOS)。[社区管理页](https://github.com/plos-clan/docs/blob/fc84dc13f484e8a0bc87e62d1956312b6a9a6a46/docs/group/group.md)列出 zzjrabbit 的社区角色。

已读取 [作者 GitHub 主页](https://github.com/zzjrabbit)、个人 README、[个人网站关于页](https://zzjrabbit.github.io/about.html)、社区项目与管理页。公开项目关系已成立，明确中国开发者或中国社区归属自述继续待核实。

### 当前版与旧版分层

[edition21 README](https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/README.md)说明项目经历多次重构，当前目标为 LoongArch64，使用增强 framekernel 思路及动态模块。作者标记第一版生日为 2023-01-28，当前版生日为 2025-11-20。

- [仓库元数据](https://api.github.com/repos/zzjrabbit/racaOS)：ID 811092792，created_at 为 2024-06-05T23:18:15Z。
- [edition21 根提交](https://github.com/zzjrabbit/racaOS/commit/879e7fa0d1c13d213397aa3cf8de33255ed87698)：2025-11-23T03:41:04Z，parents 为空。
- [固定当前提交](https://github.com/zzjrabbit/racaOS/commit/72ab92f0e296fd6889059315afa5a9850ae582ba)：2025-12-08T14:53:56Z。
- [最新现存正式 Release v16.1.0](https://github.com/zzjrabbit/racaOS/releases/tag/v16.1.0)：2024-12-06T14:02:15Z。它属于历史版本阶段。
- [分支集合](https://api.github.com/repos/zzjrabbit/racaOS/branches?per_page=100)：edition12、14、15、16、18、19、20、21。

[edition12 README](https://github.com/zzjrabbit/racaOS/blob/45a4861daf1061c21cb71ac7f5cad0b2ab973d94/README.md)记录 x86_64、抢占式多任务、文件系统和 AHCI 等旧阶段进度。v14.4 发行说明提及 FAT 挂载与 NVMe；v16.0.0 记载 VFS、CPIO initramfs 和内核模块；v16.1.0 记载 yield/sleep 及 shell 改动。当前 edition21 的路线图与这些历史版本分别呈现。

### 当前源码层

固定前缀：`https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/`

- [zodiac/src/boot/mod.rs](https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/zodiac/src/boot/mod.rs)：Limine base revision 4、kmain、可执行文件和地址请求。
- [init/src/main.rs](https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/init/src/main.rs)：模块初始化和 idle_loop。
- [init/src/module/mod.rs](https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/init/src/module/mod.rs)：core_dylib、logger、errors、memory、filesystem、task 模块清单，解析模块后调用入口。
- [zodiac/src/mem/frame.rs](https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/zodiac/src/mem/frame.rs)：4 KiB 位图页帧分配/回收。
- [modules/memory/src/lib.rs](https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/modules/memory/src/lib.rs)：Vmar 映射、写入、读回和断言测试。
- [任务模块](https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/modules/task/src/lib.rs)与[文件系统模块](https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/modules/filesystem/src/lib.rs)当前入口为空。README 把多任务、用户态、FAT/ext2/ext4 等列为路线图项。
- [builder/src/main.rs](https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/builder/src/main.rs)使用 LoongArch64 QEMU virt/la464 参数。参数中的设备清单属于模拟机配置；内核驱动完成度以对应源码和路线图核对。

### 上游与许可证

当前 README 感谢 Asterinas OSTD/OSDK 的设计启发及 wenxuanjun 的页表示例。社区历史文档记载基于 TrashOS，并列有基础代码及驱动贡献者。edition12 README 记载 raca_loader 基于 bootloader 0.11.3，并感谢 phil-opp 的 x86_64 库及 rCore 模板/思路。

[Cargo.lock](https://github.com/zzjrabbit/racaOS/blob/72ab92f0e296fd6889059315afa5a9850ae582ba/Cargo.lock)记录 Limine crate 0.5.0、acpi 6.0.1、talc 4.4.3 和 elf 0.8.0。完整上游、导入提交和许可清单待核实。

当前仓库许可字段为空；完整 edition21 树中根许可文件待取得。社区历史页面展示 GPLv2 徽章，其适用版本及当前授权范围继续核实。

已定位 [2023 年社区成员关联文章](https://www.bilibili.com/opus/809991700591149093)，作者为段错误核心已转储。它是项目历史线索。racaOS 原作者频道、当前原片和独立运行继续待核实。

## 另外两条新增线索

### BearOS／小熊操作系统

[MedAIFan 作者官网](https://www.medaifan.net/)列出 BearOS V0.10，并说明作者业余开发自己的操作系统。官网列出图形模式、中文输入输出、Shell、文件系统、磁盘文件运行、C 类库、编辑器及 BasC 语言，均按作者声明记录。[项目入口](https://www.medaifan.net/bearos.html)已定位。

B站搜索索引出现胖嘟嘟的超级熊发布的 BearOS 系统内核与文件管理视频。官网作者与账号互链、原 BV、明确公开归属、内核来源、源码与许可证继续待核实。搜索中存在多个 BearOS 同名项目，后续应以作者官网互链去重。

### OS002

B站搜索索引将 OS002 关联到 Liu_Chunyi，标题提及 C、多线程与中断。保存[索引入口](https://search.bilibili.com/all?keyword=%E9%9B%ABOS)。原片 BV、作者主页、公开归属、自身内核定位、实现关系、许可和版本继续待核实。

## KunOS 有界复核

已重新阅读 Issue #13 两条评论，并检查 [hellopgrmm 公开 GitHub 主页](https://github.com/hellopgrmm)。该主页直接列出 KunOS 与个人站仓库，明确中国归属自述继续待核实。本轮沿用已核验的 XKFS、视频与自定义授权说明，归属事项新实质进展为 0，Issue #13 保持原待核实方向。

## 检索方法、时间范围与遗漏风险

### 关键词

发现阶段使用：
- 自制操作系统 github；手搓操作系统 github；B站 手搓 内核；AI写 操作系统 bilibili
- 自制操作系统 国产；icestaros；BearOS 胖嘟嘟；OS002 Liu_Chunyi
- Plant-OS github；LunaixOS github 中国
- QuantumNEC；racaOS；QuantumNEC 国产；racaOS 国产
- SegmentationFaultCD China／bilibili；zzjrabbit China／中国；racaOS UEFIer
- KunOS hellopgrmm；KunOS 中国；hellopgrmm 关于／中国

搜索引擎查询采用不限日期的索引发现，资料时间跨度主要为 2023-01 至 2026-10-10；源码历史核验区分作者自述开发时间、仓库创建时间、当前分支根提交、Release 时间与视频发布时间。进入深查阶段后，仅对 QuantumNEC 与 racaOS 继续跟进；KunOS 仅做归属缺口复核。

### 平台与读取范围

- GitHub：主目录、作者仓库 README、固定源码、完整树、分支、提交与 Release 元数据；两项候选均通过固定 commit 链接记录。
- Bilibili：公开索引、QuantumNEC 作者频道与原片、racaOS 关联文章。
- 社区网站：plos-clan 项目、管理、关于页面；作者公开主页。
- dot 云浏览器：弥补网页提取的缓存缺失、429 与 502，读取页面公开展示内容。
- 研究产物通过本轮数据文件和日志保存，外部仓库更新由汇总任务统一处理。

### 限制与遗漏风险

1. 明确公开归属是正式收录的当前缺口。中文写作、B站/QQ使用、账号名、开发时区或社区成员姓名提供的线索均待明确自述支持。
2. 网页检索对小项目索引稀疏，部分查询返回聚合搜索页、同名项目或无关内容；相关结果只用于发现入口。
3. B站页面存在异步加载、时区重绘、试看提示与自动连播。视频标题、URL和账号已交叉核对，未完成的功能画面核验继续保留。
4. GitHub fork 字段和同名仓库只能说明平台状态，完整源码继承范围需要历史比较和作者文档继续补齐。
5. racaOS 多次重构造成架构、调度、文件系统和许可证的版本差异，后续条目应继续按阶段记录。
6. 两项固定源码中的占位与注释调用影响可运行性推断。本轮结论限定为源码可见结构和作者资料。
7. 此轮发现覆盖小范围公开入口；社区图谱中的其他自制内核、未公开源码视频、Gitee/Codeberg独立项目与未被搜索引擎索引的作者仍有遗漏可能。

