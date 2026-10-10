# 中文编程语言百科第二轮仓库研究交付

日期：2026-10-10（UTC）。
范围：Issue 3 的 CP语言、coCN、Atlanage 三项；附加一次定向检索，新发现 LingCpp（LingBuilder）。
建议条目：round2-new-repos.json，4个对象，无id。已沿用现有data/languages.json字段；合并时将pushed_at统一为repository_pushed_at、verified_at统一为日期，未另增字段。
来源优先级：原始仓库源码/官方发布元数据 > 作者文档 > 发现索引。所有源码链接固定commit；元数据/API为核验当日快照。
全过程没有执行陌生仓库代码、安装、编译、运行测试、修改远端文件或创建编码任务；未研究豫言。

## 汇总结论

- CP语言：可收录，中文词法/语法/VM源码已核验。仓库简介“恋语”作别名。同仓库README的LLVM原生AOT宣传滞后于当前CLI/CMake；当前build是字节码+runner封装。版本0.9.3/0.9.0/0.3.0并列，GitHub Releases为空。
- coCN：可收录为实验中文语言。当前.co自解释器借旧C二进制引导；不能称完整独立自举已复现。当前并发为单线程延迟任务，类型标注存在但无已核验的强制检查；编译器依赖的C运行时模板当前树缺失。
- Atlanage：可收录为有公开源码的中文编译语言。.at词法、解析、语义、代码生成、汇编、链接模块实际存在。C种子文件是预编译二进制物化器；不等于源码引导。Release标签1.0、正文1.0.1冲突，作者署名身份待核实。
- LingCpp（LingBuilder）：目录与Issue3/4/5之外的新发现。中文.lcpp语法、TypeScript parser与C++/Win32工程生成实现核实；按语言与IDE关系合并一项，不把AI辅助编辑当编译机制。

## 固定快照及原文定位

| 项目 | commit | 原文短代码 |
| --- | --- | --- |
| CP语言 | 9bd435707f280cca615a09deabdb6976d361d511 | examples/cp_demos/05_function.cp L6–11 |
| coCN | c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07 | 例子/自举函数示例.co L33–42 |
| Atlanage | da5b3a9b778ff546382990de35f2112efc9544f9 | examples/hello.at L8–11 |
| LingCpp | 2513be26b318457df8314c7a0923fd5667de09bd | cloud/admin/docs/guide/user/lingcpp-quickstart.md L16–20 |

四项原始短代码均为单一来源的连续原文，保留原始缩进/标点，没有自制示例。本轮再次按固定commit抽查coCN和Atlanage行段，并检查CP/LingCpp摘录为已读全文子串。

## Issue 3 可发布的合并进度草稿（尚未发布）

2026-10-10 第二轮只读核查已补齐3项：

1. CP语言（9bd4357）：已确认中文关键字表、解析器、字节码VM及JIT源码，并提取独立样例中的连续阶乘函数。“恋语”为同仓库简介用名，按别名合并。版本标注不同步；README的原生AOT宣传与当前CLI/CMake不一致，当前build分支为字节码+runner封装，不把95x性能或原生AOT可用性视为验证结果。
2. coCN（c641a58）：已确认.co词法、parser、求值器及原文示例。当前自解释器仍依赖历史C宿主引导；保留的生成C编译器依赖缺失模板，旧自举脚本路径未同步。当前并发为单线程延迟执行；类型标注语法存在，但强制检查与完整自举未验证。包清单0.0.2、README/Release 0.0.1、引导0.1.0分别记录。
3. Atlanage（da5b3a9）：已确认中文词法/解析以及.at编译模块和连续原文示例。首个可核实GitHub Release为2026-08-16，标签1.0与正文1.0.1不同；种子C程序只解码既有二进制，不证明从C源码引导。自举、M:N调度与性能不标为已验证。

三项均可按“有公开源码，未运行验证”整理正式条目；仓库创建、历史提交与发布日已分开。各项目首次公开日期仍存在待核项。本轮没有执行项目代码，Issue 3其余线索尚未完成，请保留议题开放。

