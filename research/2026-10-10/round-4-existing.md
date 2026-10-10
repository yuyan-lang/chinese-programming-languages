# 第四轮既有条目：易语言、结绳中文

核验日期：2026-10-10（UTC）。本轮完善lang-002和lang-012，采用原作者文档、官网图示、固定源码与发行记录。

## 一、易语言事实—来源映射

### 作者、沿革和早期公开证据

1. 官网公司介绍 https://www.eyuyan.com/intro/index.htm
   公司称吴涛为易语言创始人；2004年与大连大有房屋开发有限公司合作成立公司。作者与公司成立年份分别记录。
2. 官网历史报道目录 https://www.eyuyan.com/intro/newslist2003.htm
   网页读到2000-10-30《电脑报》第43期《原创天地》，链接原图：
   https://www.eyuyan.com/intro/images/baodao/00-43.jpg
   实际观看图片，辨认“E语言（试用版）”“1.1版”“软件作者：吴涛”以及Windows编程说明。报道日期取官网目录，图上版本与作者取原图。此链证明2000年已有公开发行材料。
3. 维基及搜索结果中的2000-09-11完成1.0、2000-09-16上传说法，涉及作者《易语言即学即用》书序的转载。原版书序或原始发行公告待核实。本条first_publication选用可直接复核的1.1历史报道，并保留1.0精确日待核实。

### 语法、环境与实现边界

4. https://www.eyuyan.com/eprc.htm
   官方产品说明涵盖中文编程、可视化窗口设计、易模块、支持库、DLL/API/COM/OCX互操作；描述中文源程序直接编译为CPU指令。百科采用“官网产品文档描述”的证据口径。宣传性性能、安全性、普遍数据库兼容结论均保留为待核实。
5. https://www.eyuyan.com/help/zlsc/lang.htm
   完整语言手册说明文本、整数、日期时间、字节集等类型；子程序、程序集、局部和全局变量；命令和库类型由运行支持库提供；窗口事件与程序入口。手册明确命令名可与变量名重名，因此本条以“中文命令”概括其语言机制。
6. https://www.eyuyan.com/help/zlsc/day/day5.htm
   “第五天”教程正文为条件与循环说明，直接嵌入下列原图：
   https://eyuyan.com/help/zlsc/day/day5.files/image012.gif
   GIF为389×203，显示按钮被单击子程序、整数型变量1和四行循环代码。人工观看原图后转录：
   
   计次循环首 (100, 变量1)
       按钮1.标题 ＝ 到文本 (变量1)
       延时 (200)
   计次循环尾 ()
   
   code_context已标注：官方图示文字转录；空白排版整理；流程连线和折叠图标省略；局部可视化编辑器片段。文本导出格式、完整.e文件、源文件字节和运行效果待核实。转录保持图示可见命令与等号形式。
7. https://www.eyuyan.com/pdown.htm
   当日官方下载页列5.95精简版、完全版、5.9x升级包并保留5.93历史版本；5.95日期字段待核实。页面还保留EPL 4.01历史说明，列Windows窗口、控制台、动态链接库及Linux控制台开发。该历史平台说明与现代5.95兼容性分别表述。页面旧版权年份只用于识别网页。
8. https://www.eyuyan.com/prc.htm
   官方产品分类分别介绍易语言、易语言·飞扬（EF）和易乐谷（ELOGO）。EF采用类C语法和另一套核心架构；易乐谷是以易语言开发的中文LOGO工具。传统易语言条目记录自己的产品线，相关语言作为分类关系。
9. 编译器内部实现语言、完整源码、5.95发行日及维护计划、在现代系统的实际执行和性能全部为待核实。GitHub自动语言统计与第三方破解发行资料均未用于实现结论。

### 易语言访问限制

- https://www.eyuyan.com/gongneng/zzqby.htm 两次web读取超时。
- first/index.htm的框架入口在web正文抽取中为空；采用可直接读取的公司介绍、产品页和历史报道页。
- 官网新闻框架的head.htm返回404；已通过具体newslist2003.htm和原图取得所需内容。
- 搜索发现的修改版／破解5.93仓库只作为低可信检索噪声记录，未采用其中代码或发行说法。
- 旧图像可以保留历史语法和作者证据；当前产品维护能力由当日页面及独立发行记录分别核验。

## 二、结绳中文事实—来源映射

### 身份来源链及时间轴

