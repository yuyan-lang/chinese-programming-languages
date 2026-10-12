# XuYu：中文关键字实现与设计阶段核验

核验日期：2026-10-12。百科基线：f543ed92b06889da9e924511505858d8f239166b（95项语言、10项内核）。原仓固定提交：2974fd20dc0b0a91eab3a83c063c21a8527a897b。研究范围为Issue22 XuYu一项；外部写入、依赖安装、构建、测试和候选程序执行均为0。

## 分类结论

建议作为lang-096正式收录，类别为“中文赋值关键字的早期AST解释器／实验性语言设计”。

当前Go实现具有中文赋值关键字“设置”。[词法器L130—134](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/internal/lexer/lexer.go#L115-L141)将精确词形“设置”归入KindKeyword；[解析器L63—91](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/internal/parser/parser.go#L27-L91)要求该关键字、标识符、等号和表达式组成赋值语句。[完整作者原例](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/examples/%E9%98%B6%E6%AE%B50/%E6%95%B4%E6%95%B0%E8%A1%A8%E8%BE%BE%E5%BC%8F.%E4%B8%AD#L1-L2)包含两行连续中文赋值，第二行引用第一行变量并组合括号与四则运算。该证据支持当前中文语法实现的分类。

Issue22与第七轮候选记录保存的“中文标识符和表达式阶段”可更新为“中文赋值关键字与整数表达式阶段”。“输出”“如／否则”、循环、函数、对象和模块分别保留设计／后续计划状态。

## 作者连续原例

来源：https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/examples/%E9%98%B6%E6%AE%B50/%E6%95%B4%E6%95%B0%E8%A1%A8%E8%BE%BE%E5%BC%8F.%E4%B8%AD#L1-L2

文件：examples/阶段0/整数表达式.中，第1—2行，完整文件。blob：dbd725280d662f52d649dfdd6fd2f1c4c8e9c542。条目code字段保留末尾换行。

```text
设置 基数 = 10
设置 总数 = (基数 + 2) * 3 - 4 / 2
```

[README](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/README.md)提供预期输出“环境[基数=10, 总数=34]”；[CLI测试源码](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/cmd/zhongwen/main_test.go#L54-L65)对相同程序断言该字符串及末尾换行。本轮证据层为静态源码与原仓测试断言，独立运行结果待核实。

## 实现链

- [token.go](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/internal/token/token.go)定义通用KindKeyword、标识符、整数、等号、换行、四则与括号类型。
- [lexer.go L61—141](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/internal/lexer/lexer.go#L115-L141)按UTF-8 rune扫描，识别运算符和换行，readIdentifier只将“设置”标为关键字。[L201—215](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/internal/lexer/lexer.go#L201-L215)允许下划线、Han字符和ASCII字母作为首字符，后续还允许Unicode数字。整数词法接受unicode.IsDigit，数值转换采用strconv.ParseInt；非ASCII数字的数值解析边界待核实。
- [parser.go L27—91](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/internal/parser/parser.go#L27-L91)逐条解析赋值，使用换行分隔，跳过空行；赋值起始要求KindKeyword和精确词形“设置”。[L93—182](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/internal/parser/parser.go#L93-L182)以parseAdditive、parseMultiplicative、parsePrimary处理加减、乘除、括号、变量及整数。
- [ast.go](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/internal/ast/ast.go)提供Program、Assignment、IntegerLiteral、VariableReference、BinaryExpression，节点保留源码范围。
- [interpreter.go L27—140](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/internal/interpreter/interpreter.go#L27-L140)使用map[string]int64保存环境，逐条求值并赋值；二元表达式递归求值，分派加减乘除，显式检查除零。Environment.String排序变量名后生成调试输出。
- [runner.go L16—34](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/internal/runner/runner.go#L16-L34)按os.ReadFile→lexer.Lex→parser.Parse→interpreter.Run串联。
- [main.go L14—59](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/cmd/zhongwen/main.go#L14-L59)自标0.0.1-dev，支持帮助、版本、运行命令，运行成功显示环境调试串。语言层“输出”仍列在M2计划。
- [go.mod](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/go.mod#L1-L3)声明模块github.com/mehaotian/xuyu和Go1.22，模块文件只列自身模块与Go版本。

## 规范与实现的阶段区别

[语言规范v0.1 L43—84](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/docs/01-%E4%BA%A7%E5%93%81%E4%B8%8E%E8%AF%AD%E8%A8%80/%E8%AF%AD%E8%A8%80%E8%A7%84%E8%8C%83-v0.1.md#L43-L84)是候选基线：列“定义、设置、如、否则、当、重复、遍历、返回、止、跳、导入”等候选关键词，提供非正式EBNF。规范定义冒号加缩进块、文字引号「」、函数、对象和类型规则；若干语义保留待决状态。

[规范L91—94](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/docs/01-%E4%BA%A7%E5%93%81%E4%B8%8E%E8%AF%AD%E8%A8%80/%E8%AF%AD%E8%A8%80%E8%A7%84%E8%8C%83-v0.1.md#L88-L97)保存作者的四行连续条件设计原例：

```text
如 玩家.生命 > 0：
    输出 「存活」
否则：
    输出 「死亡」
```

该片段可作为设计例证；正式条目主例优先采用已有“设置”实现对应的两行完整.中文件。[当前整合计划](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/docs/10-%E5%BC%80%E5%8F%91%E8%AE%A1%E5%88%92/05-%E5%BD%93%E5%89%8D%E9%98%B6%E6%AE%B5%E6%95%B4%E5%90%88%E8%AE%A1%E5%88%92.md)明确M1整数表达式完成，M2为文字与输出，M3为比较、布尔、如／否则和缩进块；第5节明确M2、M3属于后续工作。当前规范与解析器分别对应候选设计和最小语言子集。

## 日期、版本、作者与最新状态

- [仓库元数据](https://api.github.com/repos/mehaotian/xuyu)：created_at为2026-09-22T01:48:00Z，pushed_at为2026-09-22T08:56:41Z，default_branch为main，fork=false，license=null。
- [根提交](https://github.com/mehaotian/xuyu/commit/345c6efc8f038e810a122e3d1eaf98d32b8c5707)：345c6efc8f038e810a122e3d1eaf98d32b8c5707，作者／提交者时间均为2026-09-22T02:09:05Z，parents为空。
- [当前提交](https://github.com/mehaotian/xuyu/commit/2974fd20dc0b0a91eab3a83c063c21a8527a897b)：2974fd20dc0b0a91eab3a83c063c21a8527a897b，作者／提交者时间均为2026-09-22T08:56:30Z。
- 两条保留提交均署名mehaotian并关联同名GitHub账号。自然人身份、完整分工及更早公开历史待核实。
- 2026-10-12读取[main分支](https://api.github.com/repos/mehaotian/xuyu/branches/main)仍指向固定提交，Issue22快照与当前默认分支一致。
- [根提交至当前比较](https://github.com/mehaotian/xuyu/compare/345c6efc8f038e810a122e3d1eaf98d32b8c5707...2974fd20dc0b0a91eab3a83c063c21a8527a897b)为ahead1，22项文件变化，新增整数表达式.中并扩展词法、AST、解析和解释求值。
- CLI源码0.0.1-dev与规范v0.1分别保存。[Releases集合](https://api.github.com/repos/mehaotian/xuyu/releases)返回空数组；[标签引用](https://api.github.com/repos/mehaotian/xuyu/git/refs/tags)返回404。正式发行日期和发行物待核实。
- 部分原仓文档标注2026-09-21；该时间按作者文档日期保存。建库、提交、文档日期和首次公开分别记录。

## 许可、AI与上游

[完整固定树](https://api.github.com/repos/mehaotian/xuyu/git/trees/2974fd20dc0b0a91eab3a83c063c21a8527a897b?recursive=1)共109项、80文件，truncated=false。固定树内许可正文待核实，[风险文档](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/docs/00-%E9%A1%B9%E7%9B%AE%E8%AF%84%E5%AE%A1/%E9%A3%8E%E9%99%A9%E4%B8%8E%E5%BE%85%E5%86%B3%E4%BA%8B%E9%A1%B9.md)把许可证列为待决项，API许可值为null。采用“许可待核实”而保持公开可读与许可状态分别表述。

[参照项目分析](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/docs/00-%E9%A1%B9%E7%9B%AE%E8%AF%84%E5%AE%A1/%E7%AB%9E%E5%93%81%E4%B8%8E%E5%8F%82%E7%85%A7%E9%A1%B9%E7%9B%AE%E5%88%86%E6%9E%90.md)将Python、Go、Rust、易语言、文言和MoonBit列为参照或灵感，并讨论工具链方向。该资料支持参照关系；具体源码继承、兼容性和上游授权待核实。[技术路线](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/docs/02-%E6%8A%80%E6%9C%AF%E8%AE%BE%E8%AE%A1/%E6%8A%80%E6%9C%AF%E6%9E%B6%E6%9E%84%E4%B8%8E%E5%AE%9E%E7%8E%B0%E8%B7%AF%E7%BA%BF.md#L1-L68)将Go列为当前实现语言，Native、WASM及LLVM为文档规划范围。

固定树含AGENTS.md与.cursor/rules。[AGENTS.md](https://github.com/mehaotian/xuyu/blob/2974fd20dc0b0a91eab3a83c063c21a8527a897b/AGENTS.md)含AI生成注释和协作文档要求，规范亦讨论IDE建议与确定性编译边界。实际AI开发参与、模型、生成比例和人工复核范围待核实。

## 已完成与剩余字段

已完成：语言身份、已实现“设置”关键字、两行连续原例、Go前端和解释链、0.0.1-dev与v0.1分层、提交与建库时间、最新head、参照关系、许可待决状态。

待核实：独立运行；完整v0.1实现；正式发行与首次公开日；许可正文；自然人身份与贡献分工；AI实际参与；一元负号、整数溢出策略和Unicode边界的后续规则；具体源码继承。

本轮已达到分类停止条件。提供xuyu-entry.json作为lang-096正式条目草案。Issue22其余候选保持原有独立研究范围。

## 前置资料

已读百科AGENTS.md、Issue22正文及6条评论、固定data/languages.json、round-7-language-pending.json、round-25-issue-followup.md。现有lang-042为规范与例程设计阶段收录先例；XuYu此次额外具备当前中文赋值关键字实现证据。

- [百科写作规则](https://github.com/yuyan-lang/chinese-programming-languages/blob/f543ed92b06889da9e924511505858d8f239166b/AGENTS.md)
- [Issue22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)
- [初始候选记录](https://github.com/yuyan-lang/chinese-programming-languages/blob/f543ed92b06889da9e924511505858d8f239166b/research/2026-10-10/round-7-language-pending.json)


## 本轮范围、检索与复核

本轮按旧Issue22的XuYu线索定向读取GitHub原仓，重点时间范围2026年9月，核验日2026-10-12。名称排重使用XuYu、xuyu、中文语言实验器及mehaotian原仓标识，已对照当前95项语言与开放议题。读取README、规范、原例、Go源码、测试正文、完整树、两条提交及版本端点。资料覆盖限原仓当前可达历史、关联文档和既有百科记录；站外历史、未公开发行、真实作者身份及非索引视频仍有遗漏风险。

主审逐字核对原始两行程序与末尾换行，独立阅读完整词法、赋值解析与AST求值源码，确认“设置”属于已实现词元。新发现线索0项，旧候选核实收录1项，已有正式条目修改0项；收录后目录96语言／10内核。现有95项资料与内核目录原样保留。
