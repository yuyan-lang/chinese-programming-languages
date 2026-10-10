# 第七轮：Issue #3 的 zwpy、智语言与 PYCH

核验日期：2026-10-10（UTC）。核验时段：17:31—17:37 UTC。

## 范围、结果与计数

本轮聚焦原 Issue #3 的3组线索：52zwbc/zw、cnzkai/Zlang、qingsububao/PYCH-Language。

- 建议新增2项：zwpy（zw），按Python中文语法映射方案及公开文档原例记录；智语言（cnzkai），按公开语言规范与验收例程记录。
- PYCH继续待核实，新增8项发行、9个标签及Python源码附件的资产ID、SHA256证据。
- 外围新增关联线索1组：52zwbc的python313zw／python314zw。该组的内部沿革、与zwpy的对应和最终条目分组待核实。
- zw与zwpy依据明确别名和完全相同README blob归为同一项目入口。
- 华夏编程lang-054与zwpy的关系保留待核实。
- 若本轮2项采纳，Issue #3原19组中完成分类收录的线索由6组增至8组，余11组继续核实。

研究采用GitHub只读接口、普通公开网页检索及公开云浏览器。项目执行、安装、构建和测试结果均为待核实。

## 基线与防重

基线提交：[697f78bd2d10a85a0c0c8cce9444bf03bdbf415a](https://github.com/yuyan-lang/chinese-programming-languages/tree/697f78bd2d10a85a0c0c8cce9444bf03bdbf415a)。

先读取的材料：

1. 根[AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/697f78bd2d10a85a0c0c8cce9444bf03bdbf415a/AGENTS.md)，blob ab8038fa86c6ff04320372eea00cee9c5fd54cca，采用直接肯定陈述及“待核实”状态。
2. [data/languages.json](https://github.com/yuyan-lang/chinese-programming-languages/blob/697f78bd2d10a85a0c0c8cce9444bf03bdbf415a/data/languages.json)，55项，核对名称、别名和来源仓库。
3. [Issue #3正文与3条评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/3)。最近进度为第六轮新增道及CNSH，原19组完成6组。
4. [round-6.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/697f78bd2d10a85a0c0c8cce9444bf03bdbf415a/research/2026-10-10/round-6.md)、[round-6-gitee.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/697f78bd2d10a85a0c0c8cce9444bf03bdbf415a/research/2026-10-10/round-6-gitee.md)与[round-6-bilibili.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/697f78bd2d10a85a0c0c8cce9444bf03bdbf415a/research/2026-10-10/round-6-bilibili.md)。

三项均为既有候选。zwpy的中文Python名称采用52中文编程作者链限定；智语言采用cnzkai限定。华夏编程的原作者UID、.hx后缀、Zwbc安装目录与本轮资料逐项对照。

## zwpy（zw）：固定文档、同源入口与关系边界

### 日期和作者

- [仓库元数据](https://api.github.com/repos/52zwbc/zw)给出创建时间2026-05-27T10:34:47Z，fork=false，主页为https://www.52zwbc.com/。
- 默认分支4次提交。根提交[5189f7f36209f1533b6f5567be119a27fe2be063](https://github.com/52zwbc/zw/commit/5189f7f36209f1533b6f5567be119a27fe2be063)的parents为空，日期2026-05-27T10:35:50Z；提交署名glsnh、GitHub作者对象52zwbc。根README有“zw”标题与中文编程语言介绍。
- [b7283ad2b4b6eeb30ef9981673f2d83a1857b8e0](https://github.com/52zwbc/zw/commit/b7283ad2b4b6eeb30ef9981673f2d83a1857b8e0)在2026-09-10T13:35:05Z将说明同步为zwpy介绍。
- 当前固定zw提交36e929a0d4e868a8700f5ec5e7563b541c9518d4，时间2026-09-10T13:57:25Z。
- 官网固定页署名“zw语言项目（52中文编程）”。实名及其他平台账号关系待核实。

### 原例与公开实现层级

- [README第353—359行](https://github.com/52zwbc/zw/blob/36e929a0d4e868a8700f5ec5e7563b541c9518d4/README.md#L353-L359)为完整求平方根函数及调用，含函数、如果、抛出、返回、打印。
- [第90—134行](https://github.com/52zwbc/zw/blob/36e929a0d4e868a8700f5ec5e7563b541c9518d4/README.md#L90-L134)列出中文关键字映射。随后为内置函数、异常、类型方法映射。
- [第76—81行](https://github.com/52zwbc/zw/blob/36e929a0d4e868a8700f5ec5e7563b541c9518d4/README.md#L76-L81)描述.zw运行入口与Python中文内置名注册，按作者说明记录。
- [官网固定源页第203—239行](https://github.com/52zwbc/52zwbc.github.io/blob/c8deec64414b6bde6c56a3bb6e1f968895f4e4e0/index.html#L203-L239)介绍VSCode插件转为标准Python、运行、中英转换、AI错误解释与PyInstaller打包。
- zw当前树2项，README.md与微信赞赏.jpg；zwpy当前树同样2项，均truncated=false。转换器、插件和发行运行时正文待核实。
- 文档第44行首个遍历原例使用“在”，第121行映射使用“属于”；第88行的标点约定与ASCII括号例程共存。具体适用规则待核实，精确条目代码采用另一个连续原例。
- 此次重新按行提取第353—359行，结果与全文分行比对一致。

### zw／zwpy、官网与版本

- 同账号[zwpy仓库](https://github.com/52zwbc/zwpy)创建于2026-09-10T13:28:41Z。
- 固定zwpy提交74e561072b928abcfc688c3225ba6b860441c619与zw的README共享blob SHA 04a763bf1cd19daea2ff17cf55a41b91e4b5afa2，全文一致；赞赏图片也共享blob。
- README明确zwpy简称zw；官网明确zwpython英文名，构成一项的同源入口证据。
- [官网仓库](https://github.com/52zwbc/52zwbc.github.io)固定c8deec64414b6bde6c56a3bb6e1f968895f4e4e0，提交时间2026-09-10T13:51:19Z。首页元数据与页面均使用zwpy、zwpython、52中文编程。
- [官网第281—297行](https://github.com/52zwbc/52zwbc.github.io/blob/c8deec64414b6bde6c56a3bb6e1f968895f4e4e0/index.html#L281-L297)提供zwpy2_2.exe、zwpy313_2_win7.exe及编辑器下载链接，安装路径C:\\zw。
- 两个文档仓库Release列表为空，标签命名空间返回404。安装文件名采用原样记录；稳定版本和下载包内容待核实。

### 华夏编程近名对照

华夏编程现有条目采用[BV1Gtpg65EfU安装教程](https://www.bilibili.com/video/BV1Gtpg65EfU/)及同UID3493272276175446材料，给出.hx、输出语句和C:\\Program Files\\Zwbc目录。zwpy采用52zwbc仓库、52中文编程官网、.zw及C:\\zw目录。普通网页双名检索和三个文档仓库的“华夏”搜索结果提供的关联证据有限。两套作者身份、产品沿革及代码关系待核实，维持各自原始来源链。

## 智语言（cnzkai）：开发者指南与验收例程

### 固定身份、日期及原例

- [仓库元数据](https://api.github.com/repos/cnzkai/Zlang)创建时间2026-04-09T16:03:27Z，fork=false。
- 默认分支3次提交，根提交[39023dfd3acc362ed2b49859a37b102110226b9a](https://github.com/cnzkai/Zlang/commit/39023dfd3acc362ed2b49859a37b102110226b9a)的parents为空，时间2026-04-15T06:48:53Z；作者名Kaiser对应cnzkai。
- 当前固定[8049eae6d22c10cbc764f8b253f561cd6ce7d378](https://github.com/cnzkai/Zlang/tree/8049eae6d22c10cbc764f8b253f561cd6ce7d378)，提交时间2026-04-15T06:52:41Z。
- 递归树3项：README.md、test目录、test/text.z；truncated=false。
- [test/text.z第544—552行](https://github.com/cnzkai/Zlang/blob/8049eae6d22c10cbc764f8b253f561cd6ce7d378/test/text.z#L544-L552)连续给出斐波那契与阶乘两个完整函数，展示如果与返回。全文读取后按行再取回，逐字一致。
- 原例文件以输出实际值和期望值表达验收；执行成绩待核实。

### 规范与实现状态

- [README第164—245行](https://github.com/cnzkai/Zlang/blob/8049eae6d22c10cbc764f8b253f561cd6ce7d378/README.md#L164-L245)描述条件、计次循环、条件循环、跳出与跳过。
- [第249—301行](https://github.com/cnzkai/Zlang/blob/8049eae6d22c10cbc764f8b253f561cd6ce7d378/README.md#L249-L301)描述函数、递归及主函数。第253行提到“函数”关键字，例程直接使用函数名声明；适用规则待核实。
- [第562—604行](https://github.com/cnzkai/Zlang/blob/8049eae6d22c10cbc764f8b253f561cd6ce7d378/README.md#L562-L604)给出模块与公开成员语法。
- [第645—667行](https://github.com/cnzkai/Zlang/blob/8049eae6d22c10cbc764f8b253f561cd6ce7d378/README.md#L645-L667)描述zlc0目录、build.bat、zlc0.exe与验收命令。
- 仓库简介自述编译器自举。编译器正文、引导链、构建脚本、可执行发行和自举验证待核实。
- test/text.z导入a_module；配套模块与完整验收工程待核实。
- Release列表为空；标签命名空间404；当前分支列表只有main。zlc0按目录和工具名记录，版本号待核实。
- GitHub“智语言”查询还返回flythnker/quzsc-zhi-lang-core及无关笔记项目。此次按作者限定名称收录，其他同名项目关系留待明确来源。该搜索命中仅作同名风险记录。

## PYCH：发行资产补证与原例缺口

### 已取得证据

- [仓库元数据](https://api.github.com/repos/qingsububao/PYCH-Language)创建于2026-07-16T16:27:38Z，fork=false。
- 唯一main提交[de4737e7df3fa0958617fa181745c270af73954b](https://github.com/qingsububao/PYCH-Language/commit/de4737e7df3fa0958617fa181745c270af73954b)日期2026-07-16T16:32:39Z，parents为空，作者qingsububao。
- [固定README](https://github.com/qingsububao/PYCH-Language/blob/de4737e7df3fa0958617fa181745c270af73954b/README.md#L1-L2)共2行，介绍Python宿主、.pych后缀、交互与脚本模式。递归树1项、truncated=false。
- [发行列表](https://github.com/qingsububao/PYCH-Language/releases)取得8项：pych0、pych1.0、pych2.0、pych3.0、pych3.1、pych3.2、pych4.0、4.1.a。
- pych0发布2026-07-16T16:59:35Z；pych1.0发布2026-07-16T17:19:29Z；pych4.0发布2026-07-16T17:54:24Z；4.1.a发布2026-07-17T07:04:11Z。完整日期保存在待核实数组。
- [标签列表](https://api.github.com/repos/qingsububao/PYCH-Language/git/refs/tags)有9项，还包含pych4.1；全部指向同一README提交。各发行的实际解释器内容应按附件资产标识。
- [pych4.0 main.py元数据](https://api.github.com/repos/qingsububao/PYCH-Language/releases/assets/479462953)：资产ID479462953，15508字节，SHA256为7169b20e365e86456fff8a627b2f33f7d79a12a392b02de3c7c8170cf8306e9a。
- [4.1.a](https://github.com/qingsububao/PYCH-Language/releases/tag/4.1.a)标题标注试验工程，说明计划增加“如果、当时、重复、对于”；附main.1.py和main.py，两项资产摘要保存在待核实数组。
- pych0资产为FileCompilerAndInterpreterForPYCH.py；pych1.0／2.0为五个.py文件；pych3.x起为单文件main.py。按发行附件形态记录，内部语义待核实。

### 访问和下一步

只读接口访问附件下载URL返回404；普通网页读取返回缓存未命中。公开云浏览器成功打开pych4.0发行页，核到发行文字、作者、附件名和SHA256。点击main.py附件时返回浏览器URL协议安全限制，附件访问在该处停止。

额外核查了公开Issues与Discussions：Issues结果为空，Discussions显示初始欢迎界面。当前固定仓库树的资料为README。原始连续中文程序、附件源码正文、图片例程、关键词和执行路径继续待核实。

下一步需要安全可读的官方附件文本或作者公开文本镜像，并按资产SHA256核对版本。拿到原例与实现入口后再确定条目类别。

## 外围关联候选：52zwbc中文CPython仓库组

本段作为后续入口记录，最终分组及与zwpy关系待核实。

- [python313zw固定提交84fee06c5dd87bc5547d7c715a1e760dc107c720](https://github.com/52zwbc/python313zw/tree/84fee06c5dd87bc5547d7c715a1e760dc107c720)，时间2026-10-09T10:59:36Z；建库时间2026-10-07T00:58:15Z。树5495项、truncated=false。
- 其README.rst自标Python3.13.16；[Lib/_zh_builtins.py](https://github.com/52zwbc/python313zw/blob/84fee06c5dd87bc5547d7c715a1e760dc107c720/Lib/_zh_builtins.py)含中文内置包装、默认utf-8和启动加载说明。
- [python314zw固定提交a14d42425a5f9c845555783e4ed1cadad7b7df43](https://github.com/52zwbc/python314zw/tree/a14d42425a5f9c845555783e4ed1cadad7b7df43)，时间2026-10-06T23:26:30Z；建库时间2026-10-05T12:46:59Z。树5787项、truncated=false。
- 其README.rst自标Python3.14.8；[test_zh.py第1—24行](https://github.com/52zwbc/python314zw/blob/a14d42425a5f9c845555783e4ed1cadad7b7df43/test_zh.py#L1-L24)有打印、如果及中英混用代码。
- 两仓GitHub元数据fork=false；该字段按GitHub仓库形态记录。上游代码来源及派生关系需另行对照。
- 同账号和官网zwpy313文件名提供关联线索。统一产品声明、插件／运行时关联、共同提交、发行附件映射及中文语法一致性继续核实。两个库暂存一组关联线索，条目分组待核实。

## 平台、实际关键词与查询范围

平台：GitHub公开仓库与REST只读资料、普通网页搜索、官网静态源页、GitHub公开发行及讨论页。核心沿革范围为2026年4—10月，查询采用全时段。

普通网页查询：
- "52zwbc" "zwpy"
- "52zwbc" "华夏"
- "cnzkai" "Zlang"
- "qingsububao" "PYCH"
- "52中文编程" "华夏编程"
- "zwpy" "华夏"
- "sdglsdwx" 编程
- "cnzkai" "智语言"

首批精确查询返回空结果；双名扩展出现泛化的华夏／中文词义等无关结果，采信材料均回到原作者资料。

GitHub查询：
- user:52zwbc：返回8个公开仓库，发现zwpy、官网、两个中文CPython仓库及其他工具仓库。
- Zlang user:cnzkai：返回cnzkai/Zlang。
- "智语言"：返回cnzkai/Zlang、另一个同名项目和无关笔记。
- "华夏编程"：返回空数组。
- 在52zwbc/zw、52zwbc/zwpy、52zwbc/52zwbc.github.io中搜索“华夏”：返回空数组。
- 三个目标的递归树、分支、提交、发行、标签；PYCH与智语言的公开Issue列表。

首次普通网页打开目标百科仓库返回缓存未命中，GitHub只读接口可读；官网普通网页抓取失败后读取其原作者GitHub Pages固定index.html。

## 资料风险与后续方向

- 文档宣传、语法规范、实现源码、发行附件元数据与独立运行各自采用相应证据层级。
- GitHub标签可能只指向说明文档；PYCH解释器保存在额外上传的Release附件，需保存资产摘要。
- 文件名中的版本样式、编译器工具名和语言稳定版本分别记录。
- 相同作者账号与近名目录提供关系线索；同源分类优先采用明确别名、互链、共享内容和提交沿革。
- 同名智语言／ZLang、中文Python系列采用作者及仓库限定，避免名称歧义。
- 后续优先补PYCH公开源码文本、zwpy插件与运行时对应、智语言编译器及模块依赖；外围CPython组待作者关系和源码差异核验后再决定归档方式。

