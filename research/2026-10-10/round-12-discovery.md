# 第十二轮：低关注B站项目与旧社区标题入口发现

核验日期：2026-10-10；本支研究时段20:01—20:11 UTC。百科基线为[yuyan-lang/chinese-programming-languages@9776f45bed00a6f1c9a594eb8142dd5b4428095d](https://github.com/yuyan-lang/chinese-programming-languages/tree/9776f45bed00a6f1c9a594eb8142dd5b4428095d)，语言目录73项、开放Issue20项。

## 结果先览

深入范围合计2组：

1. hscript-c（中英双语关键字）：本轮真正新发现1组。由620播放的B站原片接到C++原仓，取得完整中文原例、固定解释链和明确AI协助提交。建议正式新增1项。
2. 可执行考鼎码（EC2）：第十一轮只有名字级社区背景，本轮首次深入1组。取得原作者独立规范、8行完整原例、洛书派生C解释器与WASM接口。建议正式新增1项。

本轮建议正式新增2项，既有正式条目补写0项，新待核候选0组，新增建议条目的待补字段2组。EC2计入旧标题背景首次深入。白易、壬通、云易、飞鱼、如意、唐姝等既有对象深入增量为0。极语言仅保留搜索背景，深入增量为0。

采用公开网页、GitHub固定来源与公开视频观察进行静态核验。程序运行与完整兼容性待独立核实。

## 开轮排重

已读取基线根AGENTS.md全文、完整递归目录、73项语言名称与参考源索引；对完整languages.json全部字段进行名称、别名、UID、BV与源码仓库URL检索。复核第十一轮B站、社区与PyCn日志；第十轮B站“自制脚本解释器”关键词记录作为历史检索范围背景。

20个开放Issue为#1、#3、#4、#5、#11、#13、#16、#18、#19、#22、#23、#24、#26、#27、#29、#31、#32、#33、#35、#36。排重语料使用20项完整正文和第十一轮社区审计文件内既有Issue评论。关键词“考鼎、ec2playground、hscript、533393738、BV11mNA6vE93”在73项正式目录、20项正文及既有评论审计中均命中0项。第十一轮社区日志第148行单列“极语言、考鼎码”作为未深入入口，EC2沿用旧背景口径。开轮已核全部53条Issue评论。

## 一、hscript-c：真正新发现的中英双语嵌入式脚本

### 原BV、作者与发布时间

原片：[自制脚本解释器，支持中文关键字和继承C++类！](https://www.bilibili.com/video/BV11mNA6vE93/)

发布者：[醪崑，UID533393738](https://space.bilibili.com/533393738/)。原片简介直接给出https://github.com/zxk-creator/hscript-C-。2026-10-10公开页面显示620播放、账号关注按钮计数535。以上为本次观测值。

DOM metadata：
- video:release_date = 2026-07-11T13:24:37.000Z。
- video:duration = 153秒，02:33。
- author = 醪崑。

页面初始时间为2026-07-11 21:24:37；客户端加载后时间显示06:24:37。UTC日期采用明确metadata。视频投稿时间与仓库创建、Git时间分别保存。

公开播放器画面640×360。在约01:03观察到编辑器中的中文类、构造函数和方法代码；截图前DOM video.currentTime为62.614239。较早一幅画面显示中文类型注解及动态类型字幕，该幅独立精确时间待核。原视频的逐字源代码采用下面的固定原文件补证。

原例的逐字转录以固定源码为依据。

### 固定源码、中文原例和实现链

原仓元数据：fork=false、archived=false，created_at=2026-07-08T11:29:58Z，pushed_at=2026-07-11T12:39:21Z。固定main头为[f4502da497b9abc0b280d1b1e3e01239000b7ded](https://github.com/zxk-creator/hscript-C-/tree/f4502da497b9abc0b280d1b1e3e01239000b7ded)，提交时间2026-07-11T12:38:25Z，树32项、truncated=false。当前元数据star=0、fork=0，数字按本次响应保存。

完整连续中文原例是[test/TestScriptChinese.hx第1—22行](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/test/TestScriptChinese.hx#L1-L22)，Git blob SHA182a5b7f07289014929628288c41cf60abc0a5fd。原文件全文获取与独立按行获取逐字相等。交付JSON保留22行完整类和实例调用，包含“类、公开、变量、函数、新的、自己”等实际语法。trace与Int／Float／String保持原例英文形式。

实现证据：
1. [Scanner第52—64行](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/token/Scanner.h#L52-L64)以高位字节条件接纳UTF-8名称；[第167—175行](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/token/Scanner.h#L167-L175)完整名称查表并形成词元。
2. [第179—255行](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/token/Scanner.h#L179-L255)含25项汉字映射，与英文写法共用ETokenType。映射表存在与对应运行语义分开记录。
3. [Parser第273—341行](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/ast/Parser.h#L273-L341)分派类、函数与变量，构造ClassStmt及字段／方法。第431行以后进入条件、循环和返回分派。
4. [Parser第344—427行](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/ast/Parser.h#L344-L427)消费注解、访问修饰符与类型注解后忽略。文档列出的修饰词按可解析语法保存，访问控制或类型检查能力另列待核。
5. [main.cpp第43—71行](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/main.cpp#L43-L71)串起Scanner、Parser、trace／now／TestClass原生注册及Interpreter::interpret。
6. [Interpreter第354—396行](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/ast/Interpreter.h#L354-L396)解析已注册C++父类，建立HClass；[第511—565行](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/ast/Interpreter.h#L511-L565)把自己解析为this，并分别查new及新的构造函数。
7. [Reflect.h](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/util/reflect/Reflect.h)通过显式名称分支构造TestClass；[test/TestClass.h](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/test/TestClass.h)注册原生c方法和字段访问器。[HClass.h](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/type/HClass.h)负责脚本方法、原生方法及父类链查询。

分类为“Haxe风格嵌入式脚本语言／中英双语词元前端与C++ AST解释器”。独立源码执行路径已读。Haxe完整兼容性、HaxeFoundation/hscript上游代码关系、数组字面量、符号&&／||和字符串转义覆盖、原生多实例状态及运行结果待核实。

### Git历史、版本许可与AI

默认分支六条提交均可追至空parents根：
- 2026-07-08T11:50:08Z，f2eb253178c8d343b8b85c2ff949783968717e61，第一次提交。
- 2026-07-08T18:33:32Z，[7c143b3aec56750233b29faf2df6dcc598393bfd](https://github.com/zxk-creator/hscript-C-/commit/7c143b3aec56750233b29faf2df6dcc598393bfd)，原始消息：“第二次提交。在AI帮助下实现了脚本类定义和实例化。”该差异保存类、实例、解析和解释扩展。AI范围按该原始声明保存；工具、模型及比例待核实。
- 2026-07-09T18:38:09Z，151f9ed18a978976e33f8e05ff1166fdca44742f，原生C++类继承。
- 2026-07-10T10:30:47Z，892463a131ef865bec115c96e829b33f8838dc64，运行时类型相关修复。
- 2026-07-10T11:11:14Z，[107dfbeff38dda1aac8bf120e1f5782bfca0c06b](https://github.com/zxk-creator/hscript-C-/commit/107dfbeff38dda1aac8bf120e1f5782bfca0c06b)，中文支持提交：Scanner增加高位字节分支，Interpreter加入转字符串和新的构造函数查找，并添加中文脚本。此前词表已有部分中文名字，中文执行支持按此准确变化保存。
- 2026-07-11T12:38:25Z，f4502da497b9abc0b280d1b1e3e01239000b7ded，更新README和测试；署名kkplay，GitHub关联zxk-creator。

[CMakeLists.txt](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/CMakeLists.txt)声明CMake3.20、C++20、项目名HaxeParser。Releases与git/matching-refs/tags均返回空数组。初次普通/tags API地址被连接器判定为不支持端点，git/refs/tags返回404；随后matching-refs准确确认标签集合为空。独立版本号及发行附件待核实。

[LICENSE](https://github.com/zxk-creator/hscript-C-/blob/f4502da497b9abc0b280d1b1e3e01239000b7ded/LICENSE)是Apache-2.0全文，README及元数据同标。附录Copyright保留模板占位，具体版权持有人署名及第三方继承范围继续核实。

## 二、可执行考鼎码：旧标题背景首次深入

### 独立规范和原作者链

固定[官方页面index.html](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/index.html)介绍：语言由魏永明设计，于2024年12月提出；用途为少儿信息学启蒙。页面链接GitHub VincentWei/ec2playground、Gitee vincentwei7/ec2playground和作者课程规范。

[固定README](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/README.md)列CHEN Chaochen、CHENG Tianyu、HUANG Dongqiao为洛书团队开发者，WEI Yongming负责前后端。官方课程仓README直接声明作者魏永明／VincentWei。

[独立语言规范](https://github.com/VincentWei/PLZS/blob/badd2e1b94807f11f77f4f5d5f555a86cbf42848/slides/enlightenment-spec-of-executable-coding-code.md)固定于PLZS提交badd2e1b94807f11f77f4f5d5f555a86cbf42848，日期2025-02-17T13:03:00Z，共550行。规范包括程序入口、关键词、类型、运算符、容器、系统接口和解释器要求。代码名称与语法规定以该原始文档为依据。

分类采用“算法教学领域专用语言／洛书派生的C语言与WASM解释实现”。独立规范及专用算法入口支持单列教学语言，洛书内核关系明确注明；考鼎伪代码、EC2和在线练习场按不同资料层次整理。

### 连续中文原例与固定实现

固定练习场头为[2b2d11a06e823c828c81c86ac0dd00d910287b24](https://github.com/VincentWei/ec2playground/tree/2b2d11a06e823c828c81c86ac0dd00d910287b24)，master，2025-03-03T04:22:04Z，完整树489项且truncated=false。

[demo/基本语句/函数.ec2第1—8行](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/demo/基本语句/函数.ec2#L1-L8)全文：

```text
算始 函数测试()
    返回 函数1()
算终
函始 函数1()
    执行("拍手")
    执行("说出","你好考鼎码")
    返回 1
函终
```

Git blob为6820abd514579e61d92082ad36fcab7129564232。全文与独立按行获取逐字相等。该例同时展示算法入口和普通函数。执行系统功能为函数调用；算法／函数／返回词均有实际词元及解析分派。

源码链：
1. [ec2_sytax.c第350—398行](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/ec2_wasm/ec2/ec2_sytax.c#L350-L398)保存并初始化中文词表。
2. [第1325—1380行](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/ec2_wasm/ec2/ec2_sytax.c#L1325-L1380)分派若始、当始、函始、算始、全局和返回。算法分支检查单一入口并设置isMain。函数体解析生成指令。
3. [ec2_api.c第169—202行](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/ec2_wasm/ec2/ec2_api.c#L169-L202)提供vm_dostring→vm_loadstring→vm_execute；[VM第109—140行](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/ec2_wasm/ec2/ec2_vm.c#L109-L140)区分原生函数与字节码执行，第617行起可见RETURN、CALL等指令分派。
4. [wasmIOrunCode](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/ec2_wasm/wasm/ec2_wasm_main.c#L16-L81)建立VM、初始化库、读取编辑器源码，再获取算法参数、调用入口和显示结果／统计。
5. [核心库第518—618行](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/ec2_wasm/wasm/ec2_wasm_libcore.c#L518-L618)实现拍手／说出桥接，并将输出、输入、执行、终止、整数等中文名注册为原生函数。
6. [sh/build.sh](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/sh/build.sh)静态配置emcc、WASM、ASYNCIFY、运行和中断导出。构建脚本保持文本阅读。

### 规范与实现边界

- [固定词法器第1063—1072行](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/ec2_wasm/ec2/ec2_sytax.c#L1063-L1072)对声明／导入／定义词元跳过至换行。规范为相关词定义了语义；实现覆盖按此实际分支记录。
- demo/基本语句/循环.ec2用“定义 甲 = 0”；该行属于上述跳过路径。demo/基本语句/判断.ec2使用“若又”，固定词表使用“若另”。这些旧示例的修订对应与运行结果继续待核。
- samples/U2-算法的概念/L8P1-自然数阶乘.ec2包含裸“终止”；规范解释终止为函数。该样例沿革及调用行为另待核。
- 规范第535—549行规定循环／调用限制、统计、交互与双语配置。VM第624—629行有注释形式的限制逻辑，限制生效范围继续核实。
- 数值／容器扩展、保留关键词、英文关键词配置以及所有内置函数按规范与实际源码分别记录。源码词表存在保持为静态证据，运行与完整兼容待核实。

### 时间、版本与许可

官方提出时间为2024年12月。GitHub created_at=2024-12-26T06:57:59Z，pushed_at=2025-03-03T04:23:29Z。默认历史[根提交48235f0f…](https://github.com/VincentWei/ec2playground/commit/48235f0f88d7b5c5f233b32a68f9f690437f025a)为2024-12-25T03:50:37Z、parents=[]、根树100项，包含解释器和.ec2原例。Git日期早于GitHub仓库创建，二者属于不同来源字段；首次公开时间继续待核实。

历史检索读取前三页共300条后，采用until=2024-12-27的定向查询取得10条早期提交及根。该记录可确认根资料，完整中间提交数量与所有分支历史待核实。当前head合并消息为“add bytes type-patch1”。GitHub Releases与git/matching-refs/tags均返回空数组；正式语义版本与线上部署快照待核。早前git/refs/tags返回404，后续matching-refs响应补齐准确空集合证据。

项目README标AGPL第3版或后续版本、Copyright 2024, 2025 EC2 Community；[COPYING](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/COPYING)全文为AGPLv3。[核心头注](https://github.com/VincentWei/ec2playground/blob/2b2d11a06e823c828c81c86ac0dd00d910287b24/ec2_wasm/ec2/ec2_sytax.c#L1-L45)为洛书MIT许可，chen-chaochen署名。CodeMirror与课程规范各自许可范围另待核实。

AI开发参与：原作者明确工具、使用范围和比例待核实。课程介绍涉及开源AI大模型，按课程主题记录。

## 三、实际检索、平台与时间窗

优先2024—2026年低关注、微型、AI相关与视频公开项目。所有搜索均未使用强制日期筛选，按原始资料日期人工核验；最早确认源码延伸到2024-12-25，最晚目标视频为2026-07-11。

普通网页21个实际查询：
1. site:bilibili.com/video "手搓编译器" "中文"
2. site:bilibili.com/video "全中文代码" 2025
3. "极语言" "考鼎码"
4. 中文编程 "极语言"
5. "考鼎码"
6. site:bilibili.com "手搓" "中文" "编译器"
7. site:bilibili.com "AI写" "编译器" 中文
8. "中文解释器" site:bilibili.com/video
9. "自制脚本" "中文" site:bilibili.com/video
10. "手搓编译器" site:bilibili.com/video
11. "极语言" 官网
12. "自制脚本解释器，支持中文关键字和继承"
13. "醪崑" "解释器"
14. "考鼎码" 编程 官网
15. "极语言" "SEC"
16. "可执行考鼎码" 规范
17. "醪崑" "脚本"
18. site:bilibili.com/video "AI写编译器"
19. "考鼎码" "规范" "算始"
20. "hscript-C-" "zxk-creator"
21. "AI写编译器" "中文"

公开网页浏览器B站综合第一页检索3组：中文解释器、自制脚本解释器、中文关键字 继承。第三组定位BV11mNA6vE93并读取原片。作者投稿全集及搜索翻页留待下一轮有目标时扩展。

GitHub读取百科AGENTS、项目固定树／README／源码／许可证／commits／refs／releases。专门代码搜索query=可执行考鼎码、repository=VincentWei/PLZS，取得官方规范准确文件及固定SHA。EC2设计规范的官方课程网页和练习场普通open返回不可访问结果；GitHub原始来源可读，研究转原仓固定文本。

## 四、访问风险与遗漏风险

1. 精确中文短词召回经常被自然语言教学、游戏代码、一般脚本工具和广告主导。B站词组“中文关键字 继承”有效定位原片，泛化“自制脚本解释器”第一页主要为无关对象。
2. 普通搜索引擎对醪崑及原视频题名召回弱，存在低关注视频未索引风险。B站综合结果仅三次第一页检索，搜索排名并非完整覆盖。
3. 普通网页关键词返回极语言原片、镜像仓和SEC第三方教程；本轮深度预算集中于hscript和EC2，该组仅作背景保留。
4. 公开视频360P和时间控件可见性影响逐帧转录；两次目标时间操作未确认后转静态源码。原片时间展示存在客户端时区差异，采用UTC metadata。
5. 源码、说明书、测试原例、作者视频与运行实测是独立证据层级。当前工作确认可读实现链及原例存在，完整运行与性能数字继续待核。
6. EC2旧demo与较新规范用词存在阶段差异；语言新旧版本、教学伪代码与可执行程序须保持区分。独立规范和实际解释器按各固定SHA记录。
7. hscript提交明确AI辅助的有限功能范围；项目其余文件、后续中文扩展及任何比例继续待原作者资料。EC2课程AI主题保持课程层级。
8. 现存Git根、仓库创建与公开首发时间分别保留；镜像导入、历史改写、私有资料以及仓外发行都可能留下时间缺口。

## 五、计数汇总

- 真正全新发现：1组，hscript-c。
- 旧标题背景首次深入：1组，可执行考鼎码。
- 本轮深入合计：2组。
- 正式语言新增：2项，lang-075和lang-076。
- 新待核候选：0组。
- 建议条目待补字段：2组。
- 已有正式条目补写：0项。