1. 原入口 https://tiecode.cn
   当日web正文读取失败；公开网页显示502 Connection refused。站点长期状态和停维护结论待核实。
2. https://central.sonatype.com/artifact/cn.tiecode/plugin-api/1.0.1
   网页直接读取Maven Central的POM和Versions分页。POM链接http://tiecode.cn，developer为Scave，邮箱与公开开发仓库署名一致。SCM字段指向simple-lsp4a，该字段的具体仓库关系待核实。
   Versions共两页；最早可见alpha29和alpha30为2022-11-18，后有2022-11-19、20、21、22、24及12月版本；1.0.0为2022-12-14，1.0.1为2022-12-18；garma系列列2023-01-22。页面日期缺少明确时区。采用2022年11月已有生态插件API公开记录这一有限结论。语言／最初IDE首发另列待核实。
3. https://gitee.com/scave/Tiecode-Compiler
   旧编译器README含Java入口com.tiecode.compiler.Main和Main.main(args)，列Android/Linux/WebPage/Windows/iOS目标说明。浏览器显示13次提交；当前README提交bb55bd02316179c156b1ff7898f62e66beab4050，2023-11-26 23:22:35+0800，即2023-11-26T15:22:35Z。历史目标列表按其当时说明记录，逐个平台的完成度与实际执行待核实。
4. https://gitee.com/mobile-ipe
   组织自称“移动工程平台(MobileIPE)联合成员开源组织”，成员和置顶仓库含Scave、跨平台编译器、Android基础库、文档项目。
   https://gitee.com/scave 公开页面同时指向旧编译器与当前跨平台发行仓库。
5. 当前GitHub仓库 https://github.com/FinalScave/TiecodeCompiler-Public
   created_at 2026-05-31T13:58:08Z；pushed_at 2026-06-17T14:55:54Z；archived=false；default_branch=master。
   当前头688aebd0887457fd2b6ae7abefd415eafa430e04，提交2026-06-17T14:45:55Z，作者Scave，账号FinalScave，消息“更新4.7.0-beta3”。
   https://gitee.com/mobile-ipe/TiecodeCompiler-Public 显示同一头688aebd、3次提交和4.7.0-beta3标签，确认当前两处资料的对应关系。创建时间只表述该发行仓库创建时间。
6. https://github.com/FinalScave/TiecodeCompiler-Public/releases/tag/4.7.0-beta3
   完整releases API返回beta3和beta1两项；beta3 published_at为2026-06-17T14:55:55Z，prerelease=true。发布资产有预编译压缩包和校验信息。README Maven示例使用4.7.0-beta4；beta4实际发布状态另列待核实。Release正文提及构建提交2d17c930afa72f396ae5ae4f5b17872799c0112e，当前公开头与其角色分别记录。

### 固定语法原例与实现资料

以下文件固定于提交688aebd0887457fd2b6ae7abefd415eafa430e04。

7. README.md，blob c35bfe316a0ff34372805e4fd63f6bab360c2c97
   https://github.com/FinalScave/TiecodeCompiler-Public/blob/688aebd0887457fd2b6ae7abefd415eafa430e04/README.md
   仓库定位是编译器产物、文档、C/C++头文件、预编译命令行／动态库／Wasm及平台基本库。CLI说明列source 40、46、47和多平台目标。预编译资产覆盖范围、目标代码支持程度和实际运行分别核验。
8. docs/结绳语法.md，blob b9826d730f4206d93f3318156a373040ca99dfbc
   https://github.com/FinalScave/TiecodeCompiler-Public/blob/688aebd0887457fd2b6ae7abefd415eafa430e04/docs/%E7%BB%93%E7%BB%B3%E8%AF%AD%E6%B3%95.md
   全文读取，语言概览的第一完整代码块逐字保留：
   
   @强制输出
   类 主窗口: 窗口
     变量 标题: 文本 = "Hello"

     方法 创建完毕()
       调试输出(标题)
     结束 方法
   结束 类
   
   该例展示类、变量、方法、结束标记及注解。窗口、文本和调试输出依赖平台基本库。语法文档还涵盖继承、泛型、属性、事件、类型推断、运算符重载、原生代码与平台注解；输出说明列Android的Java/XML/Gradle、HTML目标的JavaScript/HTML、CXX目标的C++。
9. headers/tiec/token.h，blob ab9143df8bf7a34649a921dad9d390a5577733b3
   中文词元枚举与语法文档对应，支持“中文关键字语言”的分类。
