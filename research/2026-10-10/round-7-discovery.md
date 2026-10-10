# 第七轮：微型与AI辅助中文语言发现

核验日期：2026-10-10（UTC）。基础目录提交：697f78bd2d10a85a0c0c8cce9444bf03bdbf415a。实际检索与核验时段：17:30—17:38 UTC。

## 范围与结果

本组主动搜索2024—2026创建的低关注度中文语法仓库，采用GitHub只读接口与普通网页搜索。根AGENTS.md、55项语言目录、research/2026-10-10/round-6.md、9个开放Issues及其全部评论用于查重。开放议题编号为1、3、4、5、11、13、16、18、19。豫言维持原样。

选取3组本轮新发现整理正式候选：PB（PengBooo）、chinese-interpreter（ling0x）、龙语言（仍然）。另9组新候选保留待核实。PB关联的2024年PengBooo仓库作为同一GitHub账号下的历史材料保存，单独计数待沿革核验。TRAE165813属于Issue #5既有辅助线索，本轮只补可读索引资料。

正式候选均取得原始连续中文代码、固定提交、作者线索、实现入口和版本资料。这里的核验层级为原始源码与发行元数据静态阅读，运行与测试结果独立标记。星数仅用于低关注度检索观察，2026-10-10所见PB为0星、ling0x解释器为0星、龙语言为1星。

## PB（PengBooo）