额外发现建议另列：LingCpp（LingBuilder）不在现有34项或Issue3/4/5；已取得官方中文语法、解析器与C++工程生成源码，按中文C++转译语言收录，IDE与语言不重复计数。

## 交付校验与补充
- JSON为UTF-8数组、4个对象、无id；字段均在当前34项已有字段集合内。
- CP的git/refs/tags进一步读取返回404；这不足以对其他托管源或历史标签作全局断言，不影响Releases空数组事实。
- 不将未成功读取、工具过大限制或404等同项目不存在；详见各项目查询日志。


# 第二轮仓库核验：CP语言
核验日期：2026-10-10。只读查询；没有下载执行、安装、编译、测试、触发CI或修改远端。条目对象见 round2-cp.json。

## 结论
可收录。中文关键字不是仅中文标识符：token.hpp 映射“函数/返回/如果/当/变量”等Token，lexer.cpp调用KeywordTable，parser分别构造函数、条件和循环AST。许可证署名小白白。仓库简介“恋语”与README的CP语言是同一个仓库，保留别名，不新增一门。

## 固定快照
https://github.com/mycplang/cplang/tree/9bd435707f280cca615a09deabdb6976d361d511
默认分支master。提交时间2026-06-29T18:17:23Z。仓库创建2026-05-10T13:46:56Z；最后推送2026-06-29T18:17:27Z；非fork、未归档。
读取 commits?per_page=100 得97项；唯一无父提交6646423655b7b62bc33036e3e9219f6fd6cd1c7d日期2026-05-28T16:45:06Z，不能推导首次公开时间。
https://github.com/mycplang/cplang/commit/6646423655b7b62bc33036e3e9219f6fd6cd1c7d

## 原始中文代码
https://github.com/mycplang/cplang/blob/9bd435707f280cca615a09deabdb6976d361d511/examples/cp_demos/05_function.cp#L6-L11
连续阶乘函数定义共6行；对象逐字保留空格/标点。不是完整程序，未执行。
不用README的斐波那契片段：其定义“斐波那契”与后续“斐那契”调用不一致，不能替作者静默改正再声称原文。

## 需要保留的边界
- CLI标v0.9.3；VERSION=v0.3.0；CMake=0.9.0；docs/RELEASE=v0.5.0；tools/version.json=CP IDE 2.4.1且compiler_version=0.1.0。只能据来源逐项描述。
- Releases集合为空；tags端点被当前工具拒绝为不支持，不等同无tags。
- README仍称-a产出原生AOT；当前main.cpp无-a分派，CMake没有AOT目标。src/codegen/aot_compiler.cpp还保留LLVM IR/llc旧实现；src/aot/aot_compiler.cpp是compileFile/compileSource返回false的占位。
- 当前main.cpp第538–606行的build分支是字节码封装到runner；并非把用户程序全部编译为原生机器码。docs/RELEASE.md亦明确v0.5.0移除AOT改SFX。历史commit可解释为何宣传与当前入口不一致；不宣称当前原生AOT可用。
- LLVM ORC JIT源码实有LLJITBuilder/addIRModule/lookup，CMake有条件开关；未独立证明它能构建或有95x性能。
- 没有逐项确认标准库功能数、零依赖、自举、内存安全或跨平台可用性。未将README旧测试数写成当前复测。

## 查询日志
1. 读取目标目录data/languages.json（34项）和Issue3（19条待核线索，0评论），按名称/别名查重。
2. get_repo及GitHub REST仓库元数据、branches、releases；取默认commit。
3. 递归Git树4044项，truncated=false；只筛自有src/include/examples/docs，未把third_party的C语言体积误判为编译器实现语言。
4. 固定commit读取README.md、LICENSE、VERSION、CMakeLists.txt、tools/version.json、docs/PROJECT_STATUS.md、docs/RELEASE.md、examples/cp_demos/05_function.cp、examples/tutorial/06_functions.cp。
5. 固定commit读取src/lexer/lexer.cpp、include/lexer/token.hpp、src/parser/parser_decl.cpp、src/parser/parser_stmt.cpp、src/codegen/codegen.cpp、src/jit/orc_jit.cpp、src/vm/vm_exec.cpp、src/main.cpp、src/codegen/aot_compiler.cpp、src/aot/aot_compiler.cpp、src/codegen/aot_stub.cpp。
6. 读取commits集合；PROFILE.md在当前快照404，未据历史提交标题编造当前文件。
7. 未研究豫言条目或实现。