10. docs/编译器Api.md，blob ddfe16fdde75abda03e71cc6d498cf6ec4038484
    headers/tiec/compiler.h，blob e07999e6fa7b17b189c709348388ffbb9e30985c
    集成API说明Context、NameTable、TreeTable、SymbolTable；公开C++接口列解析、符号填充、语义分析与最终输出阶段，含CompilerFactory。这支持公开C++集成API的事实。完整内部实现和所有后端源码待核实。
11. headers/tiec/cxx/cxx_output.h，blob b016e86f81a41426a23acd43aeb9b9b6e30d91dc
    CxxProductInfo.src_path明确注释“C++源码输出路径”，与CXX目标源码生成说明互证。
12. docs/原生代码绳包封装.md
    .d.t用于原生平台声明封装；其中正则提取器的说明属于封装辅助工具，其实现与主编译器的语法处理分别记录。
13. recursive git tree完整返回，truncated=false。所见结构含文档、headers、prebuilt及stdlibs；库中可以包含C++源码。整个编译器内部实现源码的公开完整性待核实，repo自动语言统计Raku未采用。

### 实际工具链代码与版本拆分

14. https://github.com/mobile-ipe/Tiecode-VSCode
    固定提交d3c261f4cb2742ab0256fe1d767c783dbe41c711，时间2026-06-12T15:33:29Z，作者Scave。
15. package.json，blob2575ddde265a9ff8c9fc0f2521b89b85c14b6395
    https://github.com/mobile-ipe/Tiecode-VSCode/blob/d3c261f4cb2742ab0256fe1d767c783dbe41c711/package.json
    version 0.1.1，publisher Scave，语言别名Tiecode／结绳，.t源文件及.tly布局文件。插件MIT许可按插件范围识别。
16. src/tiecode/build.ts，blob a74562175928b7133d824f6f9c3ca2da30eba699
    https://github.com/mobile-ipe/Tiecode-VSCode/blob/d3c261f4cb2742ab0256fe1d767c783dbe41c711/src/tiecode/build.ts
    已读88–91行调用tiec.wasm compile并进入runGeneratedProjectBuild；120–136行Android接Gradle；154–173行CXX接CMake。这支持“先生成目标工程，再接平台构建”的静态流程。
17. https://marketplace.visualstudio.com/items?itemName=Scave.tiecode-vscode
    原发布者商店资料与README功能描述对应。
18. https://gitee.com/mobile-ipe/Tiecode-AndroidLib
    平台库README和许可具有自身范围；主编译器整体许可待核实。
19. https://gitee.com/mobile-ipe/tiecode-document-project
    社区维护的官方及公开群文档归档。其维护说明用于来源关系，页面相对时间未直接转作语言发布日期。

### 结绳访问限制和谨慎取舍

- 旧Gitee仓库commits页面跳转登录；停在登录页，历史最初提交待核实。
- 官网502按本次访问状态记录，持续维护状态由可访问仓库与发行记录表述。
- CSDN“135万Java、1.5万Kotlin”等数量为第三方宣传线索；内部代码量与实现构成待核实。
- GitHub发行repo、VSCode插件和Android基础库各有自己的内容和许可，版本、语言统计、许可和历史分别记录。
- “TieLang”等仅见于第三方检索的别名尚缺作者资料支持，别名目前采用Tiecode与结绳。
- 平台输出说明属于静态资料；命令行、Wasm、Android及CXX实测与性能均为待核实。

## 三、同名Sheng辅助线索

本段用于结绳名称消歧与未来核查，本轮完善对象为两条既有条目。

- 精确原仓库入口：https://github.com/luojiahai/sheng
- 来源链：https://pypi.org/project/sheng/0.1.18/ 的Homepage、Bug Tracker和build badge分别直接指向该仓库、该仓库issues及python-publish.yml。
- 公开网页直接读到项目说明“The Sheng Programming Language”，中文名称“结绳”，作者luojiahai，PyPI维护者ljiahai；说明编译器以Python与PLY实现，要求Python≥3.9；.zh为示例文件后缀。作者实名与Tiecode作者之间的关系待核实。
- 0.1.18发布时间页中含明确时区2021-11-15 05:43:30 (-08:00)，即2021-11-15T13:43:30Z。
- 作者发布页保留的README式项目说明含两行连续中文原例：
  甲 赋值 "你好，世界！"
  打印(甲)
