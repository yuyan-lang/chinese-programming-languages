# Issue #3、#5、#48：历史原件、原图与范围分类

核验日期：2026-10-28（UTC）。百科基线为4e00d5240ff5ca99c745c2b00179c11e42bef800，110项语言、20项内核。本组从该提交建立独立贡献分支`contrib/issues-3-5-48-20261028`，保留PR #79全部数据、原例、引用和研究记录。

已读根AGENTS.md、三个议题正文及全部24条评论、当前目录、2026-10-25本组及E#记录、第七轮PYCH记录、第十六轮E#记录。仓库及任务根目录的`.agents/skills`均未提供文件。本轮新增一项可审阅语言对象，完成CN_Interpreter固定材料的范围分类；复合议题继续保存实质未决子项。

## 可审阅修改

[中文编程IDE（天文苑）候选对象](issues-3-5-48-candidates.json)依据TRAE作者原帖及程序原图整理；对象同步进入[data/languages.json](../../data/languages.json)和[详情页](../../languages/lang-111.html)。集成阶段分配正式ID lang-111。其他110项对象按JSON深度比较保持一致，原有字段、原例和引用全部保留。

原始资产、公开Git引用与完整提交清单保存在[证据清单](issues-3-5-48-evidence.json)。本轮取得17份PYCH原始附件、E#／CH-VM／易深IDE三个公开Git仓库、TRAE主题JSON和四张原始附图。安装、构建、导入、浏览器加载候选软件及候选程序执行均为0。

## #5 TRAE辅助线索：原帖与完整中文原例已取得