## Issue3可发布进度文案
CP语言已补齐源码与连续中文示例证据，快照9bd4357，可从“待核线索”提升为“有源码，未运行验证”。同仓库简介另用“恋语”，应作别名合并。版本字段存在v0.9.3/v0.9.0/v0.3.0差异。README的LLVM原生AOT宣传与当前CLI/CMake不一致；当前build分支为字节码+runner封装，因此本次只确认字节码VM及JIT源码，不认定95x性能、原生AOT或自举已验证。首发仍待核实，仓库创建与根提交日期分别保留。Issue3其余项目尚未全核，不应关闭。
# coCN 只读核查日志

核查时间：2026-10-10 12:08–12:12 UTC。对象：https://github.com/3477856804/coCN
范围：读取公开仓库/API、源码和官方发行元数据；不执行源码，不安装 npm 包，不创建编码任务，不修改远端。

## 结论

可作为中文关键字通用语言的实验性项目收录，但应明确“当前 .co 自解释器仍由历史 C 宿主引导”。当前源码支持真实中文语法，而完整自举、真线程、强制类型检查及性能不能从 README 宣传直接认定。保留的生成 C 编译器依赖本次固定树中不存在的运行时模板。

## 固定快照与日期

- 默认分支：master
- 固定 commit：c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07
- 提交作者署名：COSMOnb666；提交时间 2026-10-08T08:13:13Z
- 完整树：004f0558a545e9e15a79474df6fc45efc8a2b5ac，recursive tree 返回 truncated=false
- GitHub repository.created_at：2026-09-12T15:24:29Z
- repository.pushed_at：2026-10-08T08:58:22Z；未归档
- master 历史返回 63 个提交，包含无父提交的根 bbb29bf8db7f6d0e3fee3ef441267145dadc1451；其 author/committer 时间均为 2026-07-24T08:33:28Z，署名 cosmo。此为历史提交时间，不是公开发表证据。
- GitHub Release 仅返回 v0.0.1：published_at 2026-09-12T15:25:15Z；created_at 2026-09-12T15:18:20Z 是 Release/标签所关联提交时间字段，不当作仓库创建或公开时间。
- annotated tag v0.0.1：500f26f3a4cd51c1d2f8d6ef311a7876e25cb558，解引用 commit 9483dd20a4c1b45ced40f5ed0a2a662dde6bdc18。
- Gitee 首次公开时间、整个语言首发日期仍未确认。条目使用“最早可核实 GitHub Release 日期”的限定表述。

日期源：
https://api.github.com/repos/3477856804/coCN
https://api.github.com/repos/3477856804/coCN/branches/master
https://api.github.com/repos/3477856804/coCN/releases?per_page=100
https://api.github.com/repos/3477856804/coCN/git/tags/500f26f3a4cd51c1d2f8d6ef311a7876e25cb558
https://github.com/3477856804/coCN/commit/bbb29bf8db7f6d0e3fee3ef441267145dadc1451

## 中文语法与实现证据

1. src/词法分析器.co L32–36 为实际关键字判定表，识别让、函数、返回、若、如果、当、对于、从、到、循环、结束等中文词；L40 起为实际扫描器。
   https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/词法分析器.co#L32-L40
2. src/语法分析器.co 为递归下降 parser；L482–505 解析变量与类型标注，L664–719 解析函数；L873–889 由 token 到 AST。
   https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/语法分析器.co#L482-L505
   https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/语法分析器.co#L664-L719
3. src/解释器.co L12–31 导入求值器、读取 COCN_TARGET 文件并调用运行；src/求值器.co L1773–1784 解析源、建立环境、遍历语句。
   https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/解释器.co#L12-L31
   https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/求值器.co#L1773-L1784
