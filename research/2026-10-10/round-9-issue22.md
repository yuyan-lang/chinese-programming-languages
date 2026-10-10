# 第九轮：Issue #22 pchinese与MiniLang核验

核验日期：2026-10-10（UTC）。目录基线：[d4b23b6fb82c695a34f600582a4fa6399c44fb89](https://github.com/yuyan-lang/chinese-programming-languages/tree/d4b23b6fb82c695a34f600582a4fa6399c44fb89)，64项语言、7项内核。

## 范围与结果

开轮读取根AGENTS.md、完整递归目录、data/languages.json的64项条目、round-8.md，以及[Issue #22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)正文与现有2条评论。Issue第2条评论确认第八轮已收录太和与ChineseToyLang，其他8组继续核实。本分项沿用Issue中的pchinese、MiniLang身份与固定提交，核验2项。

- 旧候选核验2项：pchinese、MiniLang（FI0m9ySans）。
- 新发现0项。
- 完成分类资料2项：Python中文语法转译层与独立AST解释器各1项。
- 后续字段核验2组，详见配套pending.json；其身份属于这两项已完成分类资料的旧候选。
- 两段code字段分别来自固定源文件连续6行与9行，全文截取和按行读取结果逐字一致。
- 公开文章按AGENTS.md采用肯定陈述，并将资料缺口标为待核实。

核验方式为公开网页、GitHub仓库文件及元数据的只读检查。项目安装、构建、程序运行和外部写入均留在当前范围之外。

## 一、pchinese

固定快照：[8c1a0957d3177dd85a7723c4dcb6ab042b6a2752](https://github.com/LostPEople634/pchinese/tree/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752)。当前默认分支main头提交与该快照一致，递归树24项、truncated=false，默认分支7次提交。

### 中文原例与分类

[examples/综合示例.pcn第4—9行](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/examples/综合示例.pcn#L4-L9)完整包含阶乘函数及调用，使用“定义、如果、返回、打印”和全角括号、冒号、中文引号。函数、类、异常、推导式、条件及循环还分别出现在该文件和你好.pcn中。

分类采用“Python中文语法转译层／标识符词元映射运行器”。其实际流水线如下：

1. [translator.py第94—150行](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/pchinese/translator.py#L94-L150)逐字符扫描，依次处理注释、全角引号、标识符、ASCII引号及其他字符。
2. 注释与ASCII字符串按对应扫描分支保留；全角字符串经字面量转义封装。
3. Unicode正则\\w+识别连续标识符，第135行以MAP.get(word, word)映射整词。代码区剩余字符以PUNCT处理。
4. [keywords.py第117—124行](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/pchinese/keywords.py#L117-L124)合并内置函数、关键字及PyQt词表。
5. [runner.py第42—136行](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/pchinese/runner.py#L42-L136)调用translate／translate_file、Python compile与exec。语法解析及执行由Python承担；全局环境注册容器助手和绑定函数。
6. [cli.py第140—157行](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/pchinese/cli.py#L140-L157)的compile入口输出.py源码；[repl.py第119—151行](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/pchinese/repl.py#L119-L151)翻译后通过codeop识别完整语句并执行。

该证据支持按代码区域和标识符边界转译的实现机制。字符串、注释、Python运行时与词表分别记录。

### Qt扩展与实现边界

[qt_words.py](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/pchinese/qt_words.py)明确说明词表对代码区的导入名、属性名和变量名统一生效，所收录中文词成为保留词。GUI依赖按README记录为Python3.13环境中的PyQt5与PyQt-Fluent-Widgets。运行器的绑定助手把中文信号名查表后，通过定长lambda连接函数。

静态文本统计得到604条字面键值、601个唯一键，与README的601条词表口径对应；以下重复键具有后值覆盖：

- 事件：第112行为QEvent，第308行为event，形成字典后取event。
- 取项：第216行为item，第361行为getItem，形成字典后取getItem。
- 固定：第445行为Fixed，第666行为PIN，形成字典后取PIN。

[tests/test_qt_support.py第43—52行](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/tests/test_qt_support.py#L43-L52)的重复键检查读取已形成的PYQT字典。该项对源字面量重复的检查覆盖、对应API语义及GUI实际运行效果分别待核实。测试文件还提供名称对账、翻译检查、offscreen运行与回归入口；这些属于已保存测试源码，执行结果待独立验证。

[字符串扫描函数](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/pchinese/translator.py#L43-L91)整体保留ASCII前缀字符串，全角字符串处理将换行转换为转义序列。f-string插值中的中文转译范围和跨行全角字符串的行号对应关系继续待核实。

### 作者、时间、版本与许可

- 仓库创建：2026-08-06T05:30:41Z。
- [根提交7595e93](https://github.com/LostPEople634/pchinese/commit/7595e93ebf7e00be624fa834dfbfbaed1bdca266)：2026-08-06T05:30:42Z，初始README说明基于Python的中文编程语言实验解释器。
- [首次源码与原例上传81aca58](https://github.com/LostPEople634/pchinese/commit/81aca58ac5b042809f2888c3689dc8a86bd7cd3f)：2026-08-06T06:00:52Z。
- 7次提交均由GitHub账号LostPEople634署名；[MIT许可证](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/LICENSE)署名2026 LostPEople634。
- [__init__.py](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/pchinese/__init__.py#L1-L10)自标1.2.0。头提交时间2026-10-01T04:58:24Z，提交说明为同步1.2.0及Qt中文支持。
- [v1.1.0-alpha1预发行](https://github.com/LostPEople634/pchinese/releases/tag/v1.1.0-alpha1)：发布于2026-08-06T06:09:26Z，prerelease=true，标签指向81aca58，提供8,432,661字节pchinese.exe附件。发行说明将用途定位为个人学习实验，并提及更早本地版本。
- 1.2.0源码与1.1.0-alpha1预发行分别记录；二进制内容、1.2.0独立发行及更早公开历史待核实。
- [pchinese.spec第9行](https://github.com/LostPEople634/pchinese/blob/8c1a0957d3177dd85a7723c4dcb6ab042b6a2752/pchinese.spec#L8-L10)保留含Doubao/chats的构建输入目录线索。此信息指向开发路径，具体AI参与和生成范围待作者材料核实。

### 关系

README、包名、CLI、许可证和提交作者建立同一项目身份；GitHub元数据fork=false。Python为语义及运行基础，Qt词表为该项目配套扩展。其他中文Python项目与同名仓库的历史及代码继承关系继续待核实。

## 二、MiniLang（FI0m9ySans）

固定快照：[2778f3d3df8d6806c5b9b763e31e7d0d3ac19c7d](https://github.com/FI0m9ySans/minilang/tree/2778f3d3df8d6806c5b9b763e31e7d0d3ac19c7d)。当前默认分支main头提交与该快照一致，递归树24项、truncated=false，默认分支20次提交。

### 中文原例与独立解析

[Code/MLCode/math_simple.kalop第9—17行](https://github.com/FI0m9ySans/minilang/blob/2778f3d3df8d6806c5b9b763e31e7d0d3ac19c7d/Code/MLCode/math_simple.kalop#L9-L17)为完整迭代阶乘函数，包含“函数、定义、当、返回”；全文和按行返回结果逐字比对后写入code。README另有变量声明、平方函数和kio调用，实例目录保存hello、game、math_simple三份.kalop文件。

[Code/minilang.py](https://github.com/FI0m9ySans/minilang/blob/2778f3d3df8d6806c5b9b763e31e7d0d3ac19c7d/Code/minilang.py)集中保存解释器：

1. 第15—130行：Lexer通过正则规则生成带行列信息的Token，中文关键字在标识符规则之前匹配；标识符汉字范围明确为U+4E00—U+9FA5。
2. 第132—229行：声明Program、变量、赋值、条件、循环、函数、返回、运算、字面量和调用节点。
3. 第231—460行：Parser按语句与表达式优先级递归下降，构造AST。
4. 第462—616行：Interpreter直接执行和求值AST；变量及函数分别存入字典，自定义函数调用复制当前变量环境、绑定参数并在结束后恢复，通过ReturnException传递返回值。
5. 第617—667行：MiniLang.run串接Lexer.tokenize→Parser.parse→Interpreter.interpret；run_file以UTF-8读取文件。
6. 第672—718行：命令行支持.kalop文件与--debug，后者打印词元和语法树。内置输出函数为kio。

分类采用“中文语法语言／Python实现的独立AST解释器”。源码证据支持独立词法、解析、AST和树遍历执行链。完整Unicode标识符覆盖、运行行为与教学使用效果分别待核实。

### 作者、日期、版本与许可

- 仓库创建：2025-11-04T05:49:43Z。
- [根提交4770c51](https://github.com/FI0m9ySans/minilang/commit/4770c5120be73d9e5667fe013e1cbc921039e625)：2025-11-04T05:49:44Z，README介绍面向中文用户的MiniLang。
- [解释器上传6144cf4](https://github.com/FI0m9ySans/minilang/commit/6144cf4b94b6b582f8b05c3d69cd6db411435dbf)：2025-11-04T05:51:11Z。
- [数学原例上传6f28e64](https://github.com/FI0m9ySans/minilang/commit/6f28e6485442c219136bcf6193f903f8231a8cc4)：2025-11-04T05:52:43Z。
- 20次默认分支提交的作者账号均对应FI0m9ySans，最新提交时间2025-11-04T06:07:45Z。
- Releases集合返回空数组，git/refs/tags返回404。语言正式版本与发行物待核实。
- 仓库license元数据为null；[数学库/minilang-package.json](https://github.com/FI0m9ySans/minilang/blob/2778f3d3df8d6806c5b9b763e31e7d0d3ac19c7d/数学库/minilang-package.json)自标数学库1.0.0、MiniLang社区、MIT。这些字段只按对应数学库包元数据保存，语言仓库整体许可证与社区身份待核实。
- AI参与情况待作者原始声明核实。

### 包目录与关系

数学库/main.kalop和minilang-packages/packages/数学库/1.0.0/main.kalop均为blob d4a4cb3ade2f6bdd516f53d232b222ad4e37a73f；两处包元数据均为blob 7d045f569d9a31804ef272ac3f8f09c06ec721f7。两组路径属于同仓配套包资料。字符串工具和网络请求包目录下的main.kalop、package.json各为1字节，包管理机制和这些包的实现状态待核实。

UnaryOperation节点及其求值分支已保存；当前表达式解析链的一元语法接通待核实。README自述从零设计，外部同名语言及其他中文解释器的代码继承关系继续核实。GitHub元数据fork=false按仓库元数据事实记录。

## 检索、去重与遗漏风险

- 固定data/languages.json的64条资料全文检索pchinese、FI0m9ySans和minilang命中0项；Issue #22为两项既有候选的来源。
- GitHub查询pchinese in:name fork:true，返回原作者仓库与其他同名或部分名称匹配结果。额外同名Pchinese的元数据标主语言Java，项目身份和继承关系待核实；本分项保持原作者仓库的候选边界。
- GitHub查询minilang user:FI0m9ySans fork:true，返回FI0m9ySans/minilang。
- 普通网页搜索“pchinese LostPEople634”和“MiniLang FI0m9ySans”返回空结果。直接网页读取两仓库主页出现Cache miss，随后使用GitHub公开文件及API只读接口取得资料。
- 目录同名检索、账号、许可证、提交、原例及文件树用于身份核验；跨站转载、早期本地版本和手工复制关系仍有遗漏风险。
- 研究记录采用材料事实、作者说明与独立执行状态分层：已有测试入口按源码记录，程序安装及运行效果待独立验证。

## 交付

entry.json为2项无ID数组，字段沿用现有languages.json；两项description分别319与309字符。pending.json为这2项的后续字段核验。旧候选2项、新发现0项，身份和计数沿用Issue #22。两段原例的逐字匹配结果均为true。

