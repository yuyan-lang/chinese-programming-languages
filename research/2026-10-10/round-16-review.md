# 第十六轮独立静态审阅

核验日期：2026-10-10。百科基线为 `93815086f1778802ea57ddeeec8ad717e355814f`。审阅遵循该提交的[公开技术文档写作规范](https://github.com/yuyan-lang/chinese-programming-languages/blob/93815086f1778802ea57ddeeec8ad717e355814f/AGENTS.md)。核验方式为独立读取原作者固定源码、GitHub 元数据与既有百科记录，执行效果保留“待核实”状态。

## Z语言（zyw98020）：审阅结论

拟稿具备正式语言条目所需的中文原例和独立词法、解析、语法树求值实现证据。计数、固定提交、10行代码及主要实现链核对通过。最新条目和日志已经收紧例程形成顺序的措辞，并补足IDE实际启动的精确行号。第十五轮旧候选继续沿用[Issue #45](https://github.com/yuyan-lang/chinese-programming-languages/issues/45)，本轮计为旧候选补证、正式语言新增1项。

### 修订核验

1. **例程先后关系已使用“并存”表述。** `fibonacci.zzz`的花括号例程与`hello_new.zzz`的缩进例程均在现存根提交中，且各自blob与当前提交相同；根提交的`Parser::block`已采用INDENT/DEDENT。现存历史支持“同仓花括号例程、始/终注释与当前缩进解析并存”，各语法材料形成顺序与兼容范围继续待核实。最新条目的正文、关系、核验说明和来源标题已采用该口径。
   - [根提交花括号例程](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/ed037ddd395bca8359a17572aae92bb4875d3c2e/Z/examples/fibonacci.zzz)
   - [根提交缩进例程](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/ed037ddd395bca8359a17572aae92bb4875d3c2e/Z/examples/hello_new.zzz)
   - [根提交解析器](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/ed037ddd395bca8359a17572aae92bb4875d3c2e/Z/interpreter/src/parser.cpp)

2. **IDE启动引用已增加实际launch调用。** L283–339准确覆盖查找解释器、NSTask创建、参数、工作目录和三条标准流管道。最新条目与日志已增加`launchAndReturnError`所在的[L410–420](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/ide/IDEWindowController.m#L410-L420)。
3. **IDE补全可以补入直接实现来源。** 独立读取的`CodeEditorView.m`保存中文词和拼音映射，直接支持拟稿对中文、拼音补全的描述。[固定补全实现](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/ide/CodeEditorView.m#L234-L330)。

### 逐项核对

- **固定版本：** 原仓main读取为`bf30f52927284d96950d87ac74abd483807d7ba6`，提交时间2026-07-17T13:00:16Z；原仓创建2026-07-16T13:58:11Z，最后推送2026-07-17T13:00:19Z，archived=false。[main引用](https://api.github.com/repos/zyw98020/Zlang---Chinese-programming-language/git/ref/heads/main)、[原仓元数据](https://api.github.com/repos/zyw98020/Zlang---Chinese-programming-language)。
- **树及提交数：** 完整递归树49项，其中43个blob、6个目录；truncated=false。现存提交3项，根提交`ed037ddd395bca8359a17572aae92bb4875d3c2e`的parents为空，作者及提交者字段为zyw98020，时间2026-07-16T13:58:13Z。[固定树](https://api.github.com/repos/zyw98020/Zlang---Chinese-programming-language/git/trees/bf30f52927284d96950d87ac74abd483807d7ba6?recursive=1)、[提交集合](https://api.github.com/repos/zyw98020/Zlang---Chinese-programming-language/commits?per_page=100)。
- **原例：** `hello_new.zzz`L6–15连续10行与条目代码逐字一致，包含全部空格、空行、注释和半角符号；blob为`f3240eeb32def9fdd84b6e02cf86aedebe638e86`。片段中的递归斐波那契、条件、返回及循环调用范围准确。[固定原例](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/examples/hello_new.zzz#L6-L15)。
- **关键词：** `Keywords::init`的映射赋值恰为36项，L90–125行号准确。计数范围为源码映射表，各关键词的完整语义覆盖另行核实。[固定关键词](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/token.h#L90-L125)。
- **词法：** L131–160读取中文标识符并查关键词表；L163–205比较缩进栈并生成INDENT/DEDENT。描述与代码相符。[固定词法器](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/lexer.cpp#L131-L205)。
- **解析：** L256–438包含函数、返回、条件、while与for-in；L339–354划定缩进块。函数及控制流同时保留单条语句分支，拟稿的“采用缩进块”概括符合实际源码。[固定解析器](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/parser.cpp#L256-L438)。
- **执行：** `main.cpp`L9–40完成读文件、Lexer、Parser、Interpreter及主脚本目录设置；L43–77实现逐行REPL。[固定入口](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/main.cpp#L9-L87)。`interpreter.cpp`L413–453遍历语句并动态分派AST，L814–905包含块、条件、匹配、循环及返回，L1168–1203读模块并再次词法、解析和求值，L1231–1262建立闭包父环境、绑定参数并捕获ReturnException。[语句及返回](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/interpreter.cpp#L814-L905)、[模块及函数调用](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/interpreter.cpp#L1168-L1262)。
- **运行时函数：** `interpreter.cpp`L104、L130、L312分别注册“输入”“打印”“映射”，支持条目的三个具体举例。[固定运行时](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/src/interpreter.cpp)。
- **构建与宿主：** Makefile的CXXFLAGS包含`-std=c++17`；IDE构建脚本使用Objective-C、Cocoa、UniformTypeIdentifiers，并复制zlang到应用包。此处属于构建配置的静态事实。最低可用系统版本与平台效果继续待核实。[Makefile](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/interpreter/Makefile)、[IDE脚本](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/ide/build.sh)。
- **版本与许可：** REPL字符串为v1.0；plist中ShortVersion为1.0、BundleVersion为1、最低系统字段为10.12、版权字符串含2024。README末段声明MIT。正式发行集合为[]，公开Git refs集合仅列main分支；较早的标签命名空间请求返回404作为接口记录保留。最新条目的发行与许可待核说明准确。[plist](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/Z/ide/Z-IDE-Info.plist#L17-L28)、[README](https://github.com/zyw98020/Zlang---Chinese-programming-language/blob/bf30f52927284d96950d87ac74abd483807d7ba6/README.md)、[Releases](https://api.github.com/repos/zyw98020/Zlang---Chinese-programming-language/releases?per_page=100)。

### 旧资料与口径保留

百科固定基线包含86个语言条目。第十五轮原候选保留README L6–18的13行原例、原仓创建时间、许可声明、AI参与待核及同名关系待核；本轮以缩进例程增加实现补证。合并时继续保留[第十五轮原候选资料](https://github.com/yuyan-lang/chinese-programming-languages/blob/93815086f1778802ea57ddeeec8ad717e355814f/research/2026-10-10/round-15-root-pending.json)和Issue #45历史记录。2024版权字段、2026建库与提交时间各自保留独立意义。语言、配套IDE和同名其他作者仓库的身份边界清楚。实际安装、构建、运行、测试、自举结果以及AI工具与人机分工均继续按待核实处理。

## coCN与Atlanage：既有条目审阅

两条最新拟稿保留原ID、名称、别名和全部旧字段。独立对比基线原对象，coCN原13条参考及Atlanage原11条参考的URL均继续保留，原coCN详情页的独立例程来源也并入现行参考。最新参考数量为coCN 33条、Atlanage 27条；合计60条。旧对象全文与Atlanage旧4行代码在研究日志中留存，旧记录和新版事实各自标明。

### coCN核验结论

- 固定master、118项完整树、63条可达提交、根提交日期、仓库创建时间及唯一Release的公开时间均与原仓读取相符。当前主链由.co模块保存；Node.js的两个入口均通过spawn调用引导cocn并将COCN_TARGET传入src/解释器.co。
- 独立读取[例子/自举函数示例.co L33–42](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/%E4%BE%8B%E5%AD%90/%E8%87%AA%E4%B8%BE%E5%87%BD%E6%95%B0%E7%A4%BA%E4%BE%8B.co#L33-L42)，10行原例逐字一致，原中文函数、缩进、空行和两次输出完整保存。
- [参数类型解析](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E8%AF%AD%E6%B3%95%E5%88%86%E6%9E%90%E5%99%A8.co#L664-L719)保存参数及返回类型；[求值器L1440–1463](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L1440-L1463)的变量与函数构造使用初始化、参数、体及闭包等字段。拟稿把类型标注语法与强制检查效果分别记录，证据层级准确。
- [函数调用L1062–1093](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L1062-L1093)以闭包为父建立环境，绑定形参，拆包返回与异常信号；[任务实现L2497–2554](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L2497-L2554)显示当前线程等待执行并缓存，现行“单线程延迟任务”口径准确。
- package.json、index.js和install.js的0.0.2，以及安装器BOOTSTRAP_VERSION=0.1.0均确认。安装器源码称0.1.0为最后一个C构建版本；该来源宜持续归属为安装器注释，制品可用性保留待核实。
- 现行编译器确实读取自举运行时.c模板，生成C文本后调用cc；完整树中的模板与引导二进制补齐方式保留待核。L2脚本按根目录路径寻找相关文件，拟稿按历史与当前布局区分。
- Apache-2.0来自package声明，完整许可及发行包材料继续待核；GitHub唯一Release的4个资产名称准确。源码、资产元数据和独立运行三个层次分列。

### Atlanage核验结论

- 固定main、322项完整树、当前主线2提交、Release的tag=1.0/name=qwq/body=1.0.1，以及ZIP的创建时间、大小和GitHub摘要均确认。
- [hello.at全文L1–11](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/examples/hello.at#L1-L11)与拟稿逐字一致，包含原4行加法函数片段及前置问候和列表循环。源文件末尾换行状态和原空行保留。
- [入口L880–950](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atlv1.at#L880-L950)依次展示引用／包／模块展开、词法、语法、语义、汇编文本、COFF和链接；[链接器L1156–1208](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_linker.at#L1156-L1208)写入MZ、PE、AMD64及PE32+字段。编译目标的静态结论成立。
- seed_builder执行十六进制解码、SHA-256比对及文件写出；rebuild脚本以预存AT-V1.exe生成下一代工具，并比较两代对hello.at的汇编文本；rt_build脚本依赖atlc.exe、Python与NASM。独立运行、完整引导、全程序等价性和二进制复现性继续待核，边界准确。
- 独立重取双方固定版本后，线程池连续51行逐字相等：[Atlanage L146–196](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/runtime/xt_threadpool.c#L146-L196)、[玄铁L146–196](https://github.com/MARKJY-China/XuanTie-Lang/blob/16554746121c61d98429b498f4e8aee9ef650978/runtime/xt_threadpool.c#L146-L196)。JSON解析连续133行逐字相等：[Atlanage L2880–3012](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/runtime/xt_runtime.c#L2880-L3012)、[玄铁L2878–3010](https://github.com/MARKJY-China/XuanTie-Lang/blob/16554746121c61d98429b498f4e8aee9ef650978/runtime/xt_runtime.c#L2878-L3010)。
- 上述结果支持“运行时局部代码存在对应”。整体派生范围、形成过程、作者协作及授权沿革继续待核。玄铁固定LICENSE确为MIT并署名“Copyright (c) 2026 问号盒”，拟稿将该许可明确限定到玄铁对照来源，范围准确。

## 知序与china++：新增条目审阅

两组固定原例、实现和身份去重核验通过。它们分别沿AI-CN改名历史及chinapp原仓／Fork关系合并计数；每组计为一个项目。

### 知序（Zhixu）

- [README L31–44](https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/README.md#L31-L44)的14行平均值函数和条件分支与条目逐字一致。出处标注为README，原demo.zx文件内容差异保留说明。
- 独立读取zhixu.py的KEYWORD_MAP、tokenize、generate_python、translate、run_file：中文完整标识符查表、词元生成Python、引号标点预处理、UTF-8读取和exec调用链与拟稿相符。此处按转译语言分类。
- Ollama的HTTP generate、OpenAI兼容chat/completions与HuggingFace Transformers生成调用均有实际源码路径；模拟模型与加载失败后的模拟回退分支清楚。[固定后端实现](https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu_utils.py#L48-L418)。
- [微调、量化L529–618](https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu_utils.py#L529-L618)分别提供依赖及配置检查、训练命令提示／模拟文本、精度状态打印；[显存优化L759–780](https://github.com/1556880640-bot/zhixu/blob/d85adac01a15af7206ec72eda10d994b36a4b37a/zhixu_utils.py#L759-L780)提供CUDA检测与状态文本。拟稿按实际实现限定产品能力，训练与优化效果保持待核。
- 知序三次提交都含Claude Sonnet 4.6共同署名；AI-CN拥有其中的根和第二次提交，改名提交明确调整项目、核心文件及后缀。开发署名证据和运行时模型能力分别保存。
- 完整树8文件、master唯一分支、Releases空集合与pyproject 1.0.0、Python>=3.10核验通过。前身包版本为2.0.0，MIT属于README与包元数据声明层。

### china++（chinaplusplus）

- [main.cpp L26–38](https://github.com/chinaplusplus/chinapp/blob/dc9dc98cb963cecdd4db1c69da86698207e7ef31/main.cpp#L26-L38)的13行循环及分支与条目逐字一致，缩进与字符串转义完整。
- [核心.h](https://github.com/chinaplusplus/chinapp/blob/dc9dc98cb963cecdd4db1c69da86698207e7ef31/china++/%E6%A0%B8%E5%BF%83.h)确实把整数、返回、如果、否则、又如、三类循环及主函数映射为C++语法；[输入输出.h](https://github.com/chinaplusplus/chinapp/blob/dc9dc98cb963cecdd4db1c69da86698207e7ef31/china++/%E6%89%A9%E5%B1%95/%E8%BE%93%E5%85%A5%E8%BE%93%E5%87%BA.h)包含stdio.h及打印到printf的映射。Makefile的demo目标调用g++，另一目标使用amalgamate。宏层分类准确。
- 原仓三次提交作者映射到windworst；根提交、原仓创建和头提交均为2023-04-21。iclasspeople/chinapp创建于2025-04-14，parent/source均指向原仓。双方头和完整路径／blob列表一致。
- 完整树8项、6文件，refs仅main、Releases为空。项目版号、许可和运行效果保持待核。2025年归属Fork日期，2023年归属原仓现存历史。

## Gitee关键补核

本组使用公开网页浏览器读取固定源页面，记录范围为候选资格和分类所需的关键原件。

- **E#：** 原仓当前头为55503b2e623e3093d9c6423b63aa6b006adaaf32；[固定规范](https://gitee.com/dcosa/esharp/blob/55503b2e623e3093d9c6423b63aa6b006adaaf32/E%23%E8%A7%84%E8%8C%83.md)展示58项中文词表。[固定src/main.c](https://gitee.com/dcosa/esharp/blob/55503b2e623e3093d9c6423b63aa6b006adaaf32/src/main.c)页面标示0 Bytes和空文件。README给出基于CH-VM的定位。语言规范证据与具体实现、连续作者程序的补证项分别记录，保留待核候选的处理适当。
- **汉源码：** 独立读取[固定内置函数示例](https://gitee.com/liu-guanglin/lglCode/blob/562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8/%E5%86%85%E7%BD%AE%E5%87%BD%E6%95%B0.py)，可见中文内置调用与Python的class、def、for、async等语法并存；[固定keyword.py](https://gitee.com/liu-guanglin/lglCode/blob/562659ab0969ee33fa1f3b3ba8a9e04ef51f34e8/cpython/Lib/keyword.py)保存英文硬关键词及case/match/type等软关键词。按中文API扩展记录符合这两份原件。大型C内置实现页面在本次独立浏览中遇到页面读取超时，详细C映射交由既有原件证据继续复核；本段独立核验范围限定为上述示例和关键词表。

## 汇总核验结论

各条目的源码事实、作者声明、元数据和运行待核状态分层清楚。旧对象全文以历史记录标识保留，当前结论采用肯定、直接的事实陈述。五项已独立审阅的正式语言新稿或补全稿的代码例程均保持固定原文，安装、构建、执行、测试、自举和性能继续按待核实处理。Gitee两项关键原件支持各自保留为待核候选或中文API扩展的分类。