- 原仓库：https://github.com/nntandg/pb-lang
- 固定提交：ee2dc2845adf42a95e381d4b74b39dbd0552b9cb；作者日期2026-05-14T15:35:29Z。
- 仓库创建：2026-05-14T15:19:59Z。最早可见提交52f47bf7dc1f1e3a466e6a66397830e8832e724e，作者日期2026-05-14T15:27:39Z。
- 作者：固定README与zhpy.py署名PengBooo／彭博，pyproject.toml为PengBooo / Pengbo，提交关联nntandg。
- 中文原例：[tests/test_pb_extension.pb第8—19行](https://github.com/nntandg/pb-lang/blob/ee2dc2845adf42a95e381d4b74b39dbd0552b9cb/tests/test_pb_extension.pb#L8-L19)，连续包含定义、返回、中文乘法、如果／否则、对于／在／执行。
- 实现：[zhpy.py词法器](https://github.com/nntandg/pb-lang/blob/ee2dc2845adf42a95e381d4b74b39dbd0552b9cb/zhpy.py#L443-L486)、[中文控制流翻译](https://github.com/nntandg/pb-lang/blob/ee2dc2845adf42a95e381d4b74b39dbd0552b9cb/zhpy.py#L988-L1071)、[compile与exec入口](https://github.com/nntandg/pb-lang/blob/ee2dc2845adf42a95e381d4b74b39dbd0552b9cb/zhpy.py#L2054-L2079)。按Python中文语法转译语言分类。
- 版本：[v0.3.1](https://github.com/nntandg/pb-lang/releases/tag/v0.3.1)于2026-05-14T15:29:52Z发布；[标签引用](https://api.github.com/repos/nntandg/pb-lang/git/ref/tags/v0.3.1)指向525f0957b0705922e765c27c061636d700c3f098。发行元数据列pb-lang-0.3.1.tar.gz（30,881字节）及pb_lang-0.3.1-py3-none-any.whl（36,166字节）。包内容独立复核待补。
- [PROJECT_STATE.json](https://github.com/nntandg/pb-lang/blob/ee2dc2845adf42a95e381d4b74b39dbd0552b9cb/PROJECT_STATE.json)记录ZHPY／CHPY→PB展示名变化，并追溯2026-05-11开发阶段。测试成绩按作者自述保存。
- 许可：pyproject.toml声明MIT；完整授权正文与范围待核实。

### 同一GitHub账号下的2024年PengBooo材料

[nntandg/PengBooo](https://github.com/nntandg/PengBooo)创建于2024-08-28T08:10:09Z。固定提交4a33762d76ebc82691c2378c7ff831371e0e5f71，作者日期2024-08-28T09:33:54Z；该仓的pushed_at为2026-05-08T15:03:18Z，与默认分支最后提交日期分别记录。

[固定README](https://github.com/nntandg/PengBooo/blob/4a33762d76ebc82691c2378c7ff831371e0e5f71/README.md)已用.pb文件，并展示“将x定义为1”“创建函数a”“函数创建结束”“如果x > x2那么运行a”。[pengbooo.py](https://github.com/nntandg/PengBooo/blob/4a33762d76ebc82691c2378c7ff831371e0e5f71/pengbooo.py)以run_project及逐行分派处理这些语句。2026版本采用Lexer／Translator及不同函数结构。两仓的项目迁移、代码继承和连续版本关系继续待核实。同一账号与名称关联作为有依据的历史联系保存。

周蟒lang-014的原始来源链为gasolin/zhpy。PB同仓ZHPY／CHPY旧称及兼容命令按作者来源独立消歧。

## chinese-interpreter（ling0x）

- 原仓库：https://github.com/ling0x/chinese-interpreter
- 固定提交：e5e3a410508288f1b6d7701429137e956c11d818；作者日期2025-11-02T17:49:12Z。
- 仓库创建2025-11-01T02:55:14Z；最早可见提交7cd2ac31669a424107531133a3e0cf6408e785b8，作者日期2025-11-01T02:55:49Z。
- 作者：ling0x，4条可见提交均关联该账号。
- 中文原例：[programs/program.zh第1—5行](https://github.com/ling0x/chinese-interpreter/blob/e5e3a410508288f1b6d7701429137e956c11d818/programs/program.zh#L1-L5)，两个变量分别使用二十五、一百二十三并输出。poem.zh另有字符串连接原例。
- [完整pest规则](https://github.com/ling0x/chinese-interpreter/blob/e5e3a410508288f1b6d7701429137e956c11d818/src/chinese_lang.pest)明确“变量”“输出”，PROGRAM由声明与输出构成；字符串、中文数词、ASCII数字和波浪号连接单独定义。
- [main.rs](https://github.com/ling0x/chinese-interpreter/blob/e5e3a410508288f1b6d7701429137e956c11d818/src/main.rs)读取并解析源码，[executor.rs](https://github.com/ling0x/chinese-interpreter/blob/e5e3a410508288f1b6d7701429137e956c11d818/src/executor.rs)直接执行。运行时值为i64及String，变量环境为HashMap。
- [Cargo.toml](https://github.com/ling0x/chinese-interpreter/blob/e5e3a410508288f1b6d7701429137e956c11d818/Cargo.toml)版本0.1.0、包名chinese-compiler、Rust edition 2024。仓库名与包名作为同一项目入口关联。
- Releases与git/matching-refs/tags/均返回空数组。实现、版本、原例可读；发行物、许可、独立运行与AI参与待核实。

## 龙语言（仍然）

- 原仓库：https://github.com/RengRan199925/LongLanguage
- 固定提交：01f569b5d2d8ca43dc4295fcbb1be942cc21fa6c；作者日期2026-04-13T12:38:25Z。
- 仓库创建2026-04-13T12:26:59Z；最早可见提交d37b109c1884f7bcaa9b35ef20a849db12c58980，作者日期2026-04-13T12:34:50Z。
- [固定README](https://github.com/RengRan199925/LongLanguage/blob/01f569b5d2d8ca43dc4295fcbb1be942cc21fa6c/README.md)明确“操作人：仍然”，项目阶段“开发中”，AI工具“Cursor＋Claude”；两次提交均含Made-with: Cursor。AI生成范围采用作者自述层级。
- 中文原例：[斐波那契.long第5—8行](https://github.com/RengRan199925/LongLanguage/blob/01f569b5d2d8ca43dc4295fcbb1be942cc21fa6c/examples/%E6%96%90%E6%B3%A2%E9%82%A3%E5%A5%91.long#L5-L8)，完整递归函数，使用函数、整数、如果、返回。
- [resolver.rs第36—62行](https://github.com/RengRan199925/LongLanguage/blob/01f569b5d2d8ca43dc4295fcbb1be942cc21fa6c/longc/src/resolver.rs#L36-L62)串接Lexer／Parser与模块合并；[lib.rs第117—130行](https://github.com/RengRan199925/LongLanguage/blob/01f569b5d2d8ca43dc4295fcbb1be942cc21fa6c/longc/src/lib.rs#L117-L130)串接类型检查、IR构建、代码生成、二进制封装。类型检查错误打印为警告后继续编译。
- [多架构分派](https://github.com/RengRan199925/LongLanguage/blob/01f569b5d2d8ca43dc4295fcbb1be942cc21fa6c/longc/src/codegen/mod.rs)包含x86、x86_64、arm64；[x86_64实现](https://github.com/RengRan199925/LongLanguage/blob/01f569b5d2d8ca43dc4295fcbb1be942cc21fa6c/longc/src/codegen/x86_64/mod.rs)写入机器码字节并修补调用及分支；binary/mod.rs按目标系统选择PE或ELF。
- longc/Cargo.toml版本0.1.0，Rust edition 2021。Releases与标签列表为空。
- longc、long-lsp、龙工坊IDE、C运行时、标准库及龙界面按同一项目配套组件记录。完整平台覆盖、性能、测试、第三方来源和许可继续待核实。README声明MIT，仓库树另含stb第三方源文件。

## 9组新发现待核实候选

### 1. 太和／TaiHeLang

- 仓库：[naodingaoaoao/TaiHeLang](https://github.com/naodingaoaoao/TaiHeLang)
- 创建时间：2026-02-27T10:20:05Z；固定提交：c52c75f9ef82772017ffd19042fce72b8d891e71。
- 分类：中文编译语言候选。
- 已取得：固定README自述中文关键字、Python编译器、LLVM IR与Electron IDE，指向spec.md和examples。
- 后续：原始连续中文例程、词法与解析实现、LLVM生成入口、发行和AI参与待核实。
- 固定来源：https://github.com/naodingaoaoao/TaiHeLang/blob/c52c75f9ef82772017ffd19042fce72b8d891e71/README.md

### 2. pchinese

- 仓库：[LostPEople634/pchinese](https://github.com/LostPEople634/pchinese)
- 创建时间：2026-08-06T05:30:41Z；固定提交：8c1a0957d3177dd85a7723c4dcb6ab042b6a2752。
- 分类：Python中文语法翻译层候选。
- 已取得：固定README提供“定义／如果／返回”阶乘、类与全角标点原例，自述代码区整词替换及Python compile＋exec流程，1.2加入PyQt中文词表。
- 后续：词法扫描与运行实现、具体包版本、发行与中文库映射边界待核实。
- 固定来源：https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/README.md

### 3. ChineseToyLang

- 仓库：[sundaolin9527/ChineseToyLang](https://github.com/sundaolin9527/ChineseToyLang)
- 创建时间：2025-06-01T08:03:13Z；固定提交：897456459430f6c9abcb517fa3249739f502e7b2。
- 分类：中文玩具编译器候选。
- 已取得：固定tests/examples/test_variable.txt包含“令 a = 28;”“恒 PI = 3.1415926;”及真／假等中文语法；文件树包含C/C++词法器、解析器、IR与后端实现。
- 后续：准确语言名、docs规范、LLVM或其他后端依赖、完整流水线、版本和许可待核实。
- 固定来源：https://github.com/sundaolin9527/ChineseToyLang/blob/897456459430f6c9abcb517fa3249739f502e7b2/tests/examples/test_variable.txt

### 4. XuYu

- 仓库：[mehaotian/xuyu](https://github.com/mehaotian/xuyu)
- 创建时间：2026-09-22T01:48:00Z；固定提交：2974fd20dc0b0a91eab3a83c063c21a8527a897b。
- 分类：中文编程语言设计与早期解释器候选。
- 已取得：固定README将当前实现范围列为中文标识符、整数赋值、引用和四则表达式，采用Go；后续计划列出“输出”“如／否则”，指向语言规范-v0.1.md。
- 后续：当前原例的汉字语法边界、中文关键字规范、实现与设计分别分类、版本和许可待核实。当前实现证据按标识符与表达式阶段记录。
- 固定来源：https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/README.md

### 5. 中文Rust语法设计与转译工具

- 仓库：[bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool](https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool)
- 创建时间：2026-07-03T03:40:07Z；固定提交：4605fee9402c9ad6fe6e06771b6d2443105eada8。
- 分类：中文→Rust转译设计候选。
- 已取得：固定README提供“函数／让／可变／如果／返回”等关键词到Rust的映射规范，描述确定性语法糖和错误定位方案。
- 后续：实际用户连续代码、源码实现、设计完成度、版本和许可待核实。
- 固定来源：https://github.com/bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool/blob/4605fee9402c9ad6fe6e06771b6d2443105eada8/README.md

### 6. 中文智能合约编译器／zhsc-compiler

- 仓库：[Anubisya/zhsc-compiler](https://github.com/Anubisya/zhsc-compiler)
- 创建时间：2025-10-24T12:07:05Z；固定提交：f6d8665def53639a8b8b3adf473fdfa177e93632。
- 分类：Solidity中文语法转译DSL候选。
- 已取得：固定README有完整“.zhs”合约原例，使用“合约／公开／字符串／函数／返回”，列出Python lexer、parser、AST和Solidity生成器。
- 后续：源码实现、中文名称转拼音处理、Solidity语义覆盖、版本与发行待核实。
- 固定来源：https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/README.md

### 7. chinalang／中国语言

- 仓库：[sjqtentacles/chinalang](https://github.com/sjqtentacles/chinalang)
- 创建时间：2026-06-21T00:11:22Z；固定提交：59332f7c0d02c130257124cbbedbe8d2fd1cafc4。
- 分类：中文／英文双关键字戏仿语言候选。
- 已取得：固定README有“宣布／说／函数／上交／如果／否则”等关键字及中文程序，说明Go树遍历解释器和Lisp式宏。
- 后续：原始实现、运行时机制、作者背景、版本、许可与同源关系待核实。
- 固定来源：https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/README.md

### 8. MiniLang（FI0m9ySans）

- 仓库：[FI0m9ySans/minilang](https://github.com/FI0m9ySans/minilang)
- 创建时间：2025-11-04T05:49:43Z；固定提交：2778f3d3df8d6806c5b9b763e31e7d0d3ac19c7d。
- 分类：中文解释语言候选。
- 已取得：固定README提供“定义 数字 = 10;／函数 平方(甲)／返回”连续原例，称Python词法器、解析器与解释器，源文件后缀.kalop。
- 后续：实际实现文件、作者与AI参与、版本、发行、许可及其他MiniLang同名关系待核实。
- 固定来源：https://github.com/FI0m9ySans/minilang/blob/2778f3d3df8d6806c5b9b763e31e7d0d3ac19c7d/README.md

### 9. PyCn（sunzi334481）

- 仓库：[sunzi334481/PyCn](https://github.com/sunzi334481/PyCn)
- 创建时间：2026-10-05T11:54:33Z；固定提交：f840307aab9f55e7d25d798768db0ad4db24edb0。
- 分类：Python中文语法转译语言候选。
- 已取得：固定README提供中文递归阶乘原例和.pycn后缀，描述token级转译、中文模块导入钩子及编辑器插件。
- 后续：翻译源码、版本与发行、测试层级、同类Python中文项目沿革及AI参与待核实。
- 固定来源：https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/README.md

## 既有线索与重复入口

### TRAE165813：Issue #5辅助线索增量

2026-10-10网页搜索已返回[原帖](https://forum.trae.cn/t/topic/165813)的较长索引正文，标题为《【学习工作赛道】中文编程IDE——本土化零基础编程开发工具》，发布账号u701959982292476，索引正文显示2026年7月15日10:57。正文作者自述用TRAE Work和TRAE IDE构建中文词法、语法、JS代码生成及网页IDE，源文件扩展名为.中码。作者说明AI按其需求参与开发。原页直接读取仍返回超时。

该内容按Issue #5既有辅助线索增量保存。索引正文、原页当前内容、正式名称、连续原例和核心源码的对应性继续核实。本轮新发现计数保持3组正式候选＋9组待核实候选。

### Afiredream／Chinese++

检索再次命中Afiredream/ChinesePlusPlusCompiler，其README下载链接指向YoloLogic/ChinesePlusPlus，开放Issue #11的第四轮评论已将其作为Chinese++同源分叉处理。该入口沿用lang-046关系记录。

## 检索关键词、平台与时间范围

### GitHub仓库搜索

2026-10-10执行，单个查询请求至多100项。created筛选表示GitHub建库时间，语言最早公开时间按原始材料另核。检索分三层：中文概念词、低星编译／解释工具、英文Chinese关键词与2024年补查。

- `"中文关键字" created:2024-01-01..2026-10-10`；返回7项。
- `"中文解释器" created:2024-01-01..2026-10-10`；返回0项。
- `"自制编译器" "中文"`；返回0项。
- `"全中文" created:2024-01-01..2026-10-10`；返回100项。
- `"中文" "编译器" created:2024-01-01..2026-10-10 stars:0..3`；返回100项。
- `"中文" "解释器" created:2024-01-01..2026-10-10`；返回100项。
- `"中文编程" created:2025-01-01..2026-10-10 stars:0..3`；返回100项。
- `"Chinese programming language" created:2024-01-01..2026-10-10`；返回9项。
- `"中文语法" created:2024-01-01..2026-10-10 fork:false`；返回13项。
- `"Chinese keywords" created:2024-01-01..2026-10-10 fork:false`；返回10项。
- `"全中文代码" created:2024-01-01..2026-10-10 fork:false`；返回1项。
- `"编译器" "AI" "中文" created:2024-01-01..2026-10-10 fork:false`；返回3项。
- `"自制" "语言" "中文" created:2024-01-01..2026-10-10 fork:false`；返回2项。
- `"中文编程" created:2024-01-01..2024-12-31 fork:false`；返回7项。

部分前段检索出现大量翻译教程和fork，占满100项首屏。后段采用fork:false及“中文语法”“Chinese keywords”等更窄主题词增加有效覆盖。首屏之外的结果仍有遗漏风险。

### 普通网页搜索

- `"中文编程语言" "AI" "2026" github -豫言 -site:github.com/yuyan-lang`
- `"中文解释器" "2025" github`
- `"全中文代码" "编译器" "2026"`

结果提供TRAE165813旧线索的新索引正文，并再次命中灵码LingBuilder、奇语言、意语言和Dalin L等资料。目录已收录关系、既有Issue与仅中文标识符的命中分别处理；网页聚合转载用于发现路径，技术结论采用原仓库和原作者文档。

## 访问与遗漏风险

- GitHub搜索结果受名称、说明、排序及索引覆盖影响，100项首屏属于有界发现范围。
- ChineseToyLang的README.md请求返回404；读取原目录后定位docs及tests/examples，取得中文源码。单个README缺失按路径问题处理。
- GitHub Fetch的/repos/.../tags端点返回400状态；改用受支持的git/ref和git/matching-refs只读Git资源核对标签。该工具限制与仓库标签存在状态分别记录。
- TRAE原页直接打开超时，搜索索引正文可读，当前完整页面和演示仍待核。
- 日期分别记录仓库创建、提交作者日期与发行发布时间；pushed_at和语言首发时间各自使用。
- 原例逐字摘取固定文件，作者测试成绩、功能清单、自研与AI生成声明保留相应证据层级。
- 部分新候选当前只有README规范层核验，按待核实保存；XuYu当前实现集中于标识符与表达式，中文关键字设计和实际实现需要分别核对。


## 补充源码审阅

龙语言PE发射器的x86_64分支构造PE32+头、导入表与代码节；其余架构进入emit_stub简化PE32分支，实际写入代码。ELF发射器按架构构造32／64位ET_EXEC文件。各目标、动态库与APK能力的独立验证待核实。

- [PE分派](https://github.com/RengRan199925/LongLanguage/blob/01f569b5d2d8ca43dc4295fcbb1be942cc21fa6c/longc/src/binary/pe.rs#L14-L17)
- [简化PE32分支](https://github.com/RengRan199925/LongLanguage/blob/01f569b5d2d8ca43dc4295fcbb1be942cc21fa6c/longc/src/binary/pe.rs#L258-L288)
- [ELF64文件封装](https://github.com/RengRan199925/LongLanguage/blob/01f569b5d2d8ca43dc4295fcbb1be942cc21fa6c/longc/src/binary/elf.rs#L58-L114)