4. 原文短代码选例子/自举函数示例.co L33–42，共十行，连续摘录；blob 77ffa49b05a6aab4cd7e1cc11425d648ecb3b130。未拼接、补写或执行。
   https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/%E4%BE%8B%E5%AD%90/%E8%87%AA%E4%B8%BE%E5%87%BD%E6%95%B0%E7%A4%BA%E4%BE%8B.co#L33-L42

## 引导链与宣传边界

- bin/cocn.js L67–78 将用户路径写入 COCN_TARGET，再 spawn 引导二进制执行 src/解释器.co，cwd 切到 src。它不是独立的 JS 解释器。
- install.js L20–32 指定包版本 0.0.2、引导版本 0.1.0，下载源为 Gitee 然后 GitHub。L153–168 可先使用包内二进制，但当前 Git tree 并不含 bin/cocn，不能推断 npm tarball 也不含。
- src/求值器.co L101–105 说明并实际通过调用内置复用宿主原生函数；这不是完全消除宿主运行时的实现。
- 历史 commit f930c811e161f508fa7c6d61b26f2998e623a168 中有 co.c、Makefile、自举运行时.c。co.c L3 自称 0.1.0；L7047–7088 为生成 C 并调用 cc；L7211–7226 为 parse_program 后执行 AST 语句。历史 C 实现确实存在，不只是 README 中提到。
- 当前编译器/自举编译器.co L1013–1017 强制检查并读取自举运行时.c，L1054–1055 写 C 并运行 cc。完整当前树没有任何 .c 文件、Makefile 或 bin/cocn。
- 当前测试/自举.sh L6–12、测试/自举L2.sh L5–12 仍默认 ./co 和根目录自举编译器.co；实际编译器已移至编译器/，示例移至例子/。本次没有运行或修复这些脚本。
- 当前求值器 L1375–1386 只创建任务字典/等待任务，L2497–2554 明示并实现单线程延迟执行；L604–620 顺序等待且让出为空操作。不要标注为已验证的 pthread 真线程。
- 当前 parser 保存类型标注，但整个 evaluator 未出现“类型标注/参数类型/返回类型”字段读取；L1444–1463 声明变量、构造函数直接丢弃标注，L1065–1078 参数绑定也不检查类型。因此只列“类型标注语法”，不列“静态类型或强制运行时检查已验证”。
- 性能、完整自举、全部语言特性一致性及自动求导运行效果均未实测，未认定为验证成功。

关键源码：
https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/bin/cocn.js#L67-L78
https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/install.js#L20-L32
https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/编译器/自举编译器.co#L1013-L1055
https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/求值器.co#L1444-L1463
https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/求值器.co#L2497-L2554
https://github.com/3477856804/coCN/blob/f930c811e161f508fa7c6d61b26f2998e623a168/co.c#L7047-L7088

## 作者、版本、分类与关系

- 作者依据：当前 package.json L37 为 COSMOnb666；GitHub 仓库 owner 为 3477856804。仅记录公开署名，不推断实名，也不把根提交 cosmo 自动合并成已认证身份。
- package.json/index.js/install.js：0.0.2；README：0.0.1；GitHub Release：v0.0.1；引导 C 版本：0.1.0。这些是不同层次/时期的版本，分开记录。
- GitHub 的 releases/tags/v0.1.0 返回 404；不能因此断言 Gitee 对应发布或 npm 内嵌二进制不存在。
- package.json L39–45 将 Gitee 同名仓库列为首页/repository/bugs。语言与 C 为实现/引导/编译目标关系，Node.js 为启动安装层；未证实派生自 Python 或其他中文语言。
- 仓库语言统计显示 Shell，不能据此把语言归类为 Shell 方言。
- 包清单声明 Apache-2.0；完整当前树未见 LICENSE。此处不推断许可证是否合法完整。
- aliases 留空；cocn/co 是 package.json 中的 CLI 名，未将它们强行认定为独立语言别名。

## 查询日志

