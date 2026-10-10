# 第十一轮：Issue #22旧候选PyCn核验

核验日期：2026-10-10（UTC）。研究时段：19:31—19:36 UTC。目录基线：[b8bced915e093ccdfde6b32804f7bd2b4c6a0786](https://github.com/yuyan-lang/chinese-programming-languages/tree/b8bced915e093ccdfde6b32804f7bd2b4c6a0786)，71项语言、8项内核。

## 范围、排重和结论

本分项先读取目录根AGENTS.md、[Issue #22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)正文和全部4条评论，以及固定data/languages.json、data/kernels.json和递归目录树。目录树显示写作规范文件为根AGENTS.md。第十轮评论记载初始10组候选已有6组完成分类，剩余XuYu、Chinese Rust、PyCn及52zwbc中文CPython关联资料4组。

本轮限定sunzi334481/PyCn。新发现语言正式条目0；旧候选完成分类资料1。本项纳入目录，Issue #22初始10组累计完成分类7组，其余3组继续按原议题核验。

- 分类：Python中文方言／词元级源码转译层。
- 可追踪实现链：中文.pycn → 手写扫描及词表替换 → Python源码 → Python compile／exec。
- 中文原例：固定README第11—16行，完整阶乘函数及一次调用，6行连续文本。
- 版本：包和三套编辑器配置自标0.1.0；许可MIT。
- 测试：静态源码共86个test_方法；通过状态按作者说明与独立执行分别记录。
- 同名边界：本条与PythonDeveloper29042/PythonCN、LostPEople634/pchinese、Vincent-the-gamer/pycn及PyPI Pycn分别保留身份。

目录精确检索项目名PyCn及sunzi334481/PyCn仓库URL命中0项。模糊pycn字符串命中lang-027的chinese_code.pycn示例后缀；lang-027实际仓库为PythonDeveloper29042/PythonCN。本分项保持该既有条目的独立研究范围。

取证采用普通网页、GitHub公开文件、元数据和固定提交。测试、安装、构建、编译、桌面操作及外部写入留在本轮范围之外。词表计数、测试方法计数、JSON组装和原例逐字比对仅处理已获取文本。

## 固定来源与公开文件范围

[固定快照f840307aab9f55e7d25d798768db0ad4db24edb0](https://github.com/sunzi334481/PyCn/tree/f840307aab9f55e7d25d798768db0ad4db24edb0)与本次读取默认main头一致；分支集合仅main。递归树90项，其中65个文件、9份examples/*.pycn，truncated=false。包含7个pycn_lang Python核心文件、4份tests文件、2份docs手册、2个文档／编辑器词表生成工具，以及VSCode、JetBrains和Visual Studio插件工程。

完整树可核定这次公开快照的文件范围；历史私有资料、仓外发行文件与本地开发历史继续待核实。README的VSIX已打包说明按作者陈述保存，当前固定树给出插件源工程和构建配置，发行附件另列核验。

## 连续中文原例

[README第11—16行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/README.md#L11-L16)：

```pycn
定义 阶乘(数):
    如果 数 <= 1:
        返回 1
    返回 数 * 阶乘(数 - 1)

打印("5 的阶乘 =", 阶乘(5))
```

该片段从完整固定README切片后，与单独按start_line=11、end_line=16获取的结果逐字比较，相等为true。空白行和四空格缩进保持原文；预期输出与实际运行结果分开，实际执行待核实。另读[examples/斐波那契.pycn](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/examples/斐波那契.pycn)，确认独立原例文件中有中文递归、循环、列表方法及格字符串写法。

## 转译与宿主执行链

### 名字、词表及扫描

1. [translator.py第21—26行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/translator.py#L21-L26)使用下划线／isalpha识别名称开头，下划线／isalnum识别后续字符。完整Python Unicode标识符规范覆盖待核实。
2. [第447—585行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/translator.py#L447-L585)预扫描定义位置，把赋值目标、函数名、参数、循环变量、类名、别名及global/nonlocal等写入一个集合。集合范围为本次传入的整段源码。
3. [第35—53行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/translator.py#L35-L53)显示准确名字优先级：点号后的名称查ATTRIBUTE_MAP；普通位置先查KEYWORD_MAP，再在名称未被收集为用户定义名时查GLOBAL_NAME_MAP；其余名称保留。
4. [第591—717行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/translator.py#L591-L717)接通预扫描与主扫描，分别复制注释、扫描字符串和数字、读取名称、特殊处理导入及关键字实参，最后连接输出片段生成Python源码。
5. [mappings.py第1368—1399行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/mappings.py#L1368-L1399)构造两个映射表：全局名字表按内置函数、内置常量、异常、魔术名字顺序合并；属性表按类型方法、标准库API、魔术名字顺序合并，重复名称采用先入值。

对固定mappings.py中直接写出的字典键做文本计数，结果如下。该计数描述词表规模，完整API可用性单列待核实。

- [KEYWORD_MAP第25—66行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/mappings.py#L25-L66)：40项中文键，含定义→def、如果→if、返回→return、对于→for、在→in、导入→import、匹配→match、情形→case；复合形式包括不在→not in、不是→is not。
- [BUILTIN_FUNCTIONS第71—137行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/mappings.py#L71-L137)：65项。
- [BUILTIN_CONSTANTS第142—148行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/mappings.py#L142-L148)：5项。
- [EXCEPTION_MAP第153—229行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/mappings.py#L153-L229)：63项。
- [DUNDER_MAP第234—330行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/mappings.py#L234-L330)：86项。
- [MODULE_MAP第335—416行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/mappings.py#L335-L416)：80项。
- [TYPE_METHODS第421—517行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/mappings.py#L421-L517)：88项。
- [LIBRARY_API第523—1343行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/mappings.py#L523-L1343)：747项。
- 上述8张表的各表键文本数量与各自唯一键数量一致。跨表同名的优先级由两个合并函数决定。

### 字符串及导入转译

[translator.py第59—72行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/translator.py#L59-L72)处理字符串前缀；[第193—267行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/translator.py#L193-L267)扫描单引号、双引号及三引号字符串，处理转义、f-string插值和特殊字符串。中文前缀格／原／字分别对应f／r／b；完整内容为__主__的普通字符串可转换为__main__。

[第113—187行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/translator.py#L113-L187)扫描f-string花括号表达式、转换标志和格式尾部，在第186行递归调用translate(expr_text)。该递归调用重新收集表达式内名称。外层定义名遮蔽、嵌套格式说明及复杂表达式语义待核实。

[第342—441行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/translator.py#L342-L441)专门处理import和from：查MODULE_MAP转换模块段；import模块时按情况补中文别名；from导入项查ATTRIBUTE_MAP，再生成别名形式。多模块导入由换行连接独立import语句，子模块绑定也可能追加语句。相对导入和括号形式有专门解析分支。

### CLI、模块及REPL

- [cli.py第34—87行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/cli.py#L34-L87)：设置脚本路径与argv，UTF-8-SIG读取源码，translate后调用compile(translated, path, "exec")，再exec到含__name__、__file__和__builtins__的模块全局字典，结束时恢复sys.path与sys.argv。
- [cli.py第90—119行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/cli.py#L90-L119)：compile子命令生成Python文本，附编码及来源文件头，输出到.py或标准输出。这里的命令名称表示源码导出。
- [importer.py第22—41行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/importer.py#L22-L41)：PycnLoader读取.pycn，经translate→compile→exec进入module.__dict__；同时登记原始中文内容到linecache。
- [importer.py第44—82行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/importer.py#L44-L82)：PycnFinder基于sys.path或包路径查找单文件.pycn和包__init__.pycn，并在搜索列表前加入当前工作目录。
- [importer.py第88—99行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/importer.py#L88-L99)：install把PycnFinder插到PathFinder之前，并清除path_importer_cache。[__init__.py第3—10行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/__init__.py#L3-L10)在包导入时调用安装函数。
- [repl.py第14—44行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/repl.py#L14-L44)：跨输入保留globals与输入缓冲，translate后使用code.compile_command(..., "single")判断完整性，再exec。

这些源码构成可读的中文到Python转译和宿主执行链。运行正确性、完整语法覆盖、兼容所有Python生态的作者承诺继续待独立核实。

## 关键边界与测试证据层级

1. 行数保持分具体路径记录。[测试第262—264行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/tests/test_translator.py#L262-L264)直接断言一行“导入 数学, 随机”输出两行import。[测试第309—312行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/tests/test_translator.py#L309-L312)的行数断言覆盖三行打印输入。多模块／跨行导入展开与导出文件头情况下的源码行号对应待核实。
2. 名字遮蔽由整段源码的单一集合控制。跨函数、跨作用域、定义先后和f-string递归转换的语义待核实。属性表按名字统一替换，同名自定义方法的调用及第三方库重名行为待核实。
3. [importer.py头注第5—10行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/importer.py#L5-L10)描述末尾注册；实际install顺序为PathFinder前置，条目以实现顺序记录。当前工作目录、包路径及同名.py/.pycn模块优先级的运行结果待核实。
4. [docs手册第170行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/docs/语言手册.md#L168-L170)描述属性位置也先处理关键字；实际_translate_name先分after_dot分支。[tests第157—161行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/tests/test_translator.py#L157-L161)保存x.真、x.空、对象.长度保持原样的断言。条目采用源码分支说明优先级。
5. 四份测试源码按“def test_”方法声明逐一计数：test_translator.py 72，test_importer.py 4，test_e2e.py 9，test_check_mappings.py 1，合计86。此处核定的是静态方法数量。
6. [转译测试](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/tests/test_translator.py)多为字符串相等／包含断言，覆盖关键字、名字、属性、字符串、导入及控制流；[导入测试](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/tests/test_importer.py#L28-L60)写临时模块／包并断言导入结果；[E2E测试](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/tests/test_e2e.py#L12-L71)调用CLI子进程并检查退出码及输出子串；[词表测试](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/tests/test_check_mappings.py#L14-L37)检查每个字典内部的重复键。
7. E2E中test_compile_then_run在第64—71行执行compile命令并检查输出含def，后续生成文本执行的独立结果待核实。
8. README第143行记“86个用例全部通过”。本次读取[Actions运行集合](https://api.github.com/repos/sunzi334481/PyCn/actions/runs?per_page=100)返回total_count=0、workflow_runs=[]。作者本地测试陈述、静态测试源码和独立复测结果分别记录。

## 编辑器源码与发行层级

- [VSCode package.json](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/editors/vscode-pycn/package.json#L1-L50)声明版本0.1.0、vscode ^1.75.0、.pycn语言、语法高亮及片段；[extension.js第33—50行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/editors/vscode-pycn/extension.js#L33-L50)在终端启动pycn run或python -m pycn_lang run。
- [JetBrains build.gradle.kts](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/editors/jetbrains-pycn/build.gradle.kts#L1-L45)声明0.1.0、IntelliJ Platform 2.1.0、IDEA Community 2024.2、JDK17；[运行入口第60—79行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/editors/jetbrains-pycn/src/main/kotlin/com/pycn/plugin/PycnRunConfiguration.kt#L60-L79)组装pycn或Python模块命令。
- [Visual Studio manifest](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/editors/visualstudio-pycn/PycnVsPackage/source.extension.vsixmanifest#L1-L23)声明0.1.0、VS Community 17.x和.NET Framework4.8；[PycnRunner.cs第25—70行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/editors/visualstudio-pycn/PycnVsPackage/PycnRunner.cs#L25-L70)启动Python模块并把进程输出接入IDE输出面板。
- 三套编辑器的实际构建、安装、平台适用范围、VSIX取得位置和市场发布状态待核实。README“VSCode已安装验证”作为作者报告保存。

## 作者、日期、版本、许可与AI

[仓库元数据](https://api.github.com/repos/sunzi334481/PyCn)给出：
- owner sunzi334481；fork=false。
- created_at：2026-10-05T11:54:33Z。
- pushed_at：2026-10-06T10:43:43Z。
- 默认main最新Git提交：2026-10-06T10:43:42Z。

默认分支完整提交页24条，以空parents根提交结束，所有作者名均为sunzi334481。初始历史分列：
- [6978f23f](https://github.com/sunzi334481/PyCn/commit/6978f23f4aaf4f92d36e5a4cfb9c54855a086d1c)，2026-10-05T11:54:34Z；根树只有README.md，正文为两行项目简介。
- [ac32135e](https://github.com/sunzi334481/PyCn/commit/ac32135ef62a48b4a530dfc2b0eb6de16caed4e7)，2026-10-05T11:59:30Z；树包含README、包初始化、模块入口、CLI、importer、REPL和pyproject。
- [114e7b75](https://github.com/sunzi334481/PyCn/commit/114e7b75a986142183f4ac41e780f5c19d28432e)，2026-10-05T12:08:10Z；树中加入translator.py。
- [3c65d09e](https://github.com/sunzi334481/PyCn/commit/3c65d09e7f2aa9f8e2cea71007660e2f40fcf624)，2026-10-05T12:16:40Z；树中加入mappings.py。
- [当前提交](https://github.com/sunzi334481/PyCn/commit/f840307aab9f55e7d25d798768db0ad4db24edb0)，2026-10-06T10:43:42Z，继续上传Visual Studio插件工程文件。

[pyproject.toml第5—12行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pyproject.toml#L5-L12)包名pycn-lang，版本0.1.0，作者PyCn Language，Python>=3.10；[__init__.py第9行](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/pycn_lang/__init__.py#L9)同为0.1.0。README第61行记录作者开发环境Python3.14，各Python版本兼容性待核实。版权文本为[MIT License](https://github.com/sunzi334481/PyCn/blob/f840307aab9f55e7d25d798768db0ad4db24edb0/LICENSE#L1-L21)，署名2026 PyCn contributors。

[Releases集合](https://github.com/sunzi334481/PyCn/releases)本次返回空数组；git/refs/tags返回404。源码版本、Git标签、GitHub发行、包索引发布分别保存。普通网页读取PyPI pycn-lang页面出现Internal Error，发布状态待核实。

AI参与：已读README、语言手册、包配置、核心转译和词表源码以及24条提交消息，具体AI工具、共同作者声明、参与文件范围及比例待核实。词表中的Cursor为SQLite游标类API映射，按语言库资料处理。提交节奏与文风作为开发活动痕迹保存，AI归因继续等待作者资料。

## 同名、上游和范围划分

sunzi334481项目使用pycn-lang包名，pyproject项目URL直接指向sunzi334481/PyCn。GitHub元数据fork=false只用于仓库元数据分类；源码继承来源仍按作者声明或代码历史核验。

- 目录lang-027对应PythonDeveloper29042/PythonCN；lang-065对应LostPEople634/pchinese。本项按独立账号、仓库、包配置、快照和实现说明形成身份链，二者更新属于本轮其他研究任务。
- [Vincent-the-gamer/pycn固定README](https://github.com/Vincent-the-gamer/pycn/blob/48acdd141a914fed636ea8c5631db22a4b709a9f/README.md)由同名检索取得，目录介绍Rust CLI、logos词法／手写递归下降解析、PyO3及WASM／HTTP包装。读取main固定头48acdd141a914fed636ea8c5631db22a4b709a9f后再取README，blob与首次获取相同。这里保存同名排重依据，独立条目深挖与正式发现计数留给主任务。
- [PyPI Pycn](https://pypi.org/project/Pycn/)页面列0.0.1、2021-08-20、维护者Wry、作者Ruoyu Wang，简介为中文Python库。项目Homepage点击进入GitHub首页。本包的发布信息按其自身身份保存，sunzi334481/PyCn的首发时间继续以其仓库历史记录。
- PyCN技术评论／Python中文社区相关搜索结果按同名社区线索处理。
- 跨项目合作、改名、镜像和代码继承关系待核实。

## 检索覆盖、关键词、时段与遗漏风险

检索平台：GitHub公开仓库文件／目录／提交／分支／Releases／Git refs／Actions接口、GitHub仓库搜索、普通网页搜索与PyPI网页。普通网页搜索采用不限发布日期；核心原仓资料跨度为2026-10-05—2026-10-06，同名包资料追溯到2021年。核验截至2026-10-10 UTC。

实际关键词：
- 普通网页："sunzi334481" "PyCn"；"sunzi334481/PyCn"；"sunzi334481" "AI"。
- 普通网页："PyCn" "中文" "AI"；"PyCn" "PythonCN"；"pycn-lang"。
- GitHub仓库：PyCn in:name fork:true；PyCn user:sunzi334481；"PyCn" Chinese；PyCn in:name language:Python。
- 固定源码文本：AI、人工智能、大模型、Claude、ChatGPT、Cursor、Copilot、Codex、DeepSeek、通义、千问、Gemini，以及def test_、各词表声明。
- 目录排重：PyCn名称、sunzi334481/PyCn URL、pycn字符串，单独核对lang-027与lang-065。

结果与风险：
- 原仓及固定GitHub文件接口可读。普通网页直接读取作者主页出现Cache miss，PyPI pycn-lang读取出现Internal Error；错误作为本次访问结果保存。
- GitHub通用fetch的/search/repositories端点返回“不支持的URL”，随后通过专门search_repositories取得结果。宽查询第一页返回100项，包含PyCNC、PyCNN、PyCN社区和其他同名仓；该页覆盖记录为局部检索。精确账号查询仅返回sunzi334481/PyCn。
- 普通网页结果主要包含同名社区、同名包与无关词汇。技术结论基于原仓固定源码。
- 仓库创建、Git作者／提交时间、版权年份、包版本及发布日分别记录，避免跨证据类别推定首发。
- 测试方法计数核定源文件中的声明，动态收集、测试执行和覆盖率结果待核实。CLI、模块导入、REPL、导出源码和编辑器调用的行为边界分别保存。
- README数字本次可与词表和测试源码计数对上；库名覆盖数量与实际API可用性分别核验。
- 私有资料、历史改写、仓外打包附件、PyPI服务读取故障、搜索索引延迟及同名仓遗漏仍有风险。

## 交付

- data/languages.json中的lang-072：无ID数组1项，description为372字符，连续中文原例6行。
- round-11-pycn-pending.json：本项后续字段核验1组。
- round-11-pycn.md：本日志。

本分项外部状态保持只读，交付为本地研究文件。