- 本轮直接请求GitHub仓库与README.md均返回404；当前仓库内容、可访问状态和固定提交待核实。上述语法和作者结论来自PyPI作者发布页。
- PyPI 0.1.1搜索结果另见较早的“语句 赋值 字符串 开始 你好，世界！ 结束 / 打印 语句”形式；版本语法各自记录。当前条目不引用Sheng代码。
- 本条lang-012沿既有tiecode.cn身份来源链整理；Sheng沿luojiahai／PyPI身份来源链单独保留辅助线索。

## 四、实际检索平台、关键词、时间范围

检索时间为2026-10-10 UTC；普通web搜索均未加日期过滤。实际获得的历史材料范围：易语言2000年至2026年当日官网，Tiecode生态2022年至2026年公开资料；Sheng辅助材料2021年版本页。这里是实际检索记录，覆盖面与遗漏风险见下节。

### 普通web搜索

- 结绳 中文编程 官方 文档 作者
- site:eyuyan.com 易语言 吴涛 2000 5.93
- site:eyuyan.com "版本 2" "子程序"
- "结绳" "tiecode" "文档"
- "tiecode" "github"
- "易语言" "吴涛" "2000年9月11日"
- site:eyuyan.com "计次循环首"
- tiecode 文档 官网
- tiecode github TieLang
- site:eyuyan.com "吴涛"
- site:eyuyan.com "2000年"
- "tiecode.cn" 文档
- "tiecode" "TieLang" 中文 github
- "结绳" "Scave"
- site:eyuyan.com "2000" "9" "16"
- site:eyuyan.com "5.95" "更新"
- "TiecodeCompiler-Public" Scave
- "结绳" "Scave" 作者
- site:eyuyan.com/help ".版本 2"
- site:eyuyan.com "2000年9月16日"
- site:eyuyan.com "2000年初"
- site:eyuyan.com "全编译" "VC"
- "吴涛" "易语言即学即用" "序"
- "易语言1.0" "9月16日"
- "易语言" "2000" site:eyuyan.com/intro
- "结绳" "2019" "Scave"
- "结绳" "郭永江" 开发
- "结绳" "Scave" "2018"
- "结绳" "2017" 编程
- "结绳" "TieLang" 作者
- "易语言" "计次循环首" site:github.com README
- "易语言" ".版本 2" "你好" site:github.com
- "sheng" "luojiahai"
- "The Sheng Programming Language"

### GitHub接口

- 仓库检索：tiecode；user:mobile-ipe；sheng Chinese programming language。
- 直接读取仓库元数据、README、完整递归tree、公开releases、固定提交文件与Issue全部评论。
- Sheng直接读取使用PyPI页面实际给出的精确仓库链接。
- 无时间过滤。源码层静态核验限于本日志列出的文件。

### 公开网页

- 易语言：公司介绍、官方历史报道目录、新闻原图、教程原图及下载页。
- Tiecode：官网错误页；Gitee Scave与MobileIPE公开仓库、组织页、旧README；Maven Central POM和两页Versions；插件商店。
- Sheng：PyPI 0.1.18作者发布页与Homepage链接。
- Gitee登录页面保留为访问边界；原图以标准媒体下载保存。

## 五、遗漏风险与下一步证据要求

1. 易语言原始发行包、原版作者书序与早期站点归档可能补出1.0首发日；目前仅有官网保存的1.1公开报道可直接复核。
2. 易语言代码主要呈现为可视化表格和图像；官方原始.e文件或官方文本导出实例可补齐源文件级复核。
3. 结绳资料分散于官网、Gitee、GitHub、Maven及公开群归档；登录可见内容、历史群文件和失效域名存在遗漏风险。首个公开版本仍需作者原始公告或最早发行记录。
4. Tiecode当前公开仓库主要提供产物、API和文档；内部实现、旧Java入口与新C++集成体系之间的演进，需要对应版本原始源码或作者技术说明。
5. GitHub最新观察提交及当前官网版本仅说明本次可访问材料；其他发行渠道、闭源开发进度和长期维护计划待核实。
6. Sheng的原仓库当前返回404，PyPI发布页保留来源链与语法；同名语言的项目归属按独立作者来源链记录。
7. 所有代码示例和构建流程均属静态证据；运行、兼容性、性能及安全性另行核验。

