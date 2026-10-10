# 第十一轮：中文社区、论文与历史目录轮换

核验日期：2026-10-10（UTC）；本支线实际研究时段19:30—19:38 UTC。基线：[b8bced915e093ccdfde6b32804f7bd2b4c6a0786](https://github.com/yuyan-lang/chinese-programming-languages/tree/b8bced915e093ccdfde6b32804f7bd2b4c6a0786)，71项语言、8项内核。

## 结果与计数

本轮深入2组新项目：折言（Origami）的中文词元扩展、Rule DSL Core（blizzard1413）。建议正式新增1项，新增待核实候选1组。折言的当前版本、许可等待补字段另外保存，独立新候选计数为1。

- data/languages.json中的lang-073：1项无ID建议条目
- round-11-community-pending.json：折言字段补证1项、Rule DSL Core新候选1项
- 固定来源审阅材料：折言历史／当前固定源码及注册移除差异的审阅副本
- 公开议题排重记录：开轮18个开放Issue正文及48条评论，用于全量排重

研究采用普通公开网页及GitHub只读接口，配合本地研究文件整理。项目代码、脚本和二进制保持静态阅读状态。

## 开轮排重

读取根AGENTS.md全文及完整递归目录，取得71项languages.json全部字段。以第十轮汇总、discovery、search、bilibili、kernels、existing、issue22日志和所有开放Issue正文／评论进行名称、别名、账号与原仓地址排重。

开放Issue共18项：#1、#3、#4、#5、#11、#13、#16、#18、#19、#22、#23、#24、#26、#27、#29、#31、#32、#33；评论共48条。

php-any/origami、折言、blizzard1413/dsl及Rule DSL Core在本次排重语料中均为新对象。Issue #5历史目录线索保留旧线索口径；言叶系列、墨言、易码、自然派、CNSH及LightLang等检索命中按既有对象处理。GitCode LightLang的频次受限状态沿用，原仓保持原样。

## 1. 折言：历史默认中文词元扩展

### 原作者社区链

- [《大家愿意中文编程吗》](https://www.v2ex.com/t/1149176)，V2EX账号2024，页面日期2025-08-01。主帖先展示NewKeyword／NewOperator注册方式，再给出完整中文程序；第31条回复由同一OP直接链接php-any/origami。
- [《使用go和仓颉重构了整个PHP》](https://www.v2ex.com/t/1149147)，同账号、同日，附言直接给出项目仓库。帖子将折言定位为融合型脚本语言。标题中的仓颉路线按作者表述保存，本轮实际核对Go实现。

四行完整原例：

```text
函数 用户(名称) {
  输出 名称;
}
用户("张三");
```

主代码出处为[2025-08-01固定README第179—182行](https://github.com/php-any/origami/blob/e6e8b403b6d107e2d694639ffa9786c4277f3da2/README.md#L179-L182)。原始空格、换行及引号保留；同一程序已见2025-07-30根提交。

### 默认启用与实际执行链

历史固定提交：e6e8b403b6d107e2d694639ffa9786c4277f3da2，时间2025-08-01T01:06:40Z，递归树458项、truncated=false。

1. [origami.go第34—46行](https://github.com/php-any/origami/blob/e6e8b403b6d107e2d694639ffa9786c4277f3da2/origami.go#L34-L46)在创建解析器前注册输出→ECHO、函数→FUNC，以及逗号、分号、乘除号别名。
2. [token/ext.go](https://github.com/php-any/origami/blob/e6e8b403b6d107e2d694639ffa9786c4277f3da2/token/ext.go#L3-L17)向TokenDefinitions追加别名。
3. [lexer/lexer.go第45—73行](https://github.com/php-any/origami/blob/e6e8b403b6d107e2d694639ffa9786c4277f3da2/lexer/lexer.go#L45-L73)逐个读取词元定义，以rune匹配树识别符号。
4. [parser/parser.go第85—145行](https://github.com/php-any/origami/blob/e6e8b403b6d107e2d694639ffa9786c4277f3da2/parser/parser.go#L85-L145)读取源文件、分词及构造Program；[all_parser.go第24、30行](https://github.com/php-any/origami/blob/e6e8b403b6d107e2d694639ffa9786c4277f3da2/parser/all_parser.go#L14-L34)将FUNC、ECHO交给相应解析器。
5. [FunctionParser](https://github.com/php-any/origami/blob/e6e8b403b6d107e2d694639ffa9786c4277f3da2/parser/function_parser.go#L22-L71)构造函数AST并加入VM函数表；参数解析器有无美元符号的标识符分支。
6. [runtime.LoadAndRun](https://github.com/php-any/origami/blob/e6e8b403b6d107e2d694639ffa9786c4277f3da2/runtime/vm.go#L121-L132)解析文件并创建上下文；[Program.GetValue](https://github.com/php-any/origami/blob/e6e8b403b6d107e2d694639ffa9786c4277f3da2/node/node.go#L31-L58)逐条执行AST；[EchoStatement](https://github.com/php-any/origami/blob/e6e8b403b6d107e2d694639ffa9786c4277f3da2/node/echo.go#L22-L38)求值后调用fmt.Printf。

分类采用“融合脚本语言的中文词元扩展／Go AST解释实现（历史默认启用阶段）”。中文扩展与英文语法使用同一解释体系，同一项目计1项。PHP兼容范围、上游借鉴及独立运行继续核实。

### 精确历史变化

[根提交b6486d85…](https://github.com/php-any/origami/commit/b6486d8583598c420cdb3d42e9ae94217d451634)时间2025-07-30T16:34:12Z，parents为空，含原例和入口注册。仓库created_at=2025-05-28T07:04:16Z；两者独立记录，准确首次公开时间待核实。

[2025-08-15提交5015c8d0…](https://github.com/php-any/origami/commit/5015c8d005d94656e399f1a670da3bbd41c99490)时间2025-08-15T10:36:52Z，标题“add: lsp插件”，准确删除origami.go中的中文／全角注册块及token导入。这一差异确立默认注册启用阶段的边界。

当前固定头提交49725fc86250f46515b1d5f0e49ed2c71da5c401，时间2026-08-13T07:55:28Z，递归树2827项、truncated=false。[README_CN.md](https://github.com/php-any/origami/blob/49725fc86250f46515b1d5f0e49ed2c71da5c401/README_CN.md)仍列中文关键字，[token/ext.go](https://github.com/php-any/origami/blob/49725fc86250f46515b1d5f0e49ed2c71da5c401/token/ext.go)仍有注册接口。当前zy.go、cmd/root.go和cmd/runtime.go另行核对；当前发行物启用方式及官方使用说明待核实。

当前代码搜索NewKeyword有2项：接口本身及Qoder文档。历史默认注册移除依据明确差异；当前使用情况继续按源码与文档分层。

### 作者、版本及许可

- 维护组织php-any；根及当前头提交署名ctfang，GitHub关联cyz-home。V2EX账号2024与个人账号进一步对应待核实。
- 历史go.mod为Go1.23.6，当前为Go1.25.0，均记为实现工具链要求。
- 发行列表显示v0.0.4发表于2025-08-16，v1.0.5-symfony-support发表于2026-03-26T03:27:13Z。语言项目发行、LSP及team-navigation应用分别识别；中文扩展的发行附件范围待核。
- 历史及当前README均声明MIT，GitHublicense元数据为null。完整许可正文、版权署名与依赖适用范围待核。
- 当前树中Cursor／Claude／Qoder配置及OpenAI扩展按工具与模块线索记录，AI参与比例继续待原作者资料核实。

## 2. Rule DSL Core：原仓文档与包目录候选

原仓：[blizzard1413/dsl](https://gitee.com/blizzard1413/dsl)。Go模块与包目录均直接对应同一路径。

Gitee原页可读显示名blizzard、main、46次提交、3标签（v1.0.0、v1.1.0、v1.2.0）、MIT及README。头部v1.2.0提交链接给出完整SHA：[199a2bac8e5b5dcf68be1e87756b4764b3c74e40](https://gitee.com/blizzard1413/dsl/commit/199a2bac8e5b5dcf68be1e87756b4764b3c74e40)。提交正文与绝对时间待核实。

README将项目定位为Go规则引擎库，采用JS／TS风格语法，支持中文规则及控制流，列ANTLR4、Visitor、AST、求值器及引擎层。原页提供中文折扣规则，包含规则、如果、否则如果和返回。Go官方包目录保存的原项目[中文示例README](https://pkg.go.dev/gitee.com/blizzard1413/dsl/examples/05-chinese-keywords)另有完整问候规则：

```text
export 规则 问候 = (名字: string): string => {
    返回 "你好，" + 名字 + "！";
}
```

该三行以搜索索引可读项目原文转录，原文件字节和固定提交对应待核实。包目录还提供[parser接口](https://pkg.go.dev/gitee.com/blizzard1413/dsl/parser)与[AST类型](https://pkg.go.dev/gitee.com/blizzard1413/dsl/parser/ast)说明。语言名称RuleDSL和库名Rule DSL Core按同一项目组保存。

### 日期、版本与边界

- 包目录v1.2.0显示Published Jan 8, 2026。
- 原README记v1.0.0完成时间2026-01-06，这是作者完成日期声明。
- 仓库创建、根提交、标签绝对时间及准确首次公开日期待核。
- 包目录显示版本更新提示；原仓README、可见标签与实际最新发行分层核实。
- 中文表格出现“循环”对应for，而部分原例使用“对于”；否则如果、中文逻辑词和英文类型／库名的具体覆盖范围待实际语法文件核对。
- 原仓.kiro/specs只作为开发工具线索，AI使用范围待核。
- 性能数字、测试覆盖和“完成”徽章采用作者文档声明层级，运行证据待核实。

### 访问状态与正式收录条件

Gitee根页可读。提交、blob和raw正文请求返回Cache miss或工具不可访问；Go包目录多个直接open也返回Cache miss，搜索索引保留原项目说明。当前证据足以保留一个中英双关键字规则DSL候选。固定RuleDSL.g4、解析／求值源码、连续原文件、完整许可及版本时间补齐后再确定正式条目。

## 检索平台、时间窗与精确词组

目标窗口为2024—2026，截止2026-10-10。年份数字是检索词，结果中的作者时间、抓取时间、包版本日期和相对日期分别核验。本轮读取工具返回首组搜索结果；并按原链接深读以上2组项目。

### 中文社区轮换

- site:v2ex.com "中文编程" "2025"
- site:linux.do "中文编程语言"
- site:zhihu.com "中文编程语言" "2026"
- site:oschina.net "中文编程" "2025"
- site:linux.do "中文" "解释器"
- site:v2ex.com "中文" "编译器" "2026"
- site:blog.csdn.net "自制" "中文编程语言"
- site:oschina.net "中文编程语言"
- site:linux.do "中文编程" "自制"
- site:v2ex.com "中文编程语言" -为什么 -愿意
- site:blog.csdn.net "中文编程语言" "2026"
- site:zhihu.com "中文编程语言" "自制"
- "中文编程语言" "2026"（域名限定blog.csdn.net）
- "中文编程语言"（域名限定linux.do）
- "中文编程语言" "开源"（域名限定oschina.net）
- "中文编程语言" "自制"（域名限定zhihu.com）
- "中文编程语言" "2025" "开源" -易语言 -文言 -仓颉 -凹语言 -光明 -段言 -豫言
- "中文编程语言" "2024" "自制"
- "中文编程" "2026" "我写"
- "中文" "编程语言" "2026" "github" -site:github.com -site:linux.do -site:wa-lang.org -site:bilibili.com -site:csdn.net -site:gitcode.com -site:tencent.com
- "中文编程" "2026" "新语言" -site:bilibili.com
- "中文编程" "2025" "解释器" -site:github.com -site:linux.do -site:v2ex.com
- "中文编程" "自制" "2025" -site:bilibili.com -site:csdn.net -site:gitcode.com
- "中文编程" "AI" "我" "开源" site:v2ex.com
- "中文" "编程语言" "自制" site:linux.do
- "中文关键字" "2026" -site:bilibili.com -site:github.com -site:gitcode.com

### 身份、源码及排除项

- "Basic4AI"、Basic4AI、"Basic4AI" "中文"
- "blizzard1413" "dsl"
- "php-any" "中文"
- site:pkg.go.dev/gitee.com/blizzard1413/dsl/parser "RuleDSL"
- site:pkg.go.dev/gitee.com/blizzard1413/dsl "05-chinese-keywords"
- "gitee.com/blizzard1413/dsl" "lexer"
- "blizzard1413/dsl" "2026-01"
- "Origami" "折言" "中文" "2025"
- "blizzard1413" "DSL" "Kiro"

GitHub仓库搜索Basic4AI用于同名初筛；直接读取1033020837/Basic4AI README，内容为机器学习／深度学习／NLP学习笔记。中文BASIC语言的转载介绍需要另一条原作者证据链，保留为搜索噪声观察，本轮独立候选计数为0。PandaCoder命中为IDEA插件说明；pyzh命中为中文函数模块；二者仅做初筛。极语言、考鼎码及中文自动化测试帖子作为后续轮换入口，语法／作者／实现尚未深入，计数保持0。

GitHub折言原生只读请求：
- 公开仓库元数据、main提交、当前与2025-08-01完整递归树
- 固定README、入口、注册、词法、解析、AST及运行时文件
- 公开Releases集合（16项）、标签集合请求
- 当前代码搜索NewKeyword，返回2项
- 提交搜索“中文 repo:php-any/origami”“keyword repo:php-any/origami”，返回空集合
- 2025-08-02之前提交列表用于定位原帖同期快照
- origami.go与token/ext.go文件历史
- 根提交、2025-08-15注册移除及2026-05入口迁移差异

标签集合请求由GitHub只读接口以端点不支持返回400；发行结论采用已取得的Releases集合，标签详情待补。

### 论文与历史目录轮换

- "汉语程序设计语言" 论文 关键字
- "中文程序设计语言" "论文" "2025"
- "中文" "程序设计语言" "学报" "设计" -代码 -教程
- 直接读取[program-in-chinese/overview原目录](https://github.com/program-in-chinese/overview)

学术命中主要为编译理论、英文语法语言、既有汉语编程专利及一般教学文章；中文论文和中文摘要作为资料语言记录。历史目录Klang、CTS、圈3／4／5、孔Caml、Z语言、文言Perl、亲密数、标天汇编、丙正正与O语言已见Issue #5，继续采用旧线索口径；本轮深入资源投入于上述2个2025—2026项目。

## 覆盖与遗漏风险

1. 社区通用关键词被易语言争论、AI提示词、中文标识符、工具插件和重复镜像主导，原作者低关注项目可能排在后续结果。
2. CSDN／知乎／开源中国部分检索返回转载、作者列表或旧文章的推荐时间；标题自述、文章日期和真实项目日期分别记录。
3. Basic4AI同名初筛说明搜索说明与真实仓库可能存在语义错配；原作者材料优先。
4. Gitee根页可读与文件正文不可读并存，包目录索引抓取时间与当前仓库状态存在时间差，固定版本对应继续待核。
5. 折言存在明确默认中文注册移除。历史例程、当时启用状态、当前接口与发行附件的能力按阶段区分。
6. 本轮项目代码保持只读，运行、构建、兼容性、性能及AI贡献比例均按实际证据层级记录。