[原始主题](https://forum.trae.cn/t/topic/165813)的[公开JSON](https://forum.trae.cn/t/165813.json)本轮可读取，61005字节，SHA256为`7ad5a798541a032d2da21f87ded308f575a71a4fe5cea567aedea1d9fdd7f33f`。主题共1帖；首帖ID280497，账号u701959982292476，展示名“天文苑”，创建时间2026-07-15T10:57:35.281Z，当前公开修订时间2026-07-15T12:30:25.597Z、版本8。

原帖直接提供[代码运行效果原图](https://trae-forum-cdn.trae.com.cn/prod/original/3X/2/0/20407b70c24da7f2b4e5a43cc5e0127cc191eb50.png)。图左侧第4—10行保存完整圆面积函数及调用：制作工序声明、知定义常量、设定义变量、返回及函数调用。条目按图转录连续7行，保留全角乘号；缩进和换行采用可读排版，原始`.中码`文件字节待核。原图为47578字节，SHA256为`8a115ed4846deaf807ab58bc326867192a5371c8c50c5d23fdc4839d1658392d`。

同图另显示变量、当／不然分支和从／到循环，右侧保存作者演示输出；[基础输出原图](https://trae-forum-cdn.trae.com.cn/prod/original/3X/e/7/e7e2b7cac2bdba570baff7d95828604eb47b39af.png)提供消息赋值与显示两句的完整独立示例；[帮助原图](https://trae-forum-cdn.trae.com.cn/prod/original/3X/3/7/37ba014ed303678a71525c584c8034435652ce4f.png)明确展示中文语法说明。界面右下角版本为v1.0。

作者正文明确说明使用TRAE Work及TRAE IDE分工开发，介绍词法分析、语法解析、JavaScript生成和多平台导出。上述实现能力按作者自述记录。原图核实的界面、中文原程序与作者演示分别保留证据层级。原帖直接链接`https://ide.tianwenyuan.com`，静态HTML请求返回403；原帖链接的报名主题33589的公开JSON返回404。固定源码、发行包、许可与独立运行继续待核。当前资料已达到文档及原例层面的收录范围。

## #3 CN_Interpreter：固定材料归为理念草案

本轮直接读取[根提交README](https://github.com/whitesnowmoon/CN_Interpreter/blob/1c13f1e8d402645f69ee3c98fce48c3dac95c000/README.md)和[第二次提交README](https://github.com/whitesnowmoon/CN_Interpreter/blob/3ac37ea85dc8e17a0fcd579c7c7dd4659f85f0ab/README.md)，均为标题和“中文编程语言”两行。两次提交时间分别为2025-05-06T06:21:11Z、2025-05-06T06:22:11Z。

与此前已核[头提交4c07321166a4a697fe6c7ca3c717e7e07abca2fa的README](https://github.com/whitesnowmoon/CN_Interpreter/blob/4c07321166a4a697fe6c7ca3c717e7e07abca2fa/README.md)合看，所核三次提交保存中文编程理念；最后一次提出指令、语境和释义三种设计方向，并以“机器开机”解释主谓关系。该例属于设计讨论中的自然语言句子。具体用户语法、句法规则和完整程序仍待作者材料支持。

本轮范围结论为“中文编程理念草案”，保存为研究记录。正式语言目录继续采用具体用户语法或原始程序的标准。该固定阶段的分类已经完成；以后取得作者具体规范或原例时重新评估。Issue #3原19组可记17组完成收录或范围分类，PYCH与衍真继续待核。

## #3 PYCH：全部公开发行附件的静态覆盖

按[作者发行集合](https://github.com/qingsububao/PYCH-Language/releases)逐项取得8个发行的全部17份Python资产，共81255字节，全部SHA256与GitHub发行元数据一致。上轮仅覆盖pych0、4.0及4.1.a两份附件，本轮补齐pych1.0、2.0、3.0、3.1、3.2，重点核对历史原例、注释和交互提示。

| 发行 | 附件数 | 静态内容 |
| --- | --- | --- |
| pych0 | 1 | 中文变量、数字、打印及括号识别早期实现 |
| pych1.0 | 5 | 标识符分派、数据转换、交互文件读取和辅助函数 |
| pych2.0 | 5 | 嵌套匹配辅助测试、等价替换与未完成递归函数 |
| pych3.0 | 1 | 递归求值整合及文件读取 |
| pych3.1 | 1 | 交互／脚本选择提示 |
| pych3.2 | 1 | 数字和算术实现 |
| pych4.0 | 1 | 布尔、算术和比较实现 |
| 4.1.a | 2 | 控制流分派草稿与文件执行处理 |

[pych2.0/tool.py](https://github.com/qingsububao/PYCH-Language/releases/download/pych2.0/tool.py)资产479444999，2753字节，SHA256为`ebb8d2fc0ff6f02b57d21cb59648ade79b90be5eadf577a4635e9714a327d786`。第93行保存对`matchmethodsparentheses`的嵌套参数测试，使用方法1、方法2等占位名。该字符串用于辅助函数匹配测试，完整用户脚本仍待补。文件末尾`nestedrecursion`的`else`分支为空；静态AST读取报告待补缩进块。该检查只构建语法树，候选代码执行0次。

发行说明、Python字符串字面量、注释、提示和源码全文均已静态检查，17个附件只含Python源码；公开发行资产集合未列README、独立`.pych`原程序、视频或演示压缩包。当前可确认中文语法实现方向，作者完整中文用户程序、规范原例与许可正文继续待核。原有源代码及7月发行证据继续保留，当前材料维持候选状态。

## #48 E#：公开历史、ESIL与CH-VM关系

[E#原仓](https://gitee.com/dcosa/esharp)的正常公开Git克隆本轮成功，HEAD仍为[55503b2e623e3093d9c6423b63aa6b006adaaf32](https://gitee.com/dcosa/esharp/commit/55503b2e623e3093d9c6423b63aa6b006adaaf32)，作者时间2023-06-02T19:46:11+08:00。公开引用含master及一个0.1.0-end.preview标签，全部可达历史10次提交已检查；历史`.md`、`.c`、`.h`共32个不同文本blob。

固定`E#规范.md`为464字节、58项词语；当前`src/main.c`为0字节，`test/main.c`返回0。历史`compiler/main.c`、`AsmCompiler/main.c`、运行入口及README各版也已检查，所核程序材料保存C占位入口与运行时结构。标签[c090f0d80ca5fb6855513b906cb6a321db52903c](https://gitee.com/dcosa/esharp/tree/c090f0d80ca5fb6855513b906cb6a321db52903c)保存ESRuntime、ESIL及.esb／.esl格式设计。历史[ESRuntime/instset.h](https://gitee.com/dcosa/esharp/blob/c090f0d80ca5fb6855513b906cb6a321db52903c/ESRuntime/instset.h)注释明确提出在易语言上改进E#、编译为ESIL、由ESR解释执行的方案。该注释按开发计划记录。

由[DCOSA原组织页](https://gitee.com/dcosa)明确链接，取得[CH-VM原仓dcosa/vm](https://gitee.com/dcosa/vm)完整5次提交。固定头为[2e3185eecf440de9e311ce7255577cb56717079f](https://gitee.com/dcosa/vm/commit/2e3185eecf440de9e311ce7255577cb56717079f)，时间2023-06-08T23:28:00+08:00。[CHIL规范.md](https://gitee.com/dcosa/vm/blob/2e3185eecf440de9e311ce7255577cb56717079f/CHIL%E8%A7%84%E8%8C%83.md)与E#旧`ESIL.md`的声明标记及条目内容相同，差异集中在标题、Markdown层级和空行；按非空行去除标题标记后逐项比较，正文相同。这提供规范文本延续的直接证据。

[CH-VM规范](https://gitee.com/dcosa/vm/blob/2e3185eecf440de9e311ce7255577cb56717079f/CH-VM%E8%A7%84%E8%8C%83.md)定义.chl／.chr、文件头、元数据和指令；`ch-vm/core/vm/vm.c`、`stack.c`保存程序环境、调用帧与栈的分配原型。`chilc/main.c`和`ch-vm/main/main.c`为返回0的占位入口。E#头README已明确定位为基于CH-VM的语言；可核结论为从ESRuntime／ESIL方案到CH-VM／CHIL方案的文档关系，完整二进制兼容及语言前端调用链继续待核。

同组织的[易深IDE](https://gitee.com/dcosa/yishen)也取得完整5次提交，固定头[70c5e0b40aadf8bbd3f5dcb48061175e06389d4b](https://gitee.com/dcosa/yishen/commit/70c5e0b40aadf8bbd3f5dcb48061175e06389d4b)，时间2021-07-05T14:19:44Z，标签v1.4-alpha。README署名再见理想和云之梦歌，环境为Qt／VS2019。`KoCode/VTranslation.cpp`保存整数型→int、如果→if、主函数→main等中文C映射；`VBackgroundSystem.cpp`保存转换后写出文件的路径。这是可单独核实的中文C转换界面源码。该版本与E#的完整语法／发行集成关系继续待核，中文C映射材料单独归类。

本轮解决E#正常源码访问及部分文档沿革缺口。完整中文用户程序、具体中文句法规范或原例、实际语言前端仍有实质缺口；#48保持开放。正式目录新增0项，词表保持原词表身份。

## #5 无极、Wxe与#3衍真：有界补证与剩余阻塞

无极沿作者公开资料补查：[作者首页](https://blog.csdn.net/qq_28759809)和[中文编程专栏](https://blog.csdn.net/qq_28759809/category_9822853.html)均将原文章记为原创，时间2020-03-20 10:49:45，时区待核。正文可读部分明确项目暂名无极，链接zhf888/wuji，并自述C／lex／bison设计方案；用户语法部分进入VIP提示。作者列表所见16篇原创及4项资源、中文编程专栏2篇，继续未取得另一份公开完整语言原例。官方移动原文返回521，正常Gitee Git传输连接重置。剩余缺口为可公开核对的中文程序／语法原件与实现文件；本轮停在公开可读范围。

Wxe沿新文档路径核对原仓公开Wiki，正常`git ls-remote`返回Repository not found；同作者`neurolixir-ai`仓库的Wxe定向代码检索返回0项。沿用上轮原仓README＋MIT LICENSE及Wxe-Chinese空仓证据。实际用户语法、原程序及WxeEditor／编译器原件继续待补。

衍真采用正常Git传输读取`nextOS/yzcc.git`，返回403及project could not be found。继续沿原命名空间读取[nextOS组织主页](https://gitcode.com/nextOS)及其[公开仓库列表](https://gitcode.com/org/nextOS/repos)，两页HTML读取成功。列表可见18个不同nextOS项目路径，涉及seL4、Android ART、Godot及配套库；两页公开HTML中yzcc和衍真命中均为0。组织首页项目说明关注seL4架构。可核结论限定为当前公开列表与原地址状态，历史语言仓库的迁移、删除或访问条件继续待核。原中文程序搜索缓存与身份候选保持原证据层级。

## 评论草稿

### #3

2026-10-28完成CN_Interpreter固定材料的范围分类：两份前序README仅为标题，头提交4c073211的内容为指令／语境／释义设计讨论，现阶段记为“中文编程理念草案”，保存在研究记录。原19组现17组完成收录或范围分类；正式语言目录继续以具体用户语法或原始程序为依据。

PYCH本轮取得8个发行全部17份原始Python资产，共81255字节，SHA256全部一致。补读历史附件、注释、字符串及交互提示，pych2.0/tool.py仅保存辅助括号匹配测试；完整中文用户程序仍待补。衍真继续检查正常Git入口和可读nextOS组织列表，原语言地址不可见，公开18项目列表未给出迁移互链。PYCH、衍真两项继续待核，本复合议题保持开放。证据及资产摘要见本轮研究记录，候选执行0次。

### #5

2026-10-28取得TRAE165813原作者主题JSON与程序原图，按“中文教学语法与浏览器IDE演示”整理中文编程IDE（天文苑）条目。原作者为u701959982292476，首帖时间2026-07-15T10:57:35.281Z。原图保存制作工序定义圆面积函数及调用、中文常量／变量／返回，以及作者输出演示。界面v1.0、JS生成自述、TRAE参与和源码／许可待核分别记录。

无极补得作者公开首页与专栏的原创时间2020-03-20 10:49:45，中文用户语法原件继续受公开可读范围限制；Wxe新查Wiki及同作者公开工件仍未取得程序。无极、Wxe保持待核，既有Hanyu、言语言和易码成果保留，本复合议题继续开放。

### #48

2026-10-28成功取得E#正常公开Git原仓并静态核对全部10次提交、master和0.1.0-end.preview标签。连续中文程序及具体句法原例继续待补；当前材料为58词表、ESIL／字节码结构设计及运行平台原型。

本轮经DCOSA原组织页取得CH-VM全部5次提交，固定2e3185ee的CHIL规范与E#旧c090f0d8的ESIL规范正文相同，标题／排版分别记录；E#头README明确基于CH-VM。CH-VM程序环境／调用帧／栈有分配原型，编译器和运行主入口为占位。易深IDE固定70c5e0b4为2021年中文C映射工具，具体E#前端集成待核。文档关系已推进，完整中文用户程序和语言前端仍是实质缺口，议题保持开放。固定原件、提交时间和静态边界见研究记录；候选运行0次。

## 本地审阅与操作边界

本次变更为新增候选数据、对应HTML、研究记录及源资产摘要。基线110项语言对象按字段、原例和引用完整保留；原有研究文件及内核数据保持原样。百科JSON与HTML一致性、临时ID唯一性、本地链接、源图SHA256与Git空白差异检查均已通过。17份PYCH附件摘要一致性与nextOS公开列表18路径也已核对。仓库无适用CI配置及测试脚本。

读取优先使用GitHub连接器；GitHub发行附件、Gitee／GitCode公开Git与原站JSON及附图采用只读网络获取。自动审批拒绝0次。网络失败均为读取请求，精确地址及返回状态已记录；没有待定的外部写入。本组未push、创建PR、发表评论或关闭议题。未新增、配置或手动触发部署。
