# 第九轮个人内核主动发现：TextOS 与 AI Rust 操作系统线索

核验日期：2026-10-10。目录基线：d4b23b6fb82c695a34f600582a4fa6399c44fb89。

## 结果

- 新发现并深入2组：TextOS；未定名AI Rust操作系统（编剧笨笨）。
- 正式新增建议1项：TextOS。公开中国归属、作者／原片频道／仓库关联、自身内核工程和固定源码证据已经取得。
- 新待核实1组：编剧笨笨的AI Rust系统。原片具有作者国产自述；名称、源码、架构和内核边界继续待核实。
- 旧候选深入0项。本轮已按现有目录与开放议题排重。
- 原片功能画面可靠时间点、源码与视频的一一对应、独立运行继续待核实。

## 起点与排重

已阅读[AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/d4b23b6fb82c695a34f600582a4fa6399c44fb89/AGENTS.md)、[7项内核目录](https://github.com/yuyan-lang/chinese-programming-languages/blob/d4b23b6fb82c695a34f600582a4fa6399c44fb89/data/kernels.json)、[第八轮日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/d4b23b6fb82c695a34f600582a4fa6399c44fb89/research/2026-10-10/round-8-kernels.md)。
开放内核[Issue #13](https://github.com/yuyan-lang/chinese-programming-languages/issues/13)、[Issue #18](https://github.com/yuyan-lang/chinese-programming-languages/issues/18)、[Issue #23](https://github.com/yuyan-lang/chinese-programming-languages/issues/23)及各自全部2条评论已经读取。
另对首批、第三至第七轮内核日志检索TextOS、Maouai233、ljQAQ233、编剧笨笨及新原BV，结果均为空。

正式7项为DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380、NeoAetherOS。旧pending KunOS、NeoRunST、QuantumNEC、racaOS、BearOS和OS002本轮保持原有资料。

## 检索方法与入口

普通网页检索采用“手搓内核”“AI写操作系统”“自制内核”“自制操作系统”及2024—2026限定。首轮搜索混入课程广告、系统界面和同名页面，随后转向B站公开搜索页与作者仓库。

[B站自制操作系统检索](https://search.bilibili.com/all?keyword=%E8%87%AA%E5%88%B6%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F)在公开网页浏览器可读，返回新AI系统原片和既有LuminaOS、KunOS、NeoRunST、CoolPotOS。综合排序为发现样本，搜索覆盖和结果排序存在局限。TextOS来自“自制操作系统＋GitHub＋2025”普通网页检索，技术依据全部回到原作者仓库与原作者页面。

初筛另见VergeOS原BV1UaHp6KEYx；本轮深入收束到上述2组，VergeOS继续作为检索背景，本轮正式与pending计数均仅覆盖已整理两组。

## TextOS

### 作者与中国归属

[作者GitHub主页](https://github.com/ljQAQ233)在2026-10-10的公开网页浏览器当前页面显示所在地“Guangxi China”，置顶textos-dev。
[固定README](https://github.com/ljQAQ233/textos-dev/blob/75ebadf4134f6144ed1ffc0b1d3229582766db4f/README.md)直接给出B站Maouai233（UID503518259）；[作者专栏](https://www.bilibili.com/opus/824406955174920192)反向列出textos-dev、textos-pre，说明B站系列和仓库对应关系。这组来源建立公开作者和源码身份链。记录保留技术身份及地域自述。

### 自身内核与组件

固定提交：75ebadf4134f6144ed1ffc0b1d3229582766db4f，提交时间2026-10-01T13:53:49Z。

- [SigmaBoot主程序](https://github.com/ljQAQ233/textos-dev/blob/75ebadf4134f6144ed1ffc0b1d3229582766db4f/src/boot/SigmaBootPkg/Main.c)读取内核与内存映射、调用ExitBootServices，随后传递配置并跳到内核入口。
- [内核构建](https://github.com/ljQAQ233/textos-dev/blob/75ebadf4134f6144ed1ffc0b1d3229582766db4f/src/kernel/Makefile)采用C11、freestanding、nostdlib，独立生成kernel.elf。
- [内核入口](https://github.com/ljQAQ233/textos-dev/blob/75ebadf4134f6144ed1ffc0b1d3229582766db4f/src/kernel/main.c)初始化中断、ACPI/APIC、内存、任务及设备。
- [调度](https://github.com/ljQAQ233/textos-dev/blob/75ebadf4134f6144ed1ffc0b1d3229582766db4f/src/kernel/task.c#L426-L533)可见任务表扫描、时间片、CR3/TSS与上下文切换。
- [物理内存](https://github.com/ljQAQ233/textos-dev/blob/75ebadf4134f6144ed1ffc0b1d3229582766db4f/src/kernel/mm/pmm.c)包含空闲区链表、连续页分配和释放。
- 文件系统有VFS、FAT32、Minix、procfs和tmpfs构建路径；E1000源码含收发描述符、PCI/MMIO与LAI路由。
- 用户态入口加载/bin/init；README的Linux包装层与兼容声明按作者说明记录。

这些事实支持“具有自身内核工程”的项目定位。全体代码的原创范围、各参考项目的实际继承关系、完整功能正确性继续待核实。

### 上游、许可与AI参与

根LICENSE为MIT。LAI内附MIT许可。用户态dlmalloc文件明确来自Doug Lea的2.8.6，采用MIT-0，列出删改配置及作者／DeepSeek参与。

固定.gitmodules与完整源码树的gitlink如下：
- EDK2：ljQAQ233/edk2，32911e358735498f0e883e83e725af5f0b240f73
- LVGL：lvgl/lvgl，fd24f98254f2fdcd27180e9885ed4b6b956817c3
- OpenLibm：JuliaMath/openlibm，73f7c01c83bfaec60eea85bf686dfaa5126f4e12
- Lua：lua/lua，a5522f06d2679b8f18534fd6a9968f7eb539dc31

README和作者专栏将EDK2说明为vUDK2018路线，专栏记述罗冰来源。各子模块精确版本与完整许可清单仍待核实。
README列lyos、ToaruOS、LunaixOS、Onix及UEFI项目为参考；history.md记录2024-06-16的内核风格调整。书写风格、参考关系与实际代码继承分别判断。

### 仓库与版本历史

textos-dev创建于2023-05-01T14:53:11Z；textos-pre创建于2023-07-02T01:28:38Z，当前归档。作者说明二者为同一项目的同步与开发阶段。2025-08-03的README回顾说明将开发集中到textos-dev。

[buildable-20261001](https://github.com/ljQAQ233/textos-dev/releases/tag/buildable-20261001)发布于2026-10-01T13:58:46Z，附root.tar.gz；tag引用与核验提交一致。
[kit-202604](https://github.com/ljQAQ233/textos-dev/releases/tag/kit-202604)发布于2026-04-26T05:56:05Z，附image.img.gz。
发布元数据、附件存在与独立运行分别记录。

### 原作者视频

- [BV1mtFke9EGg](https://www.bilibili.com/video/BV1mtFke9EGg/)，2025-02-02，作者Maouai233，09:08。标题为APIC下PCI中断与LAI解析；原简介说明使用LAI取得ACPI路由。
- [BV1Nw4m1d7Lm](https://www.bilibili.com/video/BV1Nw4m1d7Lm/)，作者频道标2024-03-23，20:29，Protocol开发记录。
- [BV1Ma4y1g7Z8](https://www.bilibili.com/video/BV1Ma4y1g7Z8/)，频道标2023-05-20，08:18。专栏关联此早期工作区视频。最早公开日继续待核实。

本轮已核对作者发布页与入口关系。原片播放器后续DOM与截图连续超时，可靠功能画面时间点继续待核实。频道显示的2026年ELF系列视频属于同作者教程，其与TextOS当前内核运行的对应关系继续待核实。

## 未定名AI Rust操作系统（编剧笨笨）

- [原片BV1Thh264EtM](https://www.bilibili.com/video/BV1Thh264EtM/)，2026-09-25，01:19；发布者编剧笨笨，UID595021134。
- [更新BV1oZap6CE8X](https://www.bilibili.com/video/BV1oZap6CE8X/)，2026-09-29，01:24。
- 同作者推荐位给出[扫雷应用BV1hwYA65EqL](https://www.bilibili.com/video/BV1hwYA65EqL/)，03:12；该原片具体日期与画面待核实。

原片有“国产”标签并自述中国AI开发的Rust操作系统。9月29日简介记述矢量字体／图标、GUI资源占用与脏区调整、bootloader硬件识别、24小时空载测试。这些属于作者声明。“第一个”“高性能”“全功能”等宣传范围留待证明，条目采用中性名称和可定位事实。

播放器00:13截图显示黑色区域；该观察仅用于说明本轮画面证据范围。可靠功能画面、正式项目名、源码、架构、上游及内核边界、许可和独立运行继续待核实。新pending计数1组。

## 范围与限制

研究采用普通公开网页、GitHub只读文件／元数据和公开网页浏览器。独立运行与构建均为待核实。
GitHub tags集合端点在连接器返回“不支持的公开端点”；随后使用已知buildable-20261001的git/ref端点成功验证指向。发布集合成功读取。
B站普通网页抓取部分失败；公开网页浏览器取得检索结果、作者主页、原片元数据与项目专栏。部分视频页面随后发生DOMSnapshot、Page.getLayoutMetrics与Emulation.setFocusEmulationEnabled超时；浏览器状态仍存在，视频画面证据按实际取得范围记录。

