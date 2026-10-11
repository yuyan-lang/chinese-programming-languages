# 第16轮内核普查：hudos／hodos
检索日：2026-10-10。基线：yuyan-lang/chinese-programming-languages@93815086f1778802ea57ddeeec8ad717e355814f。

## 本轮结果与精确计数
- 读取固定研究规范、内核目录及第15轮内核日志；读取本轮全部26个开放Issues及69条评论。
- 基线86种语言、9项内核保持不变。
- 深入新候选1项：hudos／hodos（双子星观测站）；旧线索实质补源0项；正式新增0项；新增待核候选1项。
- 候选证据目录38条原始来源，编号hd1至hd38，各URL独立。来源计数以独立原始URL为准。
- 当前固定树27个对象，其中26个文件、1个目录，truncated=false。读取当前树中的17个不同源码／说明文件；另读api6.0 README一个历史文件。固定文件来源为hd9—hd24共16条及hd38一条。
- 3个分支、2个标签、2个Release；沿当前默认分支读取14个保留提交。Release资产合计3个，仅核对元数据。
- 研究采用公开网页、GitHub与Chrome静态阅读。安装、构建、执行、测试和镜像内容均列入待核范围。

## 排重与选择
固定目录9项为DragonOS、xbook2、LuminaOS、CoolPotOS、Uinxed-Kernel、OpenXJ380、NeoAetherOS／na-kernel、TextOS、HOS（HuangCheng72）。第15轮HanOS已有45源，保持原待核定位。开放议题及既有日志中的CoreZ、lgc、Halo、Verge、KunOS、Owl等已知线索均作为排重依据。
本轮关键词覆盖“自制操作系统”“手搓操作系统”“手搓内核”“AI操作系统”，年份聚焦2024—2026；GitHub另查2024-01-01至2026-10-10创建的中文自制OS项目，取首批50结果作为发现索引。JanSky520/MikuOS、OmegeUOS、YiYiYa和HelixOS按筛选线索记录。
hudos／hodos、xuchenruisz、双子星观测站在当前9项内核、26开放Issues及69评论，以及前轮内核日志／待核资料中的既有记录匹配数为0。该项按真正新发现计1。

## 原作者与源码链
B站账号双子星观测站（UID514146062）的2026年10月2日原片BV1wiaU6REGn简介直接列出github.com/xuchenruisz/hudos和chat.hudos.cn。固定README署名双子星观测站（Gemini Observatory）；论坛公开公告再次列出同仓库。该链支持原作者发布账号与仓库归属。
9月21日开源公告原片为BV1pthB64E37。合集共22项，包含hudos、hudos-server、伪系统、Python、图形、AI及7zip演示等不同阶段。早期hudos与hudos-server展示原片为BV1xehc6oENs。
中文视频、中文说明与中文项目社区已确认。作者明确中国归属、项目由中国社区发起或维护的自述继续待核实；账号拼写、中文内容、域名和节日祝福按原信息记录。自然人身份及成员分工继续待核实。视频来源采用BV编号与作品主题识别。

## 固定版本与时间
当前默认分支为内核6.1，固定SHA b4a244b808b6786d5c3a1fd98102055f7f582488，提交时间2026-10-06T23:21:49Z。仓库API pushed_at为2026-10-06T23:21:50Z。main另为cc37a6e8274d4a9eb1980307299a5b1a380874d2，api6.0另为67016fa07953af3f48bea02d10330c267c20bdd4；三阶段分别保留。
仓库创建于2026-09-14T10:38:39Z；根提交cd2b6488f5b30aad8ca546fac01934f004ab7502于同日10:40:57Z，仅README。紧接的184eaebe697741ef4f25fcbda9eb16c282750a3c含README及hudos-server1beta1_副本.zip，后者1,202,076字节，只读树元数据。
标签1对应adb0112527ce90244ff4904aaaeba6a25d7fa9d5，正式Release V26.10.1.16于2026-10-02T04:11:28Z发布，hudos_.qcow2.zip为11,036,853字节。标签2对应f632bf79977431300b2ede953636f48e8be723ec，预发布hudos v26.10.4.20于2026-10-05T00:53:38Z发布，hudos_server.qcow2.zip为11,102,819字节，HudosForum.ipa.zip为378,283字节。后者是论坛iOS客户端资产。
主程序横幅hudos-server0.1、分支内核6.1和Release26.10.x各按原字段记录。
B站初始页面与客户端时间存在时区显示差异：10月2日原片分别见21:00与06:00；早期视频初始页为8月27日08:29:31，合集为8月26日。规范时间戳与首次公开日待平台原始时间核实。

