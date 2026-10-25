# Issue #3、#5、#63：原仓与发布包核验

核验日期：2026-10-25（UTC）。基线为3f59f9224b48998b4260b36792fad57ec130ca63，103项语言、11项内核。本组只修改中文编程语言百科。贡献分支为`contrib/issues-3-5-63`；新增对象暂用候选ID，集成时统一分配数字ID。

已完整阅读三个议题正文及全部评论，来源为本次保存的GitHub快照。另读根AGENTS.md、当前语言目录以及第六、七、八、十九、二十二轮日志、青语言收录记录、言语言关联设计补证和2026-10-20客舍补证。当前仓库与工作区均无`.agents/skills`目录。公开说明使用简体中文；原始程序按原件保留字形。

## 已落实的四项编辑

| 对象 | 议题 | 本次分类 | 原始证据 |
| --- | --- | --- | --- |
| RexLang | #3 | 易语言风格的中文编译语言与运行时实现 | 原仓完整Git历史、中文递归例程、ANTLR文法、C++／LLVM编译链 |
| 意语言 | #3 | 实验性中文语言设计 | 固定原作者说明、完整中文模块原例、明确迁移声明及迁移文档 |
| Hanyu-Lang | #5 | 实验性中文语言原型 | PyPI原始sdist、作者测试中的中文打印单句、有限输出实现与词法／解析草稿 |
| 客舍 | #63 | 中文Lisp方言设计与读取器解析原型 | 固定规范、阶乘设计原例、ClojureScript分词和模板解析源码 |

四项对象保存在[data/languages.json](../../data/languages.json)与对应候选详情页；独立对象集合另存[集成候选](issues-3-5-63-candidates.json)。原始包和Git文件的摘要见[证据清单](issues-3-5-63-evidence.json)。本组增加正式可审阅对象4项；安装、导入、构建、候选程序运行及第三方测试执行均为0。

### RexLang：原例与编译实现

