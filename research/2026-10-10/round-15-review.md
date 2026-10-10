# 第十五轮独立静态审阅

审阅日期：2026-10-10。审阅时窗：21:36—21:45 UTC。百科基线：`757ddd0d875cb114b7261e389aa9a8a002f86c80`。

## 结论

本次独立重取的关键原始来源支持文言、言序、csg、Zechariah、LightLang、zlang和知语言七项稿件的分类、展示原例与主要实现描述；壬通按视频画面证据另行审阅。当前审阅发现的阻断性事实错误为0项。三处精确化建议已在整合稿落实：Zechariah明确.NET 8框架依赖式发布配置；csg生成提示名明确为“去掉扩展名的原文件名加`.g.cs`”；壬通视频跳转点统一为558秒。下文保留建议及原始证据，供追溯。

文言与言序保留原JSON的全部字段、ID和名称，旧字段原值完整存于本轮日志；原JSON的2条项目引用与原详情页额外3条引用全部进入新对象。LightLang按Issue #31旧候选补证，计数应为旧候选正式化1项、真正新发现0项。

研究边界：读取公开网页、GitHub文件和Git/发行元数据，进行原文对照及本地JSON数据检查。项目安装、编译、运行、测试及发行制品执行均保持待核实；本次检查没有执行目标项目代码。

## 建议修订

### P2：Zechariah Windows环境可以从泛化待核字段提升为精确配置事实

稿件已经正确地把便携分发描述与独立运行结果分开。固定`compiler/compiler.js`提供更细的配置事实：

- `findCsc`优先查找.NET Framework的`v4.0.30319/csc.exe`，随后检查`dotnet`命令。
- `compileLauncherCS`的dotnet分支在第224行指定`net8.0`，第227行指定`SelfContained=false`；第238行发布参数再次明确`--self-contained false`及`win-x64`。
- 构建函数复制C#启动器、Node可执行文件及`_payload.js`。固定树中实际保存`gui/node14.exe`、根`node.exe`与若干打包样例。

建议将环境句写成：“Windows启动器提供.NET Framework csc路径和目标net8.0的dotnet发布路径；dotnet路径采用框架依赖式单文件配置。目标机环境、依赖闭合及实际运行兼容待核实。”项目README的“三文件捆绑”继续作为作者分发说明记录。