## 内核边界与实现证据
当前Makefile构建BOOTAA64.EFI，目标aarch64-pc-win32-coff，入口efi_main，subsystem:EFI_APPLICATION，machine:arm64。clang、lld-link及freestanding、nodefaultlib等配置可读。efi_main持有固件系统表及Boot Services，完成图形、输入、磁盘、根文件系统初始化后尝试gui.elf／tdesktop.elf并进入shell。
UEFI Boot Services继续参与页面与缓冲区分配、文件、设备与等待服务。mmu.c的初始化函数按当前实现保留固件MMU及向量基础。hudos_server.c包含新版EL0窗口运行、临时VBAR交接、SVC处理和异常返回，需连同主文件阅读。
g_el0_enable默认1，启动自检失败时回到EL1；g_el0_phaseb默认0，自身页表克隆及ASID路径按开关控制。直接exec、协程子程序与cmd_open拥有各自入口及回退路径。当前按“UEFI固件承载的实验系统，自身内核独立性待核”保存。
ELF装载器检查64位小端、AArch64、ET_EXEC／ET_DYN，支持部分重定位。父子协程保存寄存器与栈，输入和图形提交处可让出执行；单组上下文及输入队列可见。抢占式多进程、隔离完整性待核。部分Linux AArch64系统调用编号可见，getpid返回1、getuid／geteuid返回0、brk返回常数；完整ABI覆盖待核。
文件层使用EFI_FILE_PROTOCOL／SimpleFileSystem，限额含8卷、8挂载点、8磁盘、32文件句柄槽；格式化和分区写入接口可见。后续授权运行需使用可恢复测试盘。
GOP帧缓冲、Blt影子缓冲、绝对指针、键盘扩展、UTF-8中文字体及HDA音频代码可见。当前userland目录只有2个字体头文件；完整桌面／应用对应源文件和构建链待补。
主实现包含virtio-mmio、ARP、IPv4、UDP、DHCP、DNS、TCP、HTTP与HTTPS调用链。TLS1.2与0xCCA8握手、证书签名链解析实现可读；主机名、有效期、约束及整体安全性继续待核。随机数代码包含时间与状态播种的ChaCha20 DRBG，作者注释定位演示用途。对实现的读取保留源码可见层级。
2026年10月4日修复提交37da3bd68997d6c9f11f3fce44b9dc401e093afa修改主文件+85/-8，包含控制台缓冲容量和ELF偏移／大小检查。作者Release称修复两个高危bug；独立审计和修复完备性待核。

## 许可、AI与上游
README自述GPLv2-or-later，署名2026双子星观测站。当前树的完整许可证文件待补。GitHub API license字段为空。代码、镜像和所有捆绑资源的整体授权范围待核。
sun8x16.h注释列Linux kernel字体；cjk16x16.h说明从系统STHeiti经gen_cjk_font.py／extend_cjk.py生成位图。精确字体版本、脚本和再分发许可继续待补。common.h提到四游戏框架的hudos移植及games_adapter.c，对应框架原源、适配文件与许可继续待补。tls_roots.h列系统信任库来源；tls_cli.c列RFC5246、7905、8439作为实现文档。
hudos开发合集含AI功能演示；chat.hudos.cn页面标题为Qwen-Coder Chat，论坛公告称AI聊天上线。作者新开“用AI做一个纯汇编操作系统”系列并展示WorkBuddy准备篇。该独立系列与当前C／AArch64 hudos仓的关系待核；AI编码参与程度、模型和具体生成内容继续待核。