[原仓RonxBulld/RexLang](https://gitee.com/RonxBulld/RexLang)公开Git传输成功。固定头提交为[6b11e5a5cc0e27b6c722db3c164e94d072710b7d](https://gitee.com/RonxBulld/RexLang/commit/6b11e5a5cc0e27b6c722db3c164e94d072710b7d)，作者时间2020-09-23T22:18:47+08:00；保留master历史202个提交，根提交[517e93712ab2b131de8a6734b46d558cf2f9a3ce](https://gitee.com/RonxBulld/RexLang/commit/517e93712ab2b131de8a6734b46d558cf2f9a3ce)时间2019-04-12T22:47:30+08:00。五个标签为0.1.0至0.1.4。提交时间与首次公开时间分层记录。

[oe_test/gcd_algorithm.txt第19—27行](https://gitee.com/RonxBulld/RexLang/blob/6b11e5a5cc0e27b6c722db3c164e94d072710b7d/oe_test/gcd_algorithm.txt#L19-L27)保存完整递归子程序，blob为f0bdd739dfbcaba323fe2f415ec12aa9c3886576。例程目录还有数组、结构体、全局变量、引用参数与DLL声明原件。`.版本 2`属于源文件语法标记。

[rexLang.g4](https://gitee.com/RonxBulld/RexLang/blob/6b11e5a5cc0e27b6c722db3c164e94d072710b7d/Compiler/rexlang_compiler/rexLang.g4)明确`.子程序`、`.如果`、`返回`及四种循环文法。`AstGenerate.cpp`将ANTLR词法器、解析器与CST2ASTConvert串联；`compile_driver.cpp`调用语义分析、EmitLLVMIR、WriteOutObject与Linker；`main_entity.cpp`保存命令行文件列表到生成、链接、启动产物的入口。`LLCodeGen.cpp`调用LLVM目标机输出目标文件，`Linker.cpp`使用Clang驱动形成链接参数。证据限定为静态调用链。

固定`License.txt`含Apache-2.0及保留项目名称／原仓地址的扩展条款；README另列付费闭源书面授权等商业条件。条目同时提示两份文字，适用关系待核。Yuanhui Feng职业主页的项目经历沿用Issue既有本人主页搜索缓存；本次确定身份以原仓RonxBulld署名为范围。

### 意语言：从搜索缓存推进到固定设计原件

原作者说明仓的公开Git传输成功，固定提交[f8e93ab160e174a236c88f0dbdcd39f3c30fc8c5](https://gitcode.com/gcw_2sDxn3gI/ai-agent-recommends-intent-language/commit/f8e93ab160e174a236c88f0dbdcd39f3c30fc8c5)，时间2026-10-14T15:09:22+08:00。README blob为e6f63123cf00e1dc7448443a4495725705fc82e1，完整固定树保存README一项。原文自标2026-10-04并说明人类设计／供源代码、AI撰写评估文字的分工。

[README第60—67行](https://gitcode.com/gcw_2sDxn3gI/ai-agent-recommends-intent-language/blob/f8e93ab160e174a236c88f0dbdcd39f3c30fc8c5/README.md#L60-L67)保存完整8行中文递归求和模块。条目按公开设计收录，示例中的版本13分别记录。显式长度头、意元与VM方案按设计说明记录；测试384项、自举与40%完成度属于文章自述。

固定README明确迁移到同账号`directional-computing-chengfu/docs/ai-agent-perspectives/intent-language.md`。本轮取得迁移主仓固定[879634672b8f2d4fe4893f9cc8228b455702c691](https://gitcode.com/gcw_2sDxn3gI/directional-computing-chengfu/blob/879634672b8f2d4fe4893f9cc8228b455702c691/docs/ai-agent-perspectives/intent-language.md)，时间2026-10-14T15:07:54+08:00；迁移文档blob为43e1707b86a23bd4cd67af4811afa7551d01d817。除说明仓新增迁移前言与末尾换行外，两份文章正文一致。主仓固定树277个文件，扩展名扫描返回JS／TS／.yi／.intent文件0项；语言四个核心文件和完整执行链待核。实现可见度与公开设计收录分层处理。

### Hanyu-Lang：原始分发包及实现边界

读取[PyPI元数据](https://pypi.org/pypi/hanyu-lang/0.1.2/json)后，按其返回地址取得[原始源码包](https://files.pythonhosted.org/packages/75/5a/88b050c9b25cdd0e165b858d61a4f7852cda033db0caa410ab2dd11703ae/hanyu_lang-0.1.2.tar.gz)，10095字节，SHA256为`9a3ec70999c2b6418b540c2cdc3585de6df9a2f2c638856a5105532894d79f06`，与发布记录一致。源码包上传时间2025-04-23T16:35:41.915376Z；wheel的内部对应继续待核。

原始`tests/test_basic.py`第6行将`打印("测试输出")`传入引擎并断言返回文本；这是条目采用的作者原例。第10行还保存变量赋值原例和预期，源码覆盖有实质缺口，故主例采用有限打印单句。

`src/hanyu_lang/runtime.py`仅按`打印(`和双引号检查后提取字符串；`lexer.py`保存中文关键词表；`parser.py`引用了本文件中待补的`下一个类型`、`解析打印`等方法。`runtime.py`与空`runtime/`包并存，CLI导入和解析链集成待核。条目采用实验原型分类，GUI、完整控制流、REPL、AST可视化及标准库维持发布页声明证据层级。

包元数据标0.1.2，`__init__.py`内版本为0.1.3；该文件有UTF-16 BOM。Author、邮箱、Homepage及LICENSE署名存在模板占位；LICENSE共67字节，仅含标题与占位署名，完整MIT正文待核。原作者身份限定为PyPI维护者lin8092_76。

### 客舍：规范、解析器与身份分层

通过GitHub只读连接器复核[固定提交2ab2153a46cdab9dd04976d068f62c72b5888474](https://github.com/keshe-lang/keshe-lang/commit/2ab2153a46cdab9dd04976d068f62c72b5888474)，日期2026-08-27T11:15:16Z，提交关联Fancyary。[README](https://github.com/keshe-lang/keshe-lang/blob/2ab2153a46cdab9dd04976d068f62c72b5888474/README.md#L16)保存阶乘设计原例；[SPECIFICATION.md](https://github.com/keshe-lang/keshe-lang/blob/2ab2153a46cdab9dd04976d068f62c72b5888474/SPECIFICATION.md)自标v0.1.0-alpha、2026-08-26、Wang Zhangli，并将最小解释器、宿主接入与形态系统列为路线图后续阶段。

[cljs/main.cljs](https://github.com/keshe-lang/keshe-lang/blob/2ab2153a46cdab9dd04976d068f62c72b5888474/cljs/main.cljs)保存分词、规则和模板递归解析入口；`parse-by-template`返回操作词与参数向量，`ast-template`用途与宿主求值连接待补。字符串扫描使用ASCII双引号，README使用「」；设计原例与实现覆盖分别记录。Common Lisp入口及网页各为1字节。根LICENSE提供Apache-2.0全文，规范另声明CC BY-SA 4.0。发行集合为空。

条目独立依据原仓设计和解析原型收录。FCary论坛账号、Fancyary提交关联账号与Wang Zhangli规范署名的直接身份对应继续标待核。现有两篇论坛原帖索引证据保留为关联材料；本轮直接JSON读取403。语言分类工作已形成可审阅条目，执行能力及跨账号身份分别保留在条目中。

## 其余子项的明确结果

| 子项 | 本次结果 | 精确剩余缺口 |
| --- | --- | --- |
| #3 CN_Interpreter | 连接器重新确认头提交4c07321166a4a697fe6c7ca3c717e7e07abca2fa、完整树仅README及三次提交；读取理念全文 | 具体用户语法规范或完整原始程序。README的“机器开机”为概念讨论例子，解析／实现仍待核 |
| #3 PYCH | 取得0、4.0及4.1.a两个Python附件，摘要均与发行资产一致；正式4.0表达式和脚本入口已静态阅读 | 作者保存的实际中文程序／完整语法示例和许可正文。4.1.a控制流分派调用ifrealize等函数，其定义与可用性继续待核 |
| #3 衍真 | 原页404；公开Git传输返回403“project could not be found”；旧中文循环原例搜索缓存沿用既有记录 | 可直接读取的原作者文档／规范／源包及固定内容，作者与项目身份；当前字节材料待补 |
| #5 无极 | 原作者CSDN直读521；Gitee页面及公开目录接口超时；Git传输连接重置 | 原作者中文语法／程序原件；原仓身份与实现分类。原介绍的C／lex／bison按既有作者声明记录 |
| #5 Wxe | 连接器重新核对原仓元数据及完整树，头提交仍d46b7132f23751de26dd584bab0536fa85ef790d，树为README与LICENSE | 中文用户语法／程序原例、Wxe编译器／WxeEditor原件。MIT正文与项目存在性已核 |
| #5 TRAE165813辅助线索 | 原始主题再次直读超时，沿用已有原帖索引、作者账号与.中码／JS生成声明 | 连续原始中文程序、正式项目名与编译器原件；单篇IDE介绍线索按原范围保存 |

PYCH 4.0附件资产ID479462953，15508字节，SHA256为`7169b20e365e86456fff8a627b2f33f7d79a12a392b02de3c7c8170cf8306e9a`；4.1.a main.py资产ID480078995，15048字节，摘要`5833c3b0f00f72478625450383c059d9c9d5c02fd26fbf3e66801b88e2a246a4`；main.1.py资产ID480076657，14387字节，摘要`10bde4d680b6626e03518a1ceb45653c9a1fbb3ab8105df8d51642f5dfb4bfbe`。pych0资产ID479409018、3135字节、摘要`bcd37026c7f378267029888d9a7e6a2c12a3fd5e19ad24720cf18385bfbf57cf`。附件静态核验完成，第三方程序执行0次。

4.0的`detectionidentifier`按“变量 ”、“函数 ”、“注释 ”分派；变量以“等于”分隔；递归求值识别中文数字、布尔、算术及比较方法。列表与字典在`methods`中仍为`pass`。4.1.a main.py增添“如果／当时／重复／对于”分派并调用相应实现名，文件中定义集合尚未包含这些控制流函数。条目候选原例需要作者保存的实际语句，当前研究没有编造原程序。

#5中的易码既有lang-024历史衔接和言叶／文言心→言语言lang-078关联设计证据沿用已合并结果；同作者独立版本及继承关系继续在原条目中待核。历史overview属于发现目录，按其中的具体项目与既有条目逐一排重；该入口本身构成辅助来源。

GitHub连接器按WxeEditor及作者账号补定位[WangXingwen957/Wxe-Chinese](https://github.com/WangXingwen957/Wxe-Chinese)，描述同样标为Wxe中文编程及配套WxeEditor。该仓创建于2026-04-11T09:24:00Z，size=0，提交接口返回409“Git Repository is empty”，发行集合为空。同作者名称相近仓按关联线索记录，当前可用中文语法原件继续待补。

## 议题评论草稿

### #3

2026-10-25原始资料补证与分类完成两项：RexLang按易语言风格中文编译语言收录，固定原仓6b11e5a5cc0e27b6c722db3c164e94d072710b7d保存连续中文递归子程序、ANTLR文法、C++ AST／语义分析及LLVM目标文件／链接入口；意语言按实验性设计收录，固定原作者说明f8e93ab160e174a236c88f0dbdcd39f3c30fc8c5保存完整8行中文模块，迁移说明与主仓文档已对应。测试、自举、完成度与执行能力分别按证据层级记录。

原19组现16组完成收录或范围分类。CN_Interpreter仍缺具体用户语法／完整程序；PYCH原始发行源码附件已取得并核对SHA256，剩作者完整中文原例与许可，4.1.a控制流覆盖继续待核；衍真原仓404／Git接口项目不可见，直接原件与项目身份继续待补。复合议题保留开放。四份PYCH附件均只读，安装、构建、候选运行和第三方测试执行0次。完整证据见本次研究记录及附件摘要清单。

### #5

2026-10-25已从PyPI取得Hanyu-Lang 0.1.2原始源码包，SHA256与发布记录一致，并按实验性中文语言原型收录。作者测试保留打印("测试输出")原例；有限字符串输出实现、中文词元表及解析草稿分别核验。元数据0.1.2与源内0.1.3、模板作者字段、67字节LICENSE占位和运行导入／解析集成缺口已在条目说明。GUI、完整控制流与标准库仍按发布说明分层记录。

言叶／文言心与易码沿用既有合并证据。无极仍缺原作者中文语法／程序原件，CSDN521、Gitee超时／连接重置；Wxe原仓仍仅README与MIT LICENSE，用户语法及编译器原件待补；TRAE165813原页超时，连续中文程序与正式项目身份待补。本复合议题保持开放。原始包仅静态读取，安装、导入及测试执行0次。

### #63

2026-10-25已将客舍按“中文Lisp方言设计与读取器解析原型”整理为百科条目。固定提交2ab2153a46cdab9dd04976d068f62c72b5888474保存v0.1.0-alpha规范、阶乘原例与ClojureScript分词／模板解析源码。规范路线图、解析原型和宿主求值能力分层记录；代码Apache-2.0与规范CC BY-SA 4.0分别注明。

规范署名Wang Zhangli、提交关联Fancyary与论坛FCary的直接身份对应继续待核；论坛材料按关联设计记录。完整程序运行、宿主接入与规范覆盖继续在条目中待核，当前可完成的语言设计分类已经落实。原仓设计子项完成收录；FCary与仓库的跨账号直接互链及阶段对应仍为实质剩余，本议题保持开放。

## 访问边界与覆盖

GitHub资料优先通过连接器读取；附件及PyPI由受限网络失败后获准的公开只读下载取得；Gitee和GitCode使用公开Git传输读取，不安装执行第三方。全部操作为读取与本地百科编辑；本组没有push、PR、合并、评论和关闭动作。自动审批拒绝0次。

检索围绕既有候选名称与精确原始URL，采用GitHub、PyPI、Gitee、GitCode、CSDN、Emacs China与TRAE原站。意语言和RexLang已用Git原件补足此前网页访问缺口；其余访问失败的具体状态在结果表保存。GitHub连接器检索WxeEditor及作者账号，补定位同账号Wxe-Chinese空仓；zhf888仓库搜索返回0项。精确检索PYCH／ioiiooo、zhf888／wuji及衍真原地址继续未取得新的可靠程序原件。索引遗漏、删除内容、仓外发行及历史变动保留覆盖风险。

## 本地核验

新增JSON对象、主数据与候选集合一致；四项代码与固定Git／sdist原件逐字比对；四项HTML正文与JSON字段一致；HTML本地资源链接、ID唯一性与JSON解析已核。Git diff空白检查通过。仓库无适用CI配置及测试脚本；候选临时ID与目录最终数字分配由集成阶段统一完成。
