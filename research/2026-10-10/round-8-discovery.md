# 第八轮：Gitee／GitCode与中文历史资料发现

核验日期：2026-10-10（UTC）。实际检索与核验时段：18:00—18:06 UTC。基础目录提交：48e7a753e30e8059b0c617a1c38f5385c54e3b4f。

## 范围与计数

本组新增发现2组，深入范围限这2组。正式条目建议1项：rzc（i18n-rust中文方言）。待核实候选1项：墨言（moyan_compiler）。GitCode与GitHub的i18n-rust入口合并为一个项目；中文语言包、rzc命令行、LSP及VS Code扩展作为同一项目组件记录。

已读根AGENTS.md、data/languages.json的61项目录、round-7-discovery.md，以及12个开放Issues正文和31条全部评论。开放Issue为1、3、4、5、11、13、16、18、19、22、23、24。名称、别名、作者账号和原始仓库链用于去重。既有PB、龙语言、灵创语言与Issues #22—#24的候选沿用既有记录。豫言条目维持原样。

使用普通网页搜索、GitHub只读接口和dot云公开浏览器。工作范围为原始文档、源码与发行元数据的静态阅读。项目构建、运行、测试和第三方附件内部核验均待核实。

## 正式条目建议：rzc（i18n-rust中文方言）