## 演示与访问记录
视频标题、简介、账号、合集及页面结构可读。原片时长分别包括2:31、2:39、早期3:17。播放器截图、DOMSnapshot或后续CDP交互多次超时，本轮缺少稳定逐帧图像和可重现时间戳。作者演示页面成立，画面内具体启动及操作结果保持待核。
使用Chrome浏览公开B站页面与官方论坛。论坛公告支持公开阅读。游客入口显示社区／隐私协议，研究读取范围为公开页面。论坛10月3日公告指向当前仓，10月1日公告中的尾连字符旧仓地址作为关系待核线索保存。
当前固定源码可读、发布镜像存在及作者演示索引分别列证据层。独立运行、复现、实机覆盖、安全性和性能均继续待核。

## 下一步证据门槛
1. 原作者或项目公开材料明确中国作者／中国社区归属。
2. 各演示对应的固定源码、桌面应用和完整构建输入；hudos与早期伪系统阶段对应。
3. 固件依赖、自身页表及中断控制的实际边界，独立内核分类依据。
4. GPL完整文本、字体及游戏框架等第三方资源来源和许可。
5. AI编程参与声明与作品内AI功能分别补证。
以上证据补齐前保持待核候选1项，正式内核目录仍为9项。


## 一手来源目录
hd1. 开源公告原片：https://www.bilibili.com/video/BV1pthB64E37/
   类型：原作者视频页面。支撑：9月21日开源标题、发布账号和合集。
hd2. 最新开源原片：https://www.bilibili.com/video/BV1wiaU6REGn/
   类型：原作者视频页面。支撑：视频简介直接连接原仓与官方论坛；两种显示时刻。
hd3. 发布者B站主页：https://space.bilibili.com/514146062
   类型：原作者公开主页。支撑：作者名称；hudos系列与另一个WorkBuddy纯汇编系列。
hd4. 原作者开发日志合集：https://space.bilibili.com/514146062/lists/9078226?type=season
   类型：原作者视频目录。支撑：22项公开视频；早期hudos与hudos-server、伪系统和AI功能标题。
hd5. GitHub作者主页：https://github.com/xuchenruisz
   类型：原作者公开主页。支撑：维护账号与公开仓库。
hd6. 仓库元数据：https://api.github.com/repos/xuchenruisz/hudos
   类型：平台元数据。支撑：创建时间、默认分支、13星、fork=false、许可元数据null。
hd7. 固定头提交：https://github.com/xuchenruisz/hudos/commit/b4a244b808b6786d5c3a1fd98102055f7f582488
   类型：固定提交元数据。支撑：2026-10-06T23:21:49Z。
hd8. 固定完整源码树：https://api.github.com/repos/xuchenruisz/hudos/git/trees/b4a244b808b6786d5c3a1fd98102055f7f582488?recursive=1
   类型：固定源码树。支撑：27项、26文件、1目录、truncated=false。
hd9. 固定README及许可声明：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/README.md
   类型：固定作者文档。支撑：hodos拼写、双子星观测站署名、GPL-2.0-or-later简短声明。
hd10. ARM64 EFI构建：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/Makefile
   类型：固定源码。支撑：aarch64-pc-win32-coff与EFI_APPLICATION构建目标。
hd11. UEFI协议类型：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/efi.h
   类型：固定源码。支撑：自包含UEFI接口定义。
hd12. 系统主实现：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/hudos_server.c
   类型：固定源码。支撑：固件服务、ELF装载、EL0、协程、文件、网络、音频与源码横幅版本。
hd13. 早期MMU阶段实现：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/mmu.c
   类型：固定源码。支撑：hudos_mmu_init为空操作；解释固件向量与持续Boot Services。
hd14. AArch64异常与EL0汇编：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/mmu_asm.S
   类型：固定源码。支撑：异常向量、eret与EL0上下文。
hd15. 用户程序启动：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/crt0.S
   类型：固定源码。支撑：EL1函数指针与EL0 SVC两种调用路径。
hd16. 用户调用包装：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/syscall.c
   类型：固定源码。支撑：双路径调用、文件与图形API。
hd17. 用户调用声明：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/syscall.h
   类型：固定源码。支撑：编号与接口定义。