原件：[固定编译及打包入口](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/compiler/compiler.js#L98-L298)。

### P3：csg生成提示名的措辞

稿件写“AddSource使用原文件名加`.g.cs`”。实际调用为`Path.GetFileNameWithoutExtension(csg.Path) + ".g.cs"`。建议明确为“去掉扩展名的原文件名加`.g.cs`”，以精确表达`这是测试类型.g.cs`这一形式。

原件：[生成器第51行](https://github.com/lindexi/lindexi_gd/blob/bba0c728bbc1d850f6f1929ab14a42e995e23e3b/JelallnalukebaqeLairjaybearjair/JelallnalukebaqeLairjaybearjair.Analyzers/CsgIncrementalGenerator.cs#L27-L52)。

## 展示原例逐字核验

五个文件均经GitHub只读接口独立重取，与本轮JSON的`code`值比较一致。比较保留原缩进、空行、标点与字形，仅按各稿已说明的展示边界取连续行；csg去掉文件首BOM。

| 条目 | 固定连续范围 | 原件blob | 结果 |
|---|---|---|---|
| Zechariah | `demo2.zc`第5—12行，8行 | `57b294aa3a8debe2c012d0a034f919c34ce4fca3` | 一致 |
| csg | `这是测试类型.csg`第1—11行，11行 | `328d351d05d8a86f2900b628f1381b46f54d41ec` | 一致；去BOM与末尾换行已披露 |
| 文言 | `examples/fibonacci.wy`第1—11行，11行 | `0236b22e3eff4fb0fd51a7f2c1a68b90c7454fbb` | 一致；原制表符保留 |
| 言序 | `examples/初见.yx`第1—13行，13行 | `cda7ec47e5676e19fdeb7ec4e9a439d67c54a89f` | 一致 |
| LightLang | `examples/hello.lt`第1—11行，11行 | `3599e1be5eede0603cb7c8e0cf812d9a528ac69d` | 一致 |

原例链接分别已位于各JSON的`code_source`中。LightLang旧README五行输入判空原例继续保存在日志中，保留原ASCII比较符与中文标点。对字符串比较的语义范围已有具体源码提示，采用`hello.lt`完整函数作为当前展示原例合适。

## Zechariah：分类与运行范围

独立读取`lexer.js`、`parser.js`、`codegen.js`、`compiler.js`、`interpreter.js`、`run.js`、`README.md`及`package.json`。

- 词法集合确有21个中文关键词。解析器独立构造条件、次数循环、while、函数、返回、遍历与异常处理节点。
- 编译入口先`Parser.parse`，再`Codegen.generate`，写出JavaScript。生成器按AST输出JavaScript控制结构；函数参数写入共享`__v`变量表。稿件把作用域、递归重入和恢复语义列为待核，符合静态证据范围。
- `run.js`调用另一个逐行解释器。该解释器明确匹配“用插件、显示、设、若、循环、说”；函数、返回原例对应AST编译路径。稿件将两条路径分别记录，分类成立。
- `package.json`为0.1.0并声明MIT；完整树49项且`truncated=false`，许可证文件名匹配结果为0。正式Release v1.0.0发布于2026-08-22T13:18:30Z，`prerelease=false`、附件数组为空，标签指向`acd3fb2a…`。这些不同版本来源的分层记录准确。
- AI对话插件属于产品功能。依赖清单存在`astra-cli`，Git历史保留`.trae/specs`删除路径；这些可作为开发工具材料线索，具体使用过程、模型、文件贡献和比例仍需进一步原始证据。稿件当前保留待核范围稳妥。

原件：[词法集合](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/compiler/lexer.js#L5-L9)、[解析器](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/compiler/parser.js)、[生成器](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/compiler/codegen.js)、[逐行解释器](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/interpreter.js)、[Release](https://github.com/qbr12/hbr-c.zc/releases/tag/v1.0.0)。

## 文言与言序：执行链、历史及发行

### 文言

独立重取`src/parser.ts`第670—798行及`src/execute.ts`。前者依次展开宏、分词、构造ASC、按`strict`进行类型检查、调用所选转译器并递归处理导入；后者在求值前检查`lang`，可见内置执行目标为JavaScript。多目标源码生成与内置执行接口的边界准确。

Git根提交`d58e01c1…`的`parents=[]`，作者与提交者时间均为2019-12-08T20:22:01Z。根`example.txt`包含简体中文阶乘、异或及快排例程。固定CHANGELOG的v0.3.0段明确说明迁移TypeScript。当前LICENSE为MIT，署名2019-present Lingdong Huang。GitHub latest返回正式v0.3.4，发布时间2020-07-29T05:11:41Z。源码0.4.0与GitHub发行0.3.4分列、npm继续待核，符合证据。

原件：[编译链](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/src/parser.ts#L670-L798)、[执行接口](https://github.com/wenyan-lang/wenyan/blob/97f0a4b8c5a815467c5c2cac08215d722efde208/src/execute.ts)、[历史根](https://github.com/wenyan-lang/wenyan/commit/d58e01c1fcb7ec477345dda88f3686c3502cbe43)、[正式发行](https://github.com/wenyan-lang/wenyan/releases/tag/v0.3.4)。

### 言序

独立重取`src/lib.rs`第60—140行、`src/main.rs`第235—320行及状态文档。`parse_named`依次扫描、解析、名称解析；`run`、`run_file_with`进入Interpreter。CLI的`run_vm`先`bytecode::compile`，再`Vm::execute_in_directory`；类型检查另有`check_file`入口。稿件采用“源码中分别可见”而未把所有环节强串为每次运行的必经步骤，表达准确。

根提交`10174f4e…`为`parents=[]`，标题“拆分言序语言核心”，时间2026-07-13T17:49:56Z；该根Cargo为0.3.0-alpha.1并使用`YanXuLang/language`地址。当前状态文档确为源码1.1.20、语言规范1、YXB 1、字节码2、清单/锁2、原生ABI 2。正式v1.1.20的`published_at`为2026-07-20T10:20:31Z，附注标签对象指向`5ccfd250…`。Release原文记录1.1.18及1.1.19稳定发行缺口。

作者博客首页列文章日期2026-07-14；文章链接本身包含2026/07/13。直接文章读取仍为Cache miss。稿件按页面显示日期与URL分别记录，准确。

PR #8确来自`codex/yanxu-1-1-7-gui`且已合并；合并消息含`[codex]`。PR #9标题为`[codex] Refresh GUI lock after main finalization`，亦已合并。当前措辞为公开开发命名线索，具体AI过程与比例待核，符合证据强度。MIT署名2026 Yanxu contributors亦准确。

原件：[树解释入口](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/src/lib.rs#L71-L124)、[VM及检查入口](https://github.com/YanXuLang/yanxu/blob/5ccfd2503693d0ab7d2ca27dcca525d219e2b16d/src/main.rs#L243-L305)、[拆分根提交](https://github.com/YanXuLang/yanxu/commit/10174f4ec04629f89adc85467df4281a80aadbcd)、[Release](https://github.com/YanXuLang/yanxu/releases/tag/v1.1.20)、[作者博客首页](https://blog.liuxiu.us/)、[PR #8](https://github.com/YanXuLang/yanxu/pull/8)、[PR #9](https://github.com/YanXuLang/yanxu/pull/9)。

## LightLang：旧候选同源及Rust编译链

独立读取Issue #31正文及全部1条评论，确认旧候选原仓是`gitcode.com/NomiLight2026/lightLang`。

- `07a25c1766f992e2debd2c9a6c4955882c3516e4`的提交消息明确为`Merge branch 'main' of https://gitcode.com/NomiLight2026/lightLang`，双亲为`84b1b2f…`与`3552c8d…`。后续`371da53…`亦保留GitCode地址与两个父提交。两条可见历史支持把GitHub入口与原候选作为同一历史对象记录；当前同步状态继续待核的边界恰当。
- 中文词元、Unicode标识符、类型推导迭代、AST至LLVM文本生成可见。`lightc/src/main.rs`递归读入源文件，调用词法与语法分析，合并Program，再进行推导、IR生成、Clang编译及静态运行时链接。
- `light/src/main.rs`将历史会话与当前输入重新组成源文件，调用lightc，再执行生成程序；`lightgo/src/main.rs`调用Cargo构建FFI静态库，以`--native`参数传给lightc。稿件对临时编译运行与REPL重编的描述准确。
- 五个Cargo清单均为0.2.1。0.2.0标签指向`d507d3a…`；GitHub发行集合为空。现存双根时间分别为2026-09-25T04:53:46Z和04:56:45Z，仓库创建时间05:19:32Z。旧GitCode发行侧栏与GitHub标签/源码分层恰当。
- 固定LICENSE开头确为GPL第3版，具体项目版权署名继续待核。`gen_cmp`确以浮点`fcmp`及其他类型`icmp i64`生成比较；稿件保留README输入判空示例的字符串语义风险。

原件：[Issue #31](https://github.com/yuyan-lang/chinese-programming-languages/issues/31)、[原仓地址合流提交](https://github.com/oneone1565/LightLang/commit/07a25c1766f992e2debd2c9a6c4955882c3516e4)、[后续合流](https://github.com/oneone1565/LightLang/commit/371da53cf89efcdce178fb7d9fbab20e855903ae)、[主编译入口](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightc/src/main.rs#L109-L245)、[light执行入口](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/light/src/main.rs#L243-L330)、[FFI构建入口](https://github.com/oneone1565/LightLang/blob/38aa05b295a53a2591617a5c3bc8f7b08595de25/lightgo/src/main.rs#L297-L374)。

## csg分类及文风、保留项

csg生成器独立重取确认：`.csg` AdditionalFiles筛选、六组带尾空格的整行字符串替换、Source Generator的AddSource与`系统.控制台`包装API均吻合。当前“C#中文关键字翻译层／Source Generator教学实验”的分类贴合实现边界。

已先读取基线AGENTS.md。稿件整体采用直接事实陈述与“待核实”缺口表达；分类段落避开正反对照论证。文言/言序状态里的“未归档”属于明确元数据状态，亦可统一写为`archived=false`以贴合其余条目。AI待核句在文言、言序和csg的`verification_notes`末尾有重复，整合时可作纯编辑性去重。

基线详情页独立重取所得原引用：

- 文言：主仓、Syntax-Cheatsheet、master版fibonacci.wy。
- 言序：主仓、yanxu.dev。

这5条URL均在新JSON中保留。旧页4行文言问天地例程、5行言序问候例程与旧JSON对象已逐字保存在本轮对应研究日志。各稿使用的固定源码和历史时间分别保留，声明与独立运行结果的层级清楚。

## 审阅范围余项

本次侧重关键原始来源、分类、原例、时间/版本、许可/AI边界及旧资料保留。全部检索结果、目录排重查询及csg网页沿革的复抓范围有限；本报告逐项说明独立复核所得，最终目录计数、页面生成与链接完整性由整合检查记录。

## 追加审阅：Gitee两项中文语言

追加时窗为21:42—21:45 UTC。普通网页抓取器对两个固定页面报告不可访问，随后通过公开网页浏览器正常读取同一公开页面；全程保持只读。登录提示文件的内容继续保留待核范围。

### zlang（calvinwilliams）

- 固定`doc/chinese_programming.md`的`test_factorial_chinese.z`代码块与稿件19行原例逐字吻合，包含`charset "zh_CN.gbk"`、原有空行、8/16空格缩进、库名和末尾换行。紧随其后的720确为作者文档的展示输出。
- 中文章节直接说明关键字、函数名、对象名和变量名的中文支持；示例中的“导入、函数、如果、否则、返回”组成实际语言结构。
- 固定`charset_UTF8.h`保存“主函数(array)”入口和“如果、函数、对象、接口、返回”等词元别名。固定`lexical.c`实际包含`MATCH_ALL_CHARSET_ALIAS(GB18030)`和`MATCH_ALL_CHARSET_ALIAS(UTF8)`分派，并写入`TOKEN_TYPE_IF`、`TOKEN_TYPE_FUNCTION`等内部类型。稿件的中文词元及编码说明具有源码依据。
- 固定根LICENSE明确Apache License 2.0；`charset_UTF8.h`也保留Apache-2.0许可头。依赖许可范围单列待核合理。
- 固定ChangeLog-CN独立重读确认：0.0.1.0的2022-03-22为创建项目；0.0.2.0的2022-05-29为跑通hello.z；0.2.1.0的2024-02-08为开始支持中文编程；0.2.1.1的2024-02-09为官方存量对象添加中文别名；0.12.8.0日期为2026-09-22。稿件把项目历史与中文支持历史分开准确。

原件：[中文章与19行原例](https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/doc/chinese_programming.md)、[UTF-8词元](https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/src/zlang/charset_UTF8.h)、[编码与中文分派](https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/src/zlang/lexical.c)、[根许可](https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/LICENSE)、[版本日志](https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/ChangeLog-CN)。

### 知语言（知心编译器）

- 固定`src/zhi.c`第52—71行与稿件连续20行片段一致，保留中英文`如果/if`、`返回/return`混用、变量名、符号与缩进。它是主函数中的局部片段，闭合块在后文；稿件的代码上下文准确披露这一点。
- 固定`src/token.h`第19—36行确为GBK和UTF-8的中文数据类型词元，第51—72行确为“如果、否则、选择、分支、执行、判断、循环、继续、转到、跳出、返回”的双编码词元。结合实际中文编译器源码，中文C方言/TCC衍生分类适当。
- `zhi.c`开头保留Fabrice Bellard的2001—2004版权、位中原的2019—现在版权，以及基于TCC开发的项目自述。版权起年与首次公开日期分开记录，准确。
- 固定根LICENSE页面及正文明确木兰宽松许可证第2版/MulanPSL-2.0。根许可、上游来源与各组件适用范围分层记录恰当，完整衍生许可范围继续待核。
- 0.9.30发行页独立重读显示最新版`zhixinV0.9.30`、发布者位中原、2025-04-01 14:46、短提交`bea6483`，说明同时支持`main()`和“开始（）”函数，附件列表含知心编译器.zip。稿件记录吻合，附件内容与自举效果仍属于待核范围。

原件：[实际编译器中文片段](https://gitee.com/zhiyuyan/tcc/blob/04434cfef8000dd8f9868816016abdeb0f6b0214/src/zhi.c#L52-L71)、[双编码中文词元](https://gitee.com/zhiyuyan/tcc/blob/04434cfef8000dd8f9868816016abdeb0f6b0214/src/token.h#L19-L72)、[根许可](https://gitee.com/zhiyuyan/tcc/blob/04434cfef8000dd8f9868816016abdeb0f6b0214/LICENSE)、[0.9.30发行页](https://gitee.com/zhiyuyan/tcc/releases/tag/0.9.30)。

两项的AI开发参与继续标为待核，正文没有把编译器来源、中文代码或平台AI按钮当作模型生成事实。

## 追加审阅：壬通原片截图

已直接查看两张保存的原样截图，核对图像内容与日志哈希：

- 09:18.450237帧的播放器界面显示09:19；主程序.cpp第11行可辨“返回 0;”，下一行是闭合花括号。输出区可见编译成功状态。该帧SHA-256为`084a5f1afeefa72f2d76e8304e51b324934d5c4cea2640e38713245ff22d8291`。
- 08:43.826018帧的播放器界面显示08:44；输出区可辨C++标准库`std::basic_istream`及`get`相关诊断。该帧SHA-256为`b0440d2f3c68e375d542296fd8c172ad316bbd05a5537c35f75db38202d7a893`。

两张图的图像内容、整数时间显示和哈希均与日志相符。单行原例的缩进省略已披露；中文前端实际保存内容、映射/转译机制与具体编译器继续待核，证据边界适当。录像中的编译成功和报错属于发布者演示结果，独立运行状态维持待核。

精确小数暂停时间及发布日期来自研究记录的原站DOM元数据，本次追加审阅重点为保存图像的独立目视与哈希复核。图片自身能证明其播放器整数时间显示，精确小数时间应继续与元数据记录一并保存。

P3链接定位建议已落实：原例对应558.450237秒，整合稿已将原有`t=553`统一调整为`t=558`，让读者更接近已保存帧；精确暂停值仍在上下文中保留。

原片：[BV1DaBaBNEE9](https://www.bilibili.com/video/BV1DaBaBNEE9/?t=558)。截图：[中文返回语句帧](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/evidence/BV1DaBaBNEE9-09m18s.png)、[C++诊断帧](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/evidence/BV1DaBaBNEE9-08m43s.png)。