1. GitHub connector 读取仓库元数据、默认分支 master、完整 recursive tree、全部当前可达提交（per_page=100 返回 63）、Releases（返回 1 条）。
2. 固定 master SHA 后读取 README.md、package.json、bin/cocn.js、install.js、index.js、src/解释器.co、src/词法分析器.co、src/语法分析器.co、src/求值器.co、编译器/自举编译器.co、测试/自举.sh、测试/自举L2.sh、两个自举示例、重写规范.md。
3. 读取 v0.0.1 tag ref/tag object、根 commit、历史 f930c811… 的完整树和 co.c/Makefile，分离当前自解释器与历史 C 实现。
4. tags?per_page=100 端点被 connector 的 URL 支持列表拒绝；改用其支持的 git/ref/tags/v0.0.1 和 git/tags/{sha} 读取已知 release 的标签，不调用写接口。
5. GitHub releases/tags/v0.1.0 返回 404；记录 GitHub 未有此 Release，未推广到其他源。
6. 公网读取 GitHub 首页返回 cache miss；Gitee 项目页/releases 无法由网页工具读取；官方 npm package 页 cache miss、registry URL 无法读取。
7. 网页搜索 coCN/COSMOnb666 与 @yeyelailou/cocn，出现 npm.io 的 0.0.3 索引。因无法以 npm 官方注册表核实，不采用该第三方索引作为最终版本结论，也不宣称 GitHub manifest 0.0.2 是 npm 最新版。
8. 所有结论仅基于已读原始文件/官方 GitHub 元数据；没有运行构建、测试、安装脚本或发行二进制。

## Issue 3 可直接发布的短进度草稿（尚未发布）

coCN 已完成只读源码核查，固定到 master 的 c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07。已确认实际中文词法、parser/求值器和连续原文示例；当前为 coCN 自解释器，由旧 C 二进制引导。包清单为 0.0.2，README 和唯一 GitHub Release 仍是 0.0.1；首个可核实 GitHub Release 日期为 2026-09-12，不能用更早的提交时间代替首发。收录会明确自举依赖缺口，并发实际为单线程延迟执行，类型标注的强制检查和性能等宣传暂不列为已验证。
# Atlanage 核实日志

核实日期：2026-10-10（UTC）。只读研究；没有执行仓库源码、安装软件、下载运行发布包、修改远端或创建编码任务。

## 结论

可作为“有中文语法和真实实现源码的中文通用编译语言”候选收录。固定版本为 main 提交 da5b3a9b778ff546382990de35f2112efc9544f9。已核实源码与元数据；自举、调度正确性、性能及完整构建不能标为已验证。

## 关键事实及证据