hd18. 游戏接口声明：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/common.h
   类型：固定源码。支撑：四游戏框架移植声明；原项目来源待核。
hd19. TLS原语声明：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/tls.h
   类型：固定源码。支撑：SHA256、ChaCha20、Poly1305与P256接口。
hd20. TLS1.2握手：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/tls_handshake.c
   类型：固定源码。支撑：0xCCA8握手与证书链签名核验路径。
hd21. X.509解析与签名核验：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/x509.c
   类型：固定源码。支撑：DER、RSA-SHA256和信任锚签名链。
hd22. 证书信任锚头注：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/tls_roots.h
   类型：固定源码头部。支撑：从系统信任库提取的根证书。
hd23. ASCII字体来源头注：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/userland/sun8x16.h
   类型：固定源码头部。支撑：署明Linux kernel sun8x16来源。
hd24. 中文字体来源头注：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/userland/cjk16x16.h
   类型：固定源码头部。支撑：STHeiti生成32×32位图字体。
hd25. 分支集合：https://api.github.com/repos/xuchenruisz/hudos/branches?per_page=100
   类型：平台元数据。支撑：main、api6.0、内核6.1共3分支。
hd26. 标签引用集合：https://api.github.com/repos/xuchenruisz/hudos/git/matching-refs/tags/
   类型：平台元数据。支撑：标签1和2精确提交。
hd27. 发布集合：https://api.github.com/repos/xuchenruisz/hudos/releases?per_page=100
   类型：原作者发布及平台元数据。支撑：正式V26.10.1.16与预发布v26.10.4.20；3个附件。
hd28. 当前分支全部可见提交：https://api.github.com/repos/xuchenruisz/hudos/commits?per_page=100
   类型：固定历史元数据。支撑：14项线性历史、无父根提交。
hd29. 初始提交源码树：https://api.github.com/repos/xuchenruisz/hudos/git/trees/cd2b6488f5b30aad8ca546fac01934f004ab7502?recursive=1
   类型：固定历史源码树。支撑：初始README单文件。
hd30. 首个上传提交树：https://api.github.com/repos/xuchenruisz/hudos/git/trees/184eaebe697741ef4f25fcbda9eb16c282750a3c?recursive=1
   类型：固定历史源码树。支撑：README与hudos-server1beta1压缩包。
hd31. main分支固定树：https://api.github.com/repos/xuchenruisz/hudos/git/trees/cc37a6e8274d4a9eb1980307299a5b1a380874d2?recursive=1
   类型：固定源码树。支撑：19项文件；与当前分支区分。
hd32. api6.0分支固定树：https://api.github.com/repos/xuchenruisz/hudos/git/trees/67016fa07953af3f48bea02d10330c267c20bdd4?recursive=1
   类型：固定源码树。支撑：24项文件。
hd33. api6.0 README：https://github.com/xuchenruisz/hudos/blob/67016fa07953af3f48bea02d10330c267c20bdd4/README.md
   类型：固定作者文档。支撑：内核全面更新说明。
hd34. 10月4日修复差异：https://github.com/xuchenruisz/hudos/commit/37da3bd68997d6c9f11f3fce44b9dc401e093afa
   类型：固定提交差异。支撑：控制台容量检查及ELF范围检查改动。
hd35. 项目论坛公开公告：https://chat.hudos.cn/forum
   类型：原项目社区页面。支撑：管理员公告连接同一原仓；公开公告可读，正文入口要求同意条款。
hd36. 项目AI聊天入口：https://chat.hudos.cn/
   类型：原项目页面。支撑：Qwen-Coder Chat标题；密码入口与论坛导航。
hd37. 早期hudos和hudos-server原片：https://www.bilibili.com/video/BV1xehc6oENs/
   类型：原作者视频页面。支撑：项目并列命名、8月日期显示与合集差异。
hd38. TLS客户端说明：https://github.com/xuchenruisz/hudos/blob/b4a244b808b6786d5c3a1fd98102055f7f582488/tls_cli.c
   类型：固定源码头部。支撑：RFC5246、7905、8439参考声明。

