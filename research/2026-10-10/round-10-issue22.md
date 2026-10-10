# 第十轮：Issue #22 zhsc-compiler与chinalang核验

核验日期：2026-10-10（UTC）。目录基线：[320b1f6904747bd8afcbb0c1d3655d965ed53ed3](https://github.com/yuyan-lang/chinese-programming-languages/tree/320b1f6904747bd8afcbb0c1d3655d965ed53ed3)，68项语言、8项内核。

## 范围与结果

本分项先读取根AGENTS.md、递归目录、data/languages.json、第九轮汇总round-9.md，以及[Issue #22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)全部正文和3条评论。第三条评论明确pchinese与MiniLang已在第九轮入目录，初始10组已有4组完成分类。本轮限定核验其中两个旧候选：Anubisya/zhsc-compiler、sjqtentacles/chinalang。

- 新发现0项。
- 旧候选深入2项，完成正式分类资料2项：中文Solidity DSL设计及部分实现原型1项，中文／英文双关键字独立AST解释器1项。
- 剩余字段核验2组，归属于本轮这两项分类资料，见配套pending.json。
- 本轮两项纳入分类目录，Issue #22初始10组累计完成分类6组，余下4组仍按原议题核实。
- 豫言及其他既有条目保持本分项范围之外。
- 两段code分别来自固定README连续11行、固定.cn原例连续10行；全文截取与独立按行读取逐字匹配均为true。

研究方法为公开网页、GitHub文件和元数据只读取证，交付本地资料文件。程序安装、构建、源码执行、桌面任务、链上部署和任何外部写入均在本分项范围之外。JSON组装与逐行比对只处理已取得文本。

## 一、中文智能合约编译器（zhsc-compiler）

固定快照：[f6d8665def53639a8b8b3adf473fdfa177e93632](https://github.com/Anubisya/zhsc-compiler/tree/f6d8665def53639a8b8b3adf473fdfa177e93632)。GitHub默认main头与Issue既存快照一致，公开分支列表仅main，默认分支提交2条，递归树8项、truncated=false。

### 中文原例与类别

[README第29—39行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/README.md#L29-L39)保存完整问候合约，使用“合约、公开、字符串、函数、只读、返回”等语法关键字。原例含变量、读取函数和设置函数；[第70—123行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/README.md#L70-L123)列出类型、关键字、可见性、可变性及内置链上变量。

分类采用“中文Solidity DSL设计及部分实现原型”。首句明确设计和部分实现阶段。分类依据是公开中文语法规范、连续程序及目标语言映射；设计阶段沿用目录已收录规范与例程型项目的口径。完整转译能力另列待核实。

[README第51—67行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/README.md#L51-L67)展示对应Solidity及拼音名称，按作者示意输出记录。中文名称转拼音的算法、同音冲突、字符串处理和Solidity输出合法性待核实。README后文将示例称为ERC20代币合约，ERC20标准符合性待核实；条目统一称代币示例。

### 实际实现范围和调用链

完整固定树为：.gitignore、LICENSE、README.md、__init__.py、ast_nodes.py、cli.py、compiler.py、requirements.txt。根提交[0a1d7837bff8fb1745e6aba09d43a0f7bc2b6049](https://github.com/Anubisya/zhsc-compiler/commit/0a1d7837bff8fb1745e6aba09d43a0f7bc2b6049)也保存这8个文件，核心Python文件blob与当前快照一致。

1. [ast_nodes.py第10—255行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/ast_nodes.py#L10-L255)保存节点类型、可见性、可变性枚举，以及Program、Contract、StateVariable、Function、Constructor、Event、Parameter、Block、语句和表达式节点。
2. [compiler.py第10—12行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/compiler.py#L10-L12)导入lexer.chinese_lexer、parser.chinese_parser和codegen.solidity_generator。
3. [第93—129行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/compiler.py#L93-L129)依次调用tokenize(source_code)、parse(tokens)、generate_solidity(ast)，分别包装LexerError、ParserError和CodeGenError。该段证明调度入口和预设接口。
4. 固定树及根提交实际文件范围如上。三个核心模块的公开实现位置待核实；词元生成、语法解析、AST构造与Solidity输出之间的完整实现链待核实。
5. [compiler.py第56—91行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/compiler.py#L56-L91)提供UTF-8文件读取及输出.sol的封装。[cli.py第29—91行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/cli.py#L29-L91)封装编译、词元显示、AST显示；check命令仍调用compiler.compile。
6. [requirements.txt第1行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/requirements.txt#L1)声明pypinyin>=0.49.0；[cli.py第8—12行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/cli.py#L8-L12)另有click与rich导入。完整CLI依赖配置和可运行性待核实。
7. [README第159—175行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/README.md#L159-L175)的目录布局按文档描述保存，源码存在性以固定树为准。

### 作者、创建、提交和发行分列

- 仓库账号：Anubisya。两条提交的作者名Evil，GitHub作者关联账号Anubisya。
- 仓库创建：2025-10-24T12:07:05Z。
- 初始源码提交：[0a1d7837](https://github.com/Anubisya/zhsc-compiler/commit/0a1d7837bff8fb1745e6aba09d43a0f7bc2b6049)，作者与提交时间2025-10-24T12:08:42Z，文件8项。
- 当前提交：[f6d8665](https://github.com/Anubisya/zhsc-compiler/commit/f6d8665def53639a8b8b3adf473fdfa177e93632)，时间2025-10-24T12:12:19Z，修改README在线入口和项目链接。
- 源码版本：[cli.py第20行及134—140行](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/cli.py#L134-L140)自标0.1.0；作者字段为Your Name占位。
- 公开发行：2026-10-10读取[Releases](https://github.com/Anubisya/zhsc-compiler/releases)集合为空；git/refs/tags返回404。独立发行及发布日期待核实。
- 许可：[固定MIT文本](https://github.com/Anubisya/zhsc-compiler/blob/f6d8665def53639a8b8b3adf473fdfa177e93632/LICENSE#L1-L21)，署名2024 Chinese Solidity Compiler。2024作为版权字段保存；其对应更早开发或公开历史待核实。
- AI参与：本次已读材料中的具体AI开发声明、工具记录和比例待核实。

### 关系及在线入口

GitHub元数据fork=false。README、CLI、同名仓库与许可署名组成身份链；Solidity为目标语言，pypinyin为声明的第三方依赖。README直接链接[zhsc.niubiui.com](https://zhsc.niubiui.com)。普通网页工具读取该地址返回不可访问，搜索也未取得可核对服务正文，记录为本次访问结果。在线页面与仓库代码对应、完整后端和部署状态待核实。此项按DSL资料收录，安全审计与合约资产操作在研究范围之外。

## 二、chinalang（中国语言）

固定快照：[59332f7c0d02c130257124cbbedbe8d2fd1cafc4](https://github.com/sjqtentacles/chinalang/tree/59332f7c0d02c130257124cbbedbe8d2fd1cafc4)。默认main头与Issue快照一致，公开分支列表仅main；树60项、文件52项、18份_test.go、14份.cn原例，truncated=false。

### 原例与分类

[examples/directives.cn第8—17行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/examples/directives.cn#L8-L17)包含完整“反之”宏及调用，使用“宣布、指示、引用、如果、篡改、否则、说、假、打印”。原例属于作者仓库已有.cn文本，中文关键字直接参与解析和求值。

分类采用“中文／英文双关键字戏仿语言／Go独立AST解释器”。作者[README](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/README.md#L1-L88)与初始提交以esoteric／satirical描述项目；条目以中性技术语言说明其程序内部的文本过滤、积分、日志和特殊错误语义。

### 完整词法、解析、AST和执行链

1. [token/token.go第70—127行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/token/token.go#L70-L127)将中英文关键字映射到同一TokenType。中文形式含宣布、永恒、说、函数、上交、如果、否则、真、假、当、和谐、举报、社会信用、宣传、再教育、五年计划、引用、篡改、指示。
2. [lexer/lexer.go第18—138行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/lexer/lexer.go#L18-L138)以[]rune保存输入、逐字符产生Token，并附行列；第158—164行先读取整个标识符再LookupIdent。第198—209行用unicode.IsLetter及ASCII数字识别名称组成。中文关键字要求词边界，符合README“说x”为单个标识符的说明。
3. [ast/ast.go](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/ast/ast.go#L10-L429)定义Statement、Expression、Program和声明、赋值、返回、循环、函数、宏、调用、数组、哈希等节点。
4. [parser/parser.go第12—199行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/parser/parser.go#L12-L199)注册前缀、中缀规则和运算优先级，ParseProgram构造AST；[第310—521行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/parser/parser.go#L310-L521)完成Pratt表达式、分支、函数、数组、哈希和宏语法。
5. [main.go第29—46行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/main.go#L29-L46)接通lexer.New→parser.New→ParseProgram→DefineMacros→ExpandMacros→Eval，创建变量环境、宏环境和运行时State。
6. [evaluator/evaluator.go第16—120行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/evaluator/evaluator.go#L16-L120)依AST节点分派；函数对象捕获定义环境。[第419—466行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/evaluator/evaluator.go#L419-L466)核对参数个数、创建闭包环境并执行函数体；[object/object.go第217—282行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/object/object.go#L217-L282)保存环境链、常量和重赋值。
7. [repl/repl.go第76—137行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/repl/repl.go#L76-L137)重复使用同一变量、宏和运行时环境，支持多行读取及元命令。文件路径和REPL路径具有可追踪的同一解释链。

### 宏与特殊运行时

[macro_expansion.go第8—119行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/evaluator/macro_expansion.go#L8-L119)先提取顶层宏定义并从主程序移除；调用实参冻结为Quote，宏体通过[ast.Clone](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/ast/clone.go#L3-L96)复制，再由Eval求值，返回Quote.Node取代原调用。[quote_unquote.go第11—78行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/evaluator/quote_unquote.go#L11-L78)把反引用求值结果转换为AST。该机制属于解释器内的确定性AST处理；AI共同署名作为开发记录另列。

[firewall.go](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/evaluator/firewall.go#L11-L153)对字符串做大小写无关子串查表，处理输出、变量绑定、和谐块及再教育块；[state.go](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/evaluator/state.go#L5-L109)保存积分、违规次数和日志。运行时主题按程序语义记录。

静态边界：

- [五年计划源码第315—339行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/evaluator/evaluator.go#L315-L339)将循环次数设为5并绑定“规划”；ReturnValue、Error与Detained分支可提前返回。条目采用源码边界说明其行为。
- 空值由object.Null表示，越界索引、缺键和部分默认分支返回该值；中文／英文裸null字面量的语法入口待核实。
- 宏结果须为Quote，类型检查失败处直接调用panic；实参绑定按参数索引读取。异常实参数量、宏返回值、嵌套展开及错误处理行为待核实。
- REPL使用字符级花括号计数；字符串和注释中花括号对多行输入的影响待独立核实。
- [examples_test.go第183—202行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/evaluator/examples_test.go#L183-L202)保存宏原例输出及日志断言；macro_expansion_test还覆盖重复调用的AST隔离。所有测试按源码证据记录，实际测试通过状态待核实。

### 作者、创建、提交、发行与许可分列

- 仓库账号与提交署名：sjqtentacles。[作者公开主页](https://github.com/sjqtentacles)自述为编程语言爱好者，主页直接链接chinalang；显示所在地USA。身份和地域仅按公开自述保存。
- 仓库创建：2026-06-21T00:11:22Z。
- 根提交：[e0054f918848f8ab2e8349952a7bb00dc73c9f13](https://github.com/sjqtentacles/chinalang/commit/e0054f918848f8ab2e8349952a7bb00dc73c9f13)，作者和提交时间均2026-06-21T00:11:05Z，加入52文件、6485行。该Git时间早于仓库创建17秒，各自按来源原值记录。
- 当前提交：[59332f7c0d02c130257124cbbedbe8d2fd1cafc4](https://github.com/sjqtentacles/chinalang/commit/59332f7c0d02c130257124cbbedbe8d2fd1cafc4)，时间2026-06-21T00:14:14Z，修订README介绍。
- 工具链：[go.mod第1—3行](https://github.com/sjqtentacles/chinalang/blob/59332f7c0d02c130257124cbbedbe8d2fd1cafc4/go.mod#L1-L3)声明module chinalang及go1.26.2；README写Go1.26+。
- 语言版本：正式版本号待核实。
- 公开发行：[Releases集合](https://github.com/sjqtentacles/chinalang/releases)返回空数组，git/refs/tags返回404。发行物及发布日期待核实。
- 许可：GitHub license为null，固定文件树中的许可文本待核实，整体使用许可待核实。
- AI范围：两条提交都含“Co-authored-by: Cursor”尾注。根提交涵盖解释器、原例和测试，后续提交涵盖README；可核事实为这两次提交的共同署名。具体行级归属、生成比例和人工审查过程待核实。

### 上游、同名与去重

GitHub元数据fork=false，go.mod只含模块名和工具链版本，已读核心文件导入仓库内包及Go标准库。Lisp式宏按作者说明及源码结构保存；外部解释器或教材源码继承待原作者资料核实。

GitHub查询chinalang in:name fork:true另返回Rubell1on/chinalang。读取该仓元数据得另一账号与master分支，README.md路径请求返回404。本分项将其作为同名排重结果，保持sjqtentacles项目身份边界；两个仓库的代码同源关系待核实。额外同名结果属于排重记录，新发现计数保持0。

## 检索覆盖、关键词与风险

检索平台：GitHub公开仓库、GitHub元数据及文件接口、普通网页搜索。研究时段为2026-10-10 UTC；核验截至该日。普通搜索采用不限发布日期，核心材料时间跨度为2025-10—2026-06，zhsc许可署名追溯到2024。搜索结果和Git仓日期分开处理。

实际关键词：

- 普通网页：“zhsc-compiler” “Anubisya”；“chinalang” “sjqtentacles”
- 普通网页：“zhsc.niubiui.com”；“zhsc-compiler” lexer parser
- 普通网页：“chinalang” “license”；“chinalang” “Monkey”；“sjqtentacles/chinalang” “Monkey”
- 普通网页：“zhsc-compiler” “AI”；“zhsc-compiler” “ChineseLexer”
- GitHub仓库检索：zhsc-compiler in:name fork:true；chinalang in:name fork:true
- 本地资料去重：固定68项languages.json按zhsc、chinalang、Anubisya、sjqtentacles查找，命中0项。

结果及限制：

- zhsc名称检索返回原仓1项；chinalang名称检索返回原仓及另一同名仓2项。
- 普通网页检索先出现作者主页镜像，随后直接读取github.com/sjqtentacles核对主页身份和项目链接，镜像内容作为导航线索。
- 其余搜索包含大量无关结果，技术结论采用固定原仓文件，AI、许可和上游继承的缺口按待核实保存。
- zhsc在线入口读取返回不可访问；GitHub主页网页读取出现Cache miss，GitHub连接器固定文件与API读取成功。工具读取失败和项目服务真实状态分别记录。
- GitHub通用fetch对/repos/.../tags列表端点返回不支持的URL；改用受支持的git/refs/tags元数据读取，两仓均返回404。发行集合与标签查询分别保存，正式版本判断继续审慎。
- 完整树truncated=false支持当前公开文件范围判断；仓库创建、Git时间、版权年份和Release时间属于不同证据类型。私有源码、历史删改、仓外服务实现、早期本地开发及跨站转载仍有遗漏风险。
- 中文代码保留原连续文本；文档功能承诺、可读源码、测试源码和独立执行结果分层记录。资料条目采用肯定陈述及明确待核实字段。

## 交付与核验

- data/languages.json中的lang-069与lang-070：2项无ID数组，description分别306与299字符，固定原例分别11与10行。
- round-10-issue22-pending.json：上述2项后续字段核验，包含对应固定来源。
- round-10-issue22.md：本日志。
- 新发现0；旧候选转正式分类资料2。完整解释链确认1项，设计及部分实现确认1项。
- 本分项交付研究资料，所有外部仓库、Issue、PR和发布状态保持只读范围。

