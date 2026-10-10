# 第十四轮：言语言与言叶系列旧线索补证

核验日期：2026-10-10（UTC）。
百科基线：[46734fc65a9a5da4cdc230c78c9f835134973e9a](https://github.com/yuyan-lang/chinese-programming-languages/tree/46734fc65a9a5da4cdc230c78c9f835134973e9a)，77项语言、8项内核。

## 结果与计数

本分项形成言语言（Yán）正式条目1项，分类为实验性中文函数式语言／Python源码转译实现。原始中文程序、专用词法与解析器、Python生成执行链及根历史取得补证。

- 真正新发现：0。
- 旧候选补证正式条目增量：1。
- 言叶、文言心及言的名称关系：沿用Issue #5同组研究，正式对象限定skywalk163/yan。
- 言叶、文言心的独立实现身份以及与段言／光明的具体源码继承：继续待核。
- 同账号其他仓库与网页列出的名字：作为作者范围及名称消歧资料保存。


本轮采用GitHub公开只读接口、普通网页与公开搜索索引，完成静态资料核验及研究资料整理。独立运行与自举结果待核实。

## 已读前序资料

- [根AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/46734fc65a9a5da4cdc230c78c9f835134973e9a/AGENTS.md)。
- [完整77项语言目录](https://github.com/yuyan-lang/chinese-programming-languages/blob/46734fc65a9a5da4cdc230c78c9f835134973e9a/data/languages.json)，重点排重lang-008段言、lang-009光明及全部已有名称／关系。
- [第十三轮总日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/46734fc65a9a5da4cdc230c78c9f835134973e9a/research/2026-10-10/round-13.md)及既有条目分项记录。
- [Issue #5正文与全部3条评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/5)，第六轮已定位言原仓，后续评论分别补TRAE与易码。
- [第六轮既有条目日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/46734fc65a9a5da4cdc230c78c9f835134973e9a/research/2026-10-10/round-6-existing.md)，沿用段言／光明已核谱系及言叶系列待核范围。

## 固定身份与分层时间

原仓：https://github.com/skywalk163/yan
固定main：815353dfe80dbae46ac2e0dabe5e9f447559bb78。
当前提交：2026-06-08T12:31:52Z；pushed_at：2026-06-08T12:32:17Z。
GitHub created_at：2026-06-02T10:55:57Z。
仓库ID：1257085395；fork=false。
当前完整递归树805项，739个blob，truncated=false。
README blob：122c834e1782730b90705f722bbb210d4af50ecb。

commits查询使用固定sha、per_page=100，返回61条；所有父提交SHA均在该结果中，唯一空parents根为[fad2762a6392c3af98655f3ac3d4eccbefde47ef](https://github.com/skywalk163/yan/commit/fad2762a6392c3af98655f3ac3d4eccbefde47ef)，时间2026-05-01T13:55:27Z。61条提交的author.name均为skywalk163。GitHub owner与Git署名按各自来源记录，实名及贡献分工待核。

根树18项，16个blob，包含README、design.md、plan.md、Python转译设计、词法器、解析器、节点、生成器、运行时和4份.yan例程。根README标题为“言 (Yán)”并含函数与管道原例。根yan/main.py第26—65行已串联Lexer、Parser、PythonCodeGen与exec。由此将Git历史起点补到五月。

[2026-05-05的三语言设计规范](https://deepseek.csdn.net/6a059cdf662f9a54cb746b14.html)署名天马行空skywalk，页面显示20:47:07；时区待核。设计发表、Git历史、GitHub建库分别记录，最早公开可访问时点待核。

## 原始连续中文程序

采用固定[test_v2_fib.yan第1—10行](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/test_v2_fib.yan#L1-L10)，blob b1375e8c666c7a1e09871d5720fb6aabecc8ec0b。全文141个Unicode字符、10行，完整保留注释、空行、两空格缩进及末尾换行。

程序包含定义斐波那契、函数、如果、小于、返回、递归调用、当时循环及印。正式JSON中code与完整文件原文逐字相等。原例的实际输出、递归执行和循环终止行为待运行核实。

原README仍含定／函／当等早期语句，固定parser.py将当／如果交给条件分支，将当时／当满足交给循环分支。正式展示采用当前树中的v2原例；README当循环与当前规范对应保留待核。

## 词法、解析、生成与运行

固定链接均使用815353dfe80dbae46ac2e0dabe5e9f447559bb78。

1. [yan/lexer.py第47—126行](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/yan/lexer.py#L47-L126)合并预定义中文关键词表。第167行起预扫描用户名称；第278—526行逐行预处理、分词及缩进；生成Token供解析器使用。
2. [yan/parser.py第202—336行](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/yan/parser.py#L202-L336)区分syntax_version，v2默认按缩进处理程序。语句分派包含如果／当／若、遍历、当满足／当时、定义／定、导入、导出、结构等。
3. [第466—590行](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/yan/parser.py#L466-L590)构造While、Define及Lambda节点，定义分支识别函数／函。
4. [yan/codegen.py第40—177行](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/yan/codegen.py#L40-L177)按AST类型生成Python。返回动词显式生成return，内置动词依据函数表及元数生成调用，参数不足分支生成lambda。第179行起处理管道。
5. [yan/runtime.py第362—450行](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/yan/runtime.py#L362-L450)将加／减／乘／除、列表操作、比较、高阶函数、印等映射到Python实现与元数。
6. [yan/main.py第240—349行](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/yan/main.py#L240-L349)串联Lexer.tokenize、Parser.parse、process_adverbs、模块导入、PythonCodeGen.generate和Python eval／exec。此链支持“Python源码转译实现”分类。
7. [yan/__init__.py第35—69行](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/yan/__init__.py#L35-L69)提供compile与run便捷入口；非Python目标异常分支回退生成Python。入口间的环境准备及行为一致性待核。
8. [yan/antlr/main.py](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/yan/antlr/main.py)另有ANTLR生成Lexer／Parser、ASTBuilder和Python生成链。
9. [yan/codegen_multi.py](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/yan/codegen_multi.py)另列JavaScript与WebAssembly文本生成器。各目标覆盖及输出可执行性待核。

执行路径的独立运行、CLI导入路径、模块接口、v1兼容、复杂样例与跨平台结果继续待核。分类依据为实际读取的源代码结构。

## 自举、版本、许可与AI

### 自举资料

仓库保存selfhost/lexer.yan、parser.yan、codegen.yan及compiler.yan。读取[bootstrap_v3.py第58—145行](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/yan/selfhost/bootstrap_v3.py#L58-L145)，其中包括用Python种子编译器生成后续编译器、执行生成Python和比较两阶段输出的流程。报告的2026-05-16自举成功、Python代码比例、校验值及测试通过数按作者自述保存。可复现自举、生成物真实性及完整语法范围待独立核实。

### 四类版本标记

- yan/__init__.py第9行：0.5.0。
- yan/README.md第3行徽章：0.3.0。
- yan/CHANGELOG.md首个版本段：v0.3.1，2026-05-19。
- 根README：2026-05-28语法v2；提交[fef95ad93cd223b13e16176ef91591db135ed7b0](https://github.com/skywalk163/yan/commit/fef95ad93cd223b13e16176ef91591db135ed7b0)于2026-05-28T00:05:15Z记载v2实现和迁移工具。

GitHub Releases及git/matching-refs/tags查询均返回空数组。README的语法里程碑、内部版本常量和正式发行分别保存，完整对应与发行物待核。

### 许可

根README第457—459行和yan/README.md第339—341行声明MIT。固定805项完整树中LICENSE／COPYING文件名匹配结果为0；GitHub元数据license=null。条目使用“README声明MIT”，完整许可文本、版权主体及组件授权范围继续待核。

### AI范围

根README第450—453行列明Trae的代码补全、错误诊断和重构建议，以及DuMate的代码审查和功能实现协助。当前子目录README写作Duamte。

[2026-05-23 AI致谢提交404973710b0b539ebaae067c1b75f56ecb241ce6](https://github.com/skywalk163/yan/commit/404973710b0b539ebaae067c1b75f56ecb241ce6)直接增加相同致谢，并说明语法解析、错误处理和性能优化方面的建议。工具协作按作者声明记录；模型、文件贡献、生成比例和人机分工待核。

## 言叶、文言心与段言／光明谱系

1. 言根历史的[design.md第1行](https://github.com/skywalk163/yan/blob/fad2762a6392c3af98655f3ac3d4eccbefde47ef/design.md#L1)直接使用文言心名称。当前[docs/design.md](https://github.com/skywalk163/yan/blob/815353dfe80dbae46ac2e0dabe5e9f447559bb78/docs/design.md#L1-L24)继续保存此材料。文件早期与当前的引号规则曾调整，文言心名称持续保留。
2. CSDN设计规范在同一文档中对照言叶、文言心、言，并说明各自语法特性与设计借鉴。本轮将其确认为设计材料关系，具体实现继承与改名关系继续待核。
3. 言根提交README致谢Lisp、Haskell和Wenyan。该材料提供设计启发来源，源码复用范围继续待核。
4. 言、段言和光明使用同一GitHub owner skywalk163。言历史根为fad2762a（2026-05-01），段言／光明既有共同根为a7fc3a30（2026-06-10）。
5. 本轮重新读取段言根提交a7fc3a30、README、src/keywords.py及完整156项根树，其中137个blob。言根16个blob与言当前739个blob分别对照段言根137个blob，两次整文件哈希交集均为0。该结果限定于三份快照和逐文件完全相同的比较；改写继承与设计迁移继续待核。
6. 段言根README使用段落语法与元数设计，关键词文件包含定义、如果、当、段和返回。相似理念及同作者归属作为关系线索保存。
7. 第六轮已核的段言／光明共同根、2026-08-09改名、2026-08-14双亲合流与2026-08-21迁移公告继续沿用，lang-008与lang-009保留各自现有身份。
8. 言叶与文言心本轮继续作为同组未决设计名，skywalk163/yan作为取得专门实现和原例的单个正式对象。跨项目源码继承范围写入relations与pending。

## 平台、查询与访问状态

时窗：本分项为2024—2026目标范围内的旧线索补证，普通查询采用全年代检索，GitHub历史沿固定分支追溯全部61条至2026-05-01。精确元数据区分UTC时间与网页时区待核时间。

实际平台：
- GitHub：只读仓库、文件、递归树、提交集合、发行和标签集合、代码与仓库搜索。
- CSDN／DeepSeek技术社区：原始三语言设计文档直接读取。
- GitCode／AtomGit：根README链接入口的普通网页索引。
- 普通web搜索：作者与项目精确组合；检索返回的技术栈／51CTO转帖与Ollama辅助模型仅作为消歧背景。

实际关键词：
- GitHub仓库搜索：user:skywalk163；user:skywalk163 yan；user:skywalk163 wen。
- GitHub代码搜索：文言心、言叶，范围skywalk163/yan、duan、light；言语言，范围duan、light。
- web：“skywalk163” “言语言” “段言”；“天马行空skywalk” “言叶” “github”；“言语言” “gitcode.com/skywalk163/yan”；“skywalk163” “文言心”。
- 当前与根树路径核查：lexer、parser、main、codegen、runtime、design、README、CHANGELOG、selfhost、LICENSE、COPYING、requirements。

代码搜索文言心返回空列表；原仓design.md的直接读取取得明确文字。这构成实际观察到的索引遗漏，空搜索结果按可见覆盖范围记录。

GitCode／AtomGit根页面公开索引可读，标62 Commits、Tags0，简介显式注明由AI生成。技术分类采用GitHub固定源码。GitCode commits/main及?tab=md点击均返回Cache miss，较GitHub61条历史多出的提交及平台同步情况待核。

同账号检索返回yan、yanzhi、yanlv、yanpub等仓库；其名称与Issue #5系列的归属继续按单组线索整理。普通搜索另命中同账号段言翻译模型和多语言宣传CMS转帖，均按相关生态材料保存。新语言发现计数保持0。

遗漏风险包括代码搜索索引覆盖、GitCode索引约两个月抓取延迟、动态原页读取失败、跨平台身份互链、首次公开时间、整文件哈希比较对改写继承的覆盖，以及自述能力与固定实现的版本对应。所有未决字段写入pending。

## 静态核验

资料结构、原始引用与连续示例已核对。独立运行结果待核实。