- 仓库所有者及 Release 发布者为 wc772。标签根提交作者文本为 atra，未找到二者身份关系证据，不将 atra 自动列为 wc772 的别名。
- 仓库创建时间为 2026-08-16T17:28:53Z；目前唯一 Release 的公开发布时间为 2026-08-16T17:58:33Z；仓库创建、提交作者日期与 Release 发布日期分开记录。
- 唯一标签 1.0 指向 837af6b15ca64ee2fc1b157d7bc15fc0818948a0，为父提交列表为空的根提交，提交日期 2026-08-16T17:50:33Z，署名 atra。
- 当前 main 只有两个可达提交：根提交 6bda6cec0b860c0456280c797d417f5360ab4fb5（Initial release，2026-08-16T18:05:23Z，署名 wc772），随后 da5b3a9b778ff546382990de35f2112efc9544f9（Fix dead references and remove empty file，2026-08-17T09:21:10Z）。因此不能混淆标签历史与当前主线历史。
- GitHub Release tag=1.0、name=qwq、body=1.0.1、prerelease=false。资产 atlanage-v1.0.zip 于 2026-08-17T09:23:02Z 创建，不是 Release 原始发布时间。未检查 ZIP 内部版本。
- 仓库 pushed_at=2026-08-17T09:21:36Z，archived=false，disabled=false，fork=false，license=null。完整递归树 322 项、truncated=false；未见 LICENSE 文件或已跟踪 .exe/.obj/.dll。应称“公开源码”，避免自动标为“已核实开源许可证”。
- 中文关键字证据：[atl_lexer.at 第126–200行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_lexer.at#L126-L200)；中文标识符字符范围：[第226–238行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_lexer.at#L226-L238)。
- 解析证据：[atl_parser.at 第967–1015行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_parser.at#L967-L1015)。这不是只有 README 中文文案或中文注释的仓库。
- 入口 [atlv1.at 第1–8行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atlv1.at#L1-L8) 导入 .at 模块；[第907–950行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atlv1.at#L907-L950) 实际串联词法、解析、语义、代码生成、汇编、COFF 与链接。链接器第1–5行定义 MACHINE_AMD64=0x8664。
- 实现结构还包括 .at 文件中的嵌入汇编运行时 self-hosted/atl_rt.at，以及 runtime/ 下的 C 运行时相关文件；不只依据 GitHub 的 language=C 归类。
- 引导边界：[seed_builder.c 第115–196行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/seed/seed_builder.c#L115-L196) 读取 hex、验证 SHA-256、输出既有二进制；它不是编译 .at 的 C 编译器源码。输出文件名 atlv1.exe 与 rebuild_atlv1.ps1 的 AT-V1.exe 不同。
- 自编译脚本需要已有 AT-V1.exe，构建自身汇编→对象→可执行文件，然后比较新旧编译器对 hello.at 的汇编文本；仅静态核实脚本内容，没有运行或确认一致性。
- rt_build.ps1 需要已有 atlc.exe，另调用 Python 与 NASM win64。默认仓库树未包含 atlc.exe。未核实预编译工具来源或完整从源码引导。
- atl_rt_seed.hex 头部写 generated=2026-08-08，这只是文件内部生成时间自述，不是公开首发证据。
- README 宣称自举、M:N 任务调度、图形/API 支持；源码或示例存在不等于正确性、完整性、性能验证。未新增与其他中文语言的继承/同源关系。

## 代码摘录

来源：[examples/hello.at 第8–11行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/examples/hello.at#L8-L11)
commit：da5b3a9b778ff546382990de35f2112efc9544f9
blob：7884f0f829940f6748eeb2799cf88325cdc92ec9

```text
声明 加法(a, b){
    返回值 a + b;
};
打印("1+2=" + 加法(1, 2));
```

这是同一源文件连续四行；无拼接、翻译或改写。代码未运行。

## 查询日志

1. GitHub fetch GET /repos/wc772/atlanage：成功，取得创建、推送、默认分支、归档、许可证与仓库归属元数据。
2. GET /releases 与 /releases/latest：成功，两者指向同一 1.0 Release；保存 published_at 与版本冲突。
3. GET /contents：成功，观察根目录文件。
4. GET /branches/main：成功，固定 da5b3a9b778ff546382990de35f2112efc9544f9。
5. GET /commits?per_page=100：成功，两个当前主线提交，根提交 parents=[]；没有把提交时间当作公开首发时间。
6. GET /git/trees/main?recursive=1：成功，返回 da5b3a9b778ff546382990de35f2112efc9544f9、322 项、truncated=false；用于文件存在性与缺失项判断。
7. GET /tags：连接器 URL 白名单不支持，返回 INVALID_ARGUMENT；不是仓库无标签。
8. GET /git/ref/tags/1.0 与 /git/refs/tags：成功，唯一标签指向 837af6b15ca64ee2fc1b157d7bc15fc0818948a0。
9. GET /commits/837af6b15ca64ee2fc1b157d7bc15fc0818948a0：成功但 diff 回应很大；随后 GET /git/commits/837af6b15ca64ee2fc1b157d7bc15fc0818948a0 成功，直接取得简洁提交元数据与空父列表。
10. 固定 commit 读取 README.md、文档/介绍.md、examples/hello.at、examples/06_函数.at、atc.sh、rebuild_atlv1.ps1、rt_build.ps1、seed/seed_builder.c、self-hosted/atlv1.at、atl_lexer.at、atl_parser.at、atl_runtime.at：成功。
11. 固定 commit 按行读取 runtime/xt_runtime.c 1–80、runtime/xt_scheduler.h、self-hosted/atl_linker.at 1–65、atl_codegen.at 1–65、atl_rt.at 1–100、examples/hello.at 8–11：成功；短代码被独立按行再次核对。
12. seed/atl_rt_seed.hex 1–7：成功。seed/atlv1_seed.hex 1–7：工具返回空 content（树中大小为 2,181,179 字节），未据此认定文件为空，也未解码或执行。
13. 公开 web 搜索 \"Atlanage\" \"wc772\"：无结果。未找到可证实更早公开日期或独立作者身份的额外资料。

## Issue 3 可直接发布的进度文案

Atlanage 的只读核实已完成：已固定 main 提交 da5b3a9b778ff546382990de35f2112efc9544f9，确认中文关键字、语法解析与 .at 编译器模块，并取用 examples/hello.at 第8–11行的连续原文。首个可核实 GitHub Release 发布于 2026-08-16；标签为 1.0，但发布正文写 1.0.1，已保留版本冲突说明。引导 C 文件仅解码既有二进制种子，构建脚本依赖预存编译器；自举、M:N 调度与性能不标为已验证。此轮没有运行项目代码。

# 新发现：LingCpp（LingBuilder）
核验日期2026-10-10。对象见round2-lingcpp.json。未安装、执行或改远端。

## 发现与去重
先读取现有34条及Issue3/4/5。定向搜索三项：
- “自制编程语言” “中文” “2026”
- “手搓编译器” “中文”
- “全中文代码” “语言” github
结果中的Hanyu-Lang、ikdxhz/chinese-python已在目录或Issue；排除仅中文说明/AI工具/编译器教程。
发现2026-09-13转载“灵码 LingBuilder：用中文写代码，确定性生成真实C++工程（开源）”
https://jishuzhan.net/article/2099029187160625154
转载链接指向原仓库https://github.com/mosheng20205/lingbuilder。转载仅用于发现，未用于证明实现或首发。

## 原始资料读取
- 元数据：创建2026-08-25T05:23:30Z，非fork、未归档；默认main，pushed_at=2026-10-08T12:09:04Z。
- branches -> 固定2513be26b318457df8314c7a0923fd5667de09bd；commit日期2026-10-08T12:09:01Z。
- 递归Git树3902项，未截断。
- 读取README.md、LICENSE（MoSheng2020）、electron/package.json（0.8.16）、electron/examples/basic.lcpp、electron/examples/最小示例.lcpp、cloud/admin/docs/guide/user/lingcpp-quickstart.md。
- 读取electron/src/services/lingCpp/parser.ts（1395行）：类、方法、事件、局部、结束、结束类实际解析与诊断。
- 读取electron/src/services/build/projectCodeGeneratorService.ts：构建编排，未将其当核心语言翻译器。
- 核心electron/src/services/windowDesigner/lingCppWin32Project.ts（1,881,618字节，33582行）contents返回空，raw fetch报太大；通过已知blob SHA 41d1a59266a517d03bf41188fb0e1cb2333f4f78取得全文。第361–399行工程生成入口；659–660行生成main.cpp；724–727调用parseLingCpp；31865–31983行中文控制结构的C++字符串生成。
- GitHub Releases仅“灵码更新助手”（published_at=2026-09-25T11:34:01Z），不将其当语言发行版。

## 原始短代码
https://github.com/mosheng20205/lingbuilder/blob/2513be26b318457df8314c7a0923fd5667de09bd/cloud/admin/docs/guide/user/lingcpp-quickstart.md#L16-L20
完整五行窗口类示例；不是拼凑源码。需要窗口项目上下文，未执行。

## 分类与待核实
LingCpp是语言，LingBuilder/灵码是IDE及平台；LCPP是其文件/语法名，按一项收录。该项目不在现有34条或Issue3/4/5。
未核实：语言独立版本、首次公开日期、原始介绍文章发布日期；全生态功能和跨平台运行结果；README“IDE与导出工程行为一致”的所有场景。
已核实：中文语法、解析实现、C++生成实现及C++目标；AI助手不属于该确定性转译链的必要证据。无需按“AI语言”归类。

## 可发布发现文案
新增一项原目录及Issue3/4/5之外的源码级发现：LingCpp（LingBuilder/灵码的.lcpp语言）。官方快速上手有连续“类/事件/结束/结束类”样例，TypeScript parser与C++/Win32工程生成源码已核验，固定2513be2。按中文C++转译语言收录，LingBuilder为配套IDE，不重复计数；IDE版本0.8.16、语言独立版本与首发待核实。未运行或采信性能宣传。