- 发现入口：[GitCode tan80/i18n-rust](https://gitcode.com/tan80/i18n-rust)。
- 原始README直接确认[GitHub liuqiTan80/i18n-rust](https://github.com/liuqiTan80/i18n-rust)与上述GitCode入口双平台同步维护。
- 固定main：ef07fb31b911a64ce0875738de8be641b3a2be91，作者及提交者署名tan80，日期2026-09-29T09:32:09Z。
- 仓库创建2026-08-15T07:13:24Z，pushed_at为2026-10-07T13:47:13Z；2026-10-10所见0星、未归档。日期字段各自记录。
- 递归树630项，truncated=false。源码为Rust工作区，包含engine、cli和lsp。
- [完整连续中文原例](https://github.com/liuqiTan80/i18n-rust/blob/ef07fb31b911a64ce0875738de8be641b3a2be91/README.md#L28-L32)来自README，包含“函数 主函数”“让 可变”和“打印行!”。
- [中文语言包](https://github.com/liuqiTan80/i18n-rust/blob/ef07fb31b911a64ce0875738de8be641b3a2be91/crates/engine/lang-packs/zh/keywords.toml)确认中文关键字、类型、控制流、宏和特殊值映射；[语言包元数据](https://github.com/liuqiTan80/i18n-rust/blob/ef07fb31b911a64ce0875738de8be641b3a2be91/crates/engine/lang-packs/zh/lang_info.toml)注明中文、zh扩展名及1.0版本。
- [词法器](https://github.com/liuqiTan80/i18n-rust/blob/ef07fb31b911a64ce0875738de8be641b3a2be91/crates/engine/src/lexer.rs#L112-L348)使用rustc_lexer::tokenize，按词元类型和上下文查映射表。
- [转译管线](https://github.com/liuqiTan80/i18n-rust/blob/ef07fb31b911a64ce0875738de8be641b3a2be91/crates/engine/src/lib.rs#L172-L264)串接词法、模块路径、别名和源码位置映射。
- [CLI Run分支](https://github.com/liuqiTan80/i18n-rust/blob/ef07fb31b911a64ce0875738de8be641b3a2be91/crates/cli/src/main.rs#L318-L386)实际加载映射、写入Rust转译产物并按项目情况选择直接rustc或Cargo run。
- [Cargo.toml](https://github.com/liuqiTan80/i18n-rust/blob/ef07fb31b911a64ce0875738de8be641b3a2be91/crates/cli/Cargo.toml)列rzc 0.8.3；[MIT许可](https://github.com/liuqiTan80/i18n-rust/blob/ef07fb31b911a64ce0875738de8be641b3a2be91/LICENSE)署名i18n-rust项目团队。
- [v0.8.3](https://github.com/liuqiTan80/i18n-rust/releases/tag/v0.8.3)发行时间2026-09-29T09:38:18Z，标签指向同一固定提交。附件i18n-rust-0.8.3.vsix为1,008,755字节，平台digest为sha256:b3682cff0e17ecbcc391d1f8551f9235817c1d8fbaa8a566ef3044fc74870188，另有SHA256SUMS。附件本体待核实。
- [v0.3.0](https://github.com/liuqiTan80/i18n-rust/releases/tag/v0.3.0)发行时间2026-08-16T06:05:47Z，可作为“至少当时已有公开发行”的证据。最早公开日继续待核实。
- [历史0.4.0包元数据](https://docs.rs/crate/i18n-rust-lsp/0.4.0/source/Cargo.toml)索引曾使用GitCode tan80/zrRust；当前源码注释仍有zrRust名称。名称迁移具体日期待核实，当前rzc与i18n-rust的同项目关系已由固定README确认。

### 分类与边界

按Rust中文方言／词元级源到源转译工具收录。中文模式和其他自然语言包共用同一套引擎。源程序经转译进入官方Rust工具链，语言设计和运行实现的依赖关系如实保留。

Issue #22已记录bo333/Chinese-Rust-Syntax-Design-and-Transpilation-Tool。本轮项目具有tan80／liuqiTan80作者链、完整实现目录和发行记录，按自身原始证据独立归档；两项目之间的代码继承关系待核实。

README描述AI辅助库名称映射等功能，开发过程中的AI参与范围继续待核实。完整Rust语义覆盖、跨平台行为、教学效果、声明的性能以及各个测试结果按作者说明和独立验证分层记录。

原例选择README中的可变绑定程序。docs/demo/samples/main.zh包含不可变变量的再赋值，是错误诊断演示材料；其上下文与README主例各自保留。

## 待核实：墨言（moyan_compiler）

原项目：[moyan_lang/moyan_compiler](https://gitcode.com/moyan_lang/moyan_compiler)。普通搜索首次命中该仓库，目录及全部开放Issue语料中未检出moyan、墨言或该仓库地址。

dot云公开浏览器在独立标签实读：
- 组织名“墨言编程语言”。
- 项目说明自述Rust实现、中文语法、函数式／面向对象／异步编程，AI开发和玩具项目定位。
- 当前1星、309提交。搜索索引较早快照为305提交。
- 默认master所见头提交[11e0367837834df1f2fb5655a494b4fda9cdec3d](https://gitcode.com/moyan_lang/moyan_compiler/commit/11e0367837834df1f2fb5655a494b4fda9cdec3d?ref=master)，提交账号amor2022，消息“feat: 完成P2第一批功能迭代”。
- 根页侧栏列[v0.1.0](https://gitcode.com/moyan_lang/moyan_compiler/releases/v0.1.0)，显示2025年12月16日发布。
- 页面“创建于8月26日”的年份与字段语义待核实；项目首发时间继续待核实。

普通网页直接打开根页、组织页、README候选路径、tree/master与release页返回Internal Error。云浏览器补足可见项目头部、提交和版本侧栏；root及tree/master文件表持续显示加载占位。进入原页提供的发行入口后，正文先显示loading，后续DOM读取出现Runtime.evaluate timed out和Page.getFrameTree timed out。

待核实重点：原始连续中文程序、词法／解析规则、实际Rust实现入口、固定文件正文、原作者身份、v0.1.0发行详情、许可及首发沿革。以项目页自述与可读元数据保留pending。

检索同时命中skywalk163开发记录的转载，包含“墨言moyan”名称。转载按名称消歧线索记录，其与moyan_lang的作者、实现和迁移关系待核实；本轮数量保持一个墨言候选。

## 检索平台、关键词与范围

### 普通网页搜索

以下28个查询均于2026-10-10执行。每次使用搜索工具默认返回的首组结果，采用4查询批次和long响应。Gitee及GitCode通过site限定的公开网页索引检索；平台原生全库搜索与完整翻页范围待后续扩展。

- `site:gitee.com "中文编程语言" "2026"`
- `site:gitcode.com "中文编程语言" "AI"`
- `site:gitee.com "中文编程" "2025" "AI"`
- `"中文编程语言" "论文" "语法"`
- `"moyan_compiler" github`
- `"i18n-rust" "tan80"`
- `site:gitee.com "中文" "解释器" "2025" -UID9622 -grasspy -cpython`
- `"中文程序设计语言" "论文" 编译`
- `"moyan_compiler"`
- `"moyan_lang" 中文`
- `"汉语" "程序设计语言" "1985"`
- `"汉语程序设计语言" 论文`
- `site:gitcode.com/moyan_lang/moyan_compiler "函数"`
- `site:gitcode.com/moyan_lang/moyan_compiler "墨言"`
- `site:gitee.com "moyan" "编程"`
- `site:gitcode.com "moyan" "2026"`
- `"moyan_lang"`
- `"moyan" "中文编程"`
- `"墨言" "编程语言"`
- `site:gitee.com "中文语法" "AI"`
- `site:gitee.com "中文编程语言" "2024" -uid9622 -zhishi`
- `site:gitee.com "中文关键字" "AI"`
- `"汉语程序设计语言" "数摞" "王"`
- `"中文程序设计语言" "实验" 论文 -豫言`
- `site:gitee.com "中文编程语言" "AI" -uid9622 -longhun -zhishi`
- `site:gitcode.com "中文编程语言" "玩具"`
- `"汉语程序设计语言" "沈志斌"`
- `"中文" "领域专用语言" "论文" 语法`

2024、2025、2026以查询词出现，属于发现过滤线索；网页索引的抓取时间、仓库创建日和语言首发日分别处理。本轮深入选择为两个GitCode发现入口：其中i18n-rust经作者互链转向GitHub固定源码；墨言经dot云公开浏览器补核元数据。

### GitHub只读搜索与目录核验

- 仓库搜索：`moyan_compiler`，per_page=20；返回0项。
- 百科开放议题：`repo:yuyan-lang/chinese-programming-languages is:issue is:open`，topn=100；返回12项，逐项读取全部评论，共31条。
- 百科固定文件：AGENTS.md、data/languages.json、research/2026-10-10/round-7-discovery.md和round-7-language-pending.json。
- i18n-rust：仓库元数据、commits/main、根contents、固定递归树、所需固定文件、releases集合及git/matching-refs/tags/。Releases返回23项、标签27项。此处只以本轮直接核对的版本建立结论。
- 豫言原有条目保持原样。

### 中文历史与论文方向

历史检索命中[汉语编程单片机原专利CN1093663C](https://patents.google.com/patent/CN1093663C/zh)及其1995年公开文献关联，索引包含汉语程序设计语言、词典和数摞说明；还命中[元易达项目可行性报告](https://www.uml.org.cn/yyal/yyaL25.htm?artid=221)，参考书作者为沈志斌。以上作为下轮历史来源入口，当前仅完成发现级阅读，原始连续程序与完整版本关系待补；本轮新增数量仍为上述2组。

论文方向的宽查询出现自然语言处理、中文授课的程序设计课程和通用DSL论文，中文关键字程序证据需继续筛选。[CCF PL-China 2026会议程序](https://pl.cs.pku.edu.cn/pl-china-2026/program/)中出现中文状态转移矩阵的建模与验证方向，本轮保留为检索范围说明。

## 遗漏风险与证据层级

- 网页检索覆盖受索引、语言、精确词、排序和首组结果限制。Gitee小仓库、登录后内容及未索引项目仍有遗漏风险。
- “2024—2026”关键词会匹配正文、年份和转载时间；原始发布元数据单独核对。
- GitCode页的自动生成简介可能混入搜索摘要；技术结论优先使用原README、源码或明确作者自述。
- 本轮两项中，rzc已取得固定语法原例及实际转译入口；墨言的语法与源码正文继续待核实。
- 低星数按核验时刻的平台元数据记录。项目规模、质量和维护状态各自采用相应证据。
- 同名中文Rust工具、同作者阶段名和跨平台镜像分别去重。历史目录、转载和索引只提供发现入口。
- 工具调用保持只读；三个交付文件为本地研究资料。

