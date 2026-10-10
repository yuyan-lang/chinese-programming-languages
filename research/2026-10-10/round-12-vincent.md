# 第十二轮：PyCN（Vincent-the-gamer）旧背景首次深入

核验日期：2026-10-10（UTC）。研究时段：20:00—20:07 UTC。百科基线：[9776f45bed00a6f1c9a594eb8142dd5b4428095d](https://github.com/yuyan-lang/chinese-programming-languages/tree/9776f45bed00a6f1c9a594eb8142dd5b4428095d)，73项语言、8项内核。

## 结论、范围与排重

本分项完成Vincent-the-gamer/pycn的独立条目资料，分类为“Python中文方言／Rust AST源码转译工具链”。正式条目资料增量1，新发现项目计数0。项目在第十一轮已作为同名排重背景出现，本轮首次深入原例、核心实现、宿主、历史和发行。

开轮读取根AGENTS.md、固定data/languages.json和data/kernels.json全文、百科完整递归树、round11-pycn研究日志，以及20个开放Issue正文和53条评论。完整目录逐项核对名称、别名、分类和主要来源。Vincent仓库URL在lang-072关系文字和参考中出现；lang-072的独立主体是sunzi334481/PyCn。lang-027主体是PythonDeveloper29042/PythonCN，lang-065主体是LostPEople634/pchinese。上述项目按仓库身份分列。

开放Issue #22初始PyCn候选指向sunzi334481，最近评论确认其已收录为lang-072。Issue #22初始10组现完成分类7组，剩余3组的分类进度与本条保持各自范围。20个开放Issue及53条评论的本次排重结果对应2026-10-10开轮状态。

本轮采用普通网页、GitHub公开文件、目录、提交与发行元数据的静态阅读。程序的安装、构建、测试和运行结果保持独立待核。已取得的原文用于源码文本计数和连续原例比对。

## 固定快照与覆盖

[主干固定快照48acdd141a914fed636ea8c5631db22a4b709a9f](https://github.com/Vincent-the-gamer/pycn/tree/48acdd141a914fed636ea8c5631db22a4b709a9f)与本次main接口返回一致。递归树126项、95个文件，truncated=false，其中有15份examples/*.pycn。保存并阅读43份固定公开原文，覆盖全部14个Rust文件、全部15份.pycn原例、根中英文README、中文入门及使用文档、四份mapping文档、配置、许可证和发布流程。

核心工作区包含parser、pycn、parser-wasm、pycn-dylib、http-server五个crate。默认main历史接口一次返回76条提交，末项为parents=[]的根提交。作者名统计为Vincent-the-gamer 74条、Vince 2条，GitHub作者账号均映射至Vincent-the-gamer。

## 连续中文原例

[examples/函数.pycn第1—7行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/examples/函数.pycn#L1-L7)：

```pycn
定义 是否是质数（被判断的数）：
    如果 被判断的数 小于 二：
        返回 假
    迭代 数一 在 范围（二，整数（被判断的数 取幂 零点五）加 一）：
        如果 被判断的数 取余 数一 等于 零：
            返回 假
    返回 真
```

这是固定原文件中的完整质数判断函数。全文切片与独立start_line=1、end_line=7接口结果逐字一致。缩进、中文数字、中文运算词、全角括号和标点保持原文；调用在同文件后文，运行结果待独立核实。固定中文入门文档也引用该函数。文档配对Python片段中的小写true／false按文档原文保存，实际生成器在parser.rs第1418—1423行输出True／False。

## 实际实现链

### 词法及数字

[parser/src/lexer.rs第4—246行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/lexer.rs#L4-L246)以logos派生Token，声明中英文流程词、布尔空值、运算符和全角标点。Identifier正则使用ASCII字母、下划线及U+4E00—U+9FA5，后续字符另含ASCII数字。完整Unicode标识符覆盖待核实。

[第249—429行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/lexer.rs#L249-L429)逐行计算缩进，空格计1、Tab计8，以栈产生Indent／Dedent；空行与注释行单独处理，行内使用Token::lexer。普通标识符再查关键字及内置名映射，打印、范围、整数、列表等进入BuiltInFunc；魔法方法名称也在该层转换。

中文数字词元由[第408—419行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/lexer.rs#L408-L419)传入chinese_to_digits，再根据结果是否含小数点改为Float或Integer。[chinese_to_digits.rs第1—7行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/chinese_to_digits.rs#L1-L7)使用chinese2digits::take_number_from_string，并返回replaced_text。

### AST与Python文本生成

[parser/src/lib.rs第6—13行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/lib.rs#L6-L13)给出完整入口：lex → parse → ast_to_python，返回String。

[ast.rs第1—52行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/ast.rs#L1-L52)定义Program、赋值、调用、If、For、Return、Def、Class、装饰函数／类、参数展开、容器、索引、切片、导入等节点。[parser.rs第354—506行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/parser.rs#L354-L506)构造函数、条件与迭代节点；[第618—825行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/parser.rs#L618-L825)按递归函数分层解析逻辑、比较、位运算、移位、加法、乘法和一元运算。

[第1128—1562行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/parser.rs#L1128-L1562)将各节点写成Python源码，用四空格生成代码块。第1140—1156行及1512—1515行把中文列表方法和魔法名称映射到Python属性。普通中文变量和函数名称保留；布尔节点生成True／False。这里的自有AST服务于源码生成，运行时对象和执行语义由Python承担。

### 三种执行入口与两种转译包装

1. [pycn/src/lib.rs第9—16行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn/src/lib.rs#L9-L16)：run_pycn调用parse_pycn，转成CString，经PyO3的Python::with_gil与PyModule::from_code执行生成的Python文本。
2. [第18—36、55—84行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn/src/lib.rs#L18-L84)：文件入口读取源码，收集同目录.pycn导入，分别转译到模块名字典。扫描器匹配Program与Import／ImportFrom。
3. [第87—127行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn/src/lib.rs#L87-L127)：创建Python字典，插入sys.meta_path的InMemoryLoader，exec_module调用exec；入口globals设置__name__为__main__后调用builtins.exec。
4. [pycn/src/cli.rs第12—38行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn/src/cli.rs#L12-L38)提供run和--show-python；后者调用[show_generated_python](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn/src/lib.rs#L38-L51)打印生成文本。
5. [pycn-dylib/src/lib.rs第1—19行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn-dylib/src/lib.rs#L1-L19)导出两个C ABI函数，分别包装代码字符串与文件执行。
6. [parser-wasm/src/lib.rs第1—13行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser-wasm/src/lib.rs#L1-L13)公开parsePycn与parsePycnFile，返回Python文本；文件入口使用std::fs::read_to_string。浏览器／Node文件访问与部署环境待核实。
7. [http-server/src/main.rs第19—32行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/http-server/src/main.rs#L19-L32)从POST JSON读取code，经parse_pycn后返回pythonCode。README结构表将其称为代码执行服务；本次保存的HTTP源码职责为转译响应。

## 语法、运行及测试边界

- Token词法声明、AST节点、解析分支和宿主行为分层核验。词法表含While、Try、Except、Finally、Raise、Assert、Global、Nonlocal、With、Match等；当前AstNode循环节点为For，语句解析主要覆盖函数、类、装饰器、条件、迭代、返回、break／continue／pass、导入、赋值和表达式。其余关键字的语句覆盖及完整Python兼容性待核实。
- [lexer.rs第299—420行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/lexer.rs#L299-L420)只在分词结果为Ok时追加词元。[parser.rs第18—53、1116—1124行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/parser.rs#L1116-L1124)在语句解析返回None后递增游标继续。错误诊断、非法字符保真与输入拒绝行为待核实。
- [parser.rs第780—825行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/parser.rs#L780-L825)把乘、除、取余、地板除和取幂放在同一解析循环；[第1392—1406行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/parser.rs#L1392-L1406)直接串接二元表达式。复杂表达式的AST与宿主重新解析语义待独立核实，输出值保持待核。
- 字符串在AST内保存词元原文，[第1417行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/src/parser.rs#L1414-L1424)统一替换中文双引号。f-string内部中文表达式、中文单引号、转义和跨行字符串的完整覆盖待核实。
- 依赖收集遍历Program中的Import／ImportFrom，按同目录模块名拼接.pycn。嵌套导入、包结构、不同目录同名文件、重复执行时的导入钩子及源码定位待核实。
- run_pycn以let _保存PyModule::from_code的Result；文件执行路径多处unwrap。两条入口的错误传播及对外C API初始化方式待独立核实。
- 全部14份Rust源码的#[test]文本计数为4：[parser/tests/test.rs](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/parser/tests/test.rs#L1-L8)的1项打印中文数字转换结果；[bootstrap.rs第304—377行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn/src/bootstrap.rs#L304-L377)的3项覆盖平台标签、路径剥离及标准库抽取清理。它们作为测试源码证据保存，独立执行结果待核实。
- 本次Actions集合共3次发布运行，v1.0.5对应[29677156050](https://github.com/Vincent-the-gamer/pycn/actions/runs/29677156050)结论success，其前两次为failure。固定release.yml中的cargo test文本计数为0。发布工作流成功、静态测试声明和语言执行验证分别记录。

## 运行时打包边界

[pycn/Cargo.toml第7—26行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn/Cargo.toml#L7-L26)默认启用名为static-python的特性，依赖PyO3 0.25.1；构建和标准库引导源文件都配置CPython 3.12.13、python-build-standalone 20260718。

[build.rs第43—108行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn/build.rs#L43-L108)处理外部PYO3_CONFIG_FILE时读取shared并据此生成链接参数；Windows默认分支补库目录并复制DLL；Unix默认分支请求静态libpython链接。发布工作流第324—371行另打包Python共享库。README、发行正文和配置中的“静态”按其来源描述保留，各平台发行物实际链接情况待核实。

[main.rs第5—16行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn/src/main.rs#L5-L16)的调用顺序是prepare_freethreaded_python → setup_python_home → use_cli；setup_python_home在第39—42行取得标准库后设置PYTHONHOME。[bootstrap.rs第32—80行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/pycn/src/bootstrap.rs#L32-L80)查找标准库目录，缺失时触发下载。首次启动顺序、标准库自动获取、纯净机器及Windows路径行为待核实。

## 作者、时间、版本和许可分列

- 作者身份：仓库所有者Vincent-the-gamer；76条默认分支提交均由GitHub归属于此账号，Git作者名为Vincent-the-gamer或Vince。实名、其他参与者及AI开发范围待核实。
- 仓库创建：2025-07-09T07:33:56Z，来自[仓库元数据](https://api.github.com/repos/Vincent-the-gamer/pycn)。
- 根Git提交：[89e11caa8f38038c1a8ef87490655b5a9f975921](https://github.com/Vincent-the-gamer/pycn/commit/89e11caa8f38038c1a8ef87490655b5a9f975921)，作者和提交时间均为2025-07-09T07:34:17Z，保存README、中文质数例、Rust HashMap逐项replace和PyO3执行。
- AST演进：[d0fa1832e304c3a4e75fb5c8b79b42034691ca9e](https://github.com/Vincent-the-gamer/pycn/commit/d0fa1832e304c3a4e75fb5c8b79b42034691ca9e)，作者及提交时间为2025-07-10T07:32:24Z，新增parser crate、AST、logos词法器和手写解析器。
- 固定主干最后Git提交：2026-08-29T09:29:14Z；仓库pushed_at为2026-08-29T09:29:19Z。archived=false。
- 源码版本：[Cargo workspace第3行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/Cargo.toml#L1-L10)为1.0.5，核心crate继承workspace版本。
- 许可：[LICENSE.md第1—21行](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/LICENSE.md#L1-L21)为MIT，版权署名2025-PRESENT Vincent-the-gamer。版权年份与创建、提交、发行时间分别保存。

### 发行记录

2026-10-10读取GitHub Releases集合有6条；git/refs/tags也给出6个标签，均指向commit对象。以下使用published_at：

- v1.0.0：2025-07-09T09:04:21Z；初始发行，标签5f7e9cdbad9cf75dd237851ef65e60e2dff9a4de。
- v1.0.1：2025-07-21T07:15:50Z；发行说明记录本地.pycn模块导入。
- v1.0.2：2025-07-25T06:50:16Z；发行说明记录类、中文数字、位运算、lambda和多变量处理。
- v1.0.3：2025-07-31T08:06:12Z；发行说明记录切片、字典和列表方法。
- v1.0.4：2025-08-20T03:08:55Z；发行说明记录装饰器，含Node/Web WASM附件。
- v1.0.5：2026-07-19T06:55:17Z；标签4f26a4329c9c1100b4036df6310ac8f297fd2ce0，保存Linux／macOS／Windows各x64及arm64的6个裸二进制和6份压缩包。

来源：[首发v1.0.0](https://github.com/Vincent-the-gamer/pycn/releases/tag/v1.0.0)、[最新v1.0.5](https://github.com/Vincent-the-gamer/pycn/releases/tag/v1.0.5)、[发行集合](https://api.github.com/repos/Vincent-the-gamer/pycn/releases?per_page=100)、[标签引用](https://api.github.com/repos/Vincent-the-gamer/pycn/git/refs/tags)。

主干快照与v1.0.5标签对比为ahead 7、behind 0，二者源码版本号同为1.0.5。后续提交涉及build.rs、bootstrap.rs、main.rs和文档等；[固定比较](https://github.com/Vincent-the-gamer/pycn/compare/4f26a4329c9c1100b4036df6310ac8f297fd2ce0...48acdd141a914fed636ea8c5631db22a4b709a9f)作为主干与发行边界依据。附件存在、发布工作流结论、实际二进制内部结构和各平台运行结果分别记录。

## 同名、同源与AI

- GitHub元数据fork=false，当前源码及根提交显示本仓实现的演进。
- sunzi334481/PyCn为Python手写词元转译层；PythonDeveloper29042/PythonCN为全文替换后调用系统Python；本项目当前为Rust logos／自有AST／Python生成／PyO3宿主链。跨项目继承、合作、迁移和改名关系待核实。
- 第十一轮背景已核PyPI同名Pycn 0.0.1（2021-08-20，Wry／Ruoyu Wang）；该包身份单列，其日期用于本项目历史的适用性待核实。
- 固定源码、README及已读文档共43份，76条Git提交消息，以独立词AI及Claude、ChatGPT、Cursor、Copilot、Codex、DeepSeek、Gemini、人工智能、大模型、Co-authored等检索。本轮可归属的AI开发声明、模型、比例和参与范围仍待核实。GitHub页面导航里的Copilot广告及普通英文片段按页面或单词上下文处理。
- 官方文档链接同作者VSCode插件；GitHub账号限定搜索返回pycn和vscode-pycn两仓，编辑器插件按配套工具线索保存，安装与可用性待核实。

## 检索词、平台、时段及风险

检索时段：2026-10-10 20:00—20:07 UTC。网页检索采用不限发布日期；原仓Git记录跨度2025-07-09—2026-08-29；发行发表于2025-07-09—2026-07-19。

实际检索：
- 普通网页：“Vincent-the-gamer” “pycn”；“Vincent-the-gamer” “pycn” AI；“pycn” “Vincent” Claude Cursor；“Vincent-the-gamer/pycn”；“pycn.vincentthegamer.dpdns.org”；“Vincent-the-gamer” “PyCN” “AI”。
- GitHub仓库搜索：pycn user:Vincent-the-gamer，返回本项目和vscode-pycn。
- GitHub公开API：main分支、递归Git树、固定文件、76提交列表、根提交和AST演进提交、Releases、tag refs、主干与发行对比、Issues全部状态、Actions运行集合。
- 百科排重：全部73项语言／8内核、Vincent-the-gamer仓库URL、PyCN／PyCn及同名相关字符串、20个开放Issue和53条评论。
- 固定文本：While／Try／With／Match等词元与AstNode、parse_stmt、parse_pycn、ast_to_python、PyModule、exec、sys.meta_path、#[test]、cargo test、shared、PYTHONHOME及上述AI词。

风险与本次访问结果：
- 固定GitHub文件和API可读；/tags?per_page=100被通用fetch报不支持URL，随后通过/git/refs/tags核得全部6引用。
- 普通网页索引大部分精确查询为空；宽查询有同名无关结果。原仓普通网页open返回旧缓存：63次提交、旧官网pycn.vince-g.xyz、v1.0.5标2025-10-19。本次GitHub API返回76次提交、新官网和2026-07-19的v1.0.5 published_at。两类来源按时间层保存，发行记录重建或改写原因待核实。
- 当前官网https://pycn.vincentthegamer.dpdns.org/zh_hans/由普通网页工具返回不可访问；固定仓内同源中文文档可读。网页可达性及部署实际行为待核实。
- API元数据提供本次公开状态；历史改写、迁移、已撤回发行及仓外材料存在遗漏风险。创建时间、Git作者／提交时间、版权年份和发行published_at各自独立。
- 静态读取支持实现链与接口职责核验；动态错误、性能、包内内容、测试通过及所有Python库兼容性继续待核。
- 搜索索引覆盖、缓存陈旧、同名包及大小写差异分别记录。新发现计数0，旧背景首次深入计1。

