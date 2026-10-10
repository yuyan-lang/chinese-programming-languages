# 第十四轮发现：历史原作者资料与脑语言平台分层

核验日期：2026-10-10；研究窗口21:01—21:08 UTC。基线为[yuyan-lang/chinese-programming-languages@46734fc65a9a5da4cdc230c78c9f835134973e9a](https://github.com/yuyan-lang/chinese-programming-languages/tree/46734fc65a9a5da4cdc230c78c9f835134973e9a)，77项语言、8项内核。

## 结果与计数

深入范围为2组：

1. 文言Perl／中書珨：Issue #5已经提到的历史旧线索。本轮补齐固定原例、源过滤转换链、原作者、2002年起的技术版本记录和CC0声明，建议转正式1项。
2. 脑语言：本轮真正新发现1组。2022年原创单字词表接到2025年原仓编辑器及2026年dshjs平台。固定实现支持单字代码输入与中文函数别名，中文语法连续原作程序继续待核，保留新候选1组。

本组正式新增建议1项，真正新发现正式收录0项；旧线索转正式1项，新待核候选1组，正式对象待补字段1组。脑语言关联的naoyuyan仓、dshjs平台与旧名按同一研究组分层，独立新语言数保持1组候选口径。

核验范围为公开网页、GitHub原始资料与源码静态阅读。独立运行结果待核实。

## 开轮排重

已读取固定AGENTS.md、完整递归树、data/languages.json全部字段、第十三轮发现日志。GitHub开放Issue集合23项，编号为1、3、4、5、11、13、16、18、19、22、23、24、26、27、29、31、32、33、35、36、38、40、41。全仓评论接口返回72条；按23项开放Issue的issue_url过滤为60条相关评论，其余12条属于其他议题／PR语料。开放Issue列表中的PR数量为0。

对77项全字段、23项正文、60条相关评论及历轮研究日志检索：

- 文言Perl命中Issue #5正文历史目录，正式目录匹配0项；PerlYuYan与中書珨属于本轮补出的原模块名和原作中文名。
- 脑语言、naoyuyan、2500ai、dshjs及腾讯云文章2045815在基线目录、Issues及相关评论匹配0项；历轮研究日志匹配0项。
- 衍真／nextOS/yzcc命中Issue #3、其第六轮补证评论及round-6-gitee日志，按既有候选处理。
- 历史Klang由program-in-chinese/overview指向HTWX/klang_dlang；搜索同名股票K浪指向asmcos/Klang，按不同原仓区分。
- CNlua的GitHub检索返回xgongya/cnLua。本轮保留发现背景，深入资源集中于上述2组。第十三轮lyzavng/lua维持已有待核状态。

## 一、文言Perl／中書珨：旧线索转正式

### 原作者与固定证据

原仓：[audreyt/lingua-sinica-perlyuyan](https://github.com/audreyt/lingua-sinica-perlyuyan)。固定master头：[08b4d8294876903ed7ff193fa3a08f247d66b637](https://github.com/audreyt/lingua-sinica-perlyuyan/tree/08b4d8294876903ed7ff193fa3a08f247d66b637)。完整树12项，truncated=false。仓库fork=false、archived=false；本次观测286星、27Fork，作为观测值保存。

核心模块的NAME同时列出Lingua::Sinica::PerlYuYan与中書珨；CC0段直接署名唐鳳。历史目录将同一仓库称作文言Perl。上述名称构成可核同源关系。

### 原作连续代码

固定[lib/Lingua/Sinica/PerlYuYan.pm第23—33行](https://github.com/audreyt/lingua-sinica-perlyuyan/blob/08b4d8294876903ed7ff193fa3a08f247d66b637/lib/Lingua/Sinica/PerlYuYan.pm#L23-L33)保留英文算法注释、Perl模块导入、空行及八行连续繁体中文埃拉托斯芬筛法。JSON按原POD缩进、标点与字形保存，共11行。全文读取和单独第23—34行读取逐字核对，blob为3ac0956e79ae555ab3892eefba742b37ca35128e。

原例使用“用、吾、當、印”等语法与内置词。固定[t/1-mult.t](https://github.com/audreyt/lingua-sinica-perlyuyan/blob/08b4d8294876903ed7ff193fa3a08f247d66b637/t/1-mult.t)另保存俄农式乘法，末尾测试预期俄農(18,23)=414。预期值按作者测试源码记录，执行结果继续待核。

### 实现与分类

分类为“Perl文言中文方言／源过滤转换层”。

1. [第57—71行](https://github.com/audreyt/lingua-sinica-perlyuyan/blob/08b4d8294876903ed7ff193fa3a08f247d66b637/lib/Lingua/Sinica/PerlYuYan.pm#L57-L71)逐对读取DATA英文与中文词表，中文行逐字展开，构造%Tab；英文多字母关键字补空格。
2. 第73—74行设置資曰、亂曰、檔曰、列曰、套曰等多字标记。
3. [第76—84行](https://github.com/audreyt/lingua-sinica-perlyuyan/blob/08b4d8294876903ed7ff193fa3a08f247d66b637/lib/Lingua/Sinica/PerlYuYan.pm#L76-L84)FILTER进行UTF-8解码、按中文键长度降序全局替换，再编码输出；第87—95行translate为英文文本到中文的反向替换。
4. [第206—213行](https://github.com/audreyt/lingua-sinica-perlyuyan/blob/08b4d8294876903ed7ff193fa3a08f247d66b637/lib/Lingua/Sinica/PerlYuYan.pm#L206-L213)列if→倘、while→當、return→回、sub→副、my→吾、use→用。
5. [Makefile.PL](https://github.com/audreyt/lingua-sinica-perlyuyan/blob/08b4d8294876903ed7ff193fa3a08f247d66b637/Makefile.PL)明确依赖Filter::Simple::Compile 0.02。其[MetaCPAN原始模块文档](https://metacpan.org/pod/Filter%3A%3ASimple%3A%3ACompile)说明与Filter::Simple API兼容并基于Module::Compile。
6. [t/2-table.t](https://github.com/audreyt/lingua-sinica-perlyuyan/blob/08b4d8294876903ed7ff193fa3a08f247d66b637/t/2-table.t)保存映射表断言；源码测试与测试成功分开处理。

当前实现为全局文本替换。字符串、注释、正则上下文、重复词映射及整体语义兼容待核实。核心use 5.008与Changes 0.11所述5.10分开保存，各功能最低版本继续核实。

### 时间、版本与许可

[技术Changes第193—206行](https://github.com/audreyt/lingua-sinica-perlyuyan/blob/08b4d8294876903ed7ff193fa3a08f247d66b637/Changes#L193-L206)记0.01=2002-01-21、0.02=2002-01-22、0.03=2002-08-18。以上是原作者历史记录；早期发行附件及准确首次公开时刻继续待核。

默认分支历史完整读取至空parents根：89d0bcf63d4986da915c9021a42b5b3a4ea12669，2009-03-01T15:46:04Z；GitHub建库2009-10-30T20:22:25Z。head作者时间2014-11-03T17:42:06Z，提交者时间2015-01-10T05:00:01Z，仓库pushed_at为2015-01-10T05:00:08Z。updated_at属于GitHub活动元数据，技术维护按提交字段判断。

核心VERSION=1257700140.47574，源码旁注2009年11月9日；README保留1257439830.94865，旁注2009年11月6日。2009-11-04的Changes说明版本号改用Unix时间戳。GitHub Releases及matching-refs/tags均返回空数组；CPAN发行与源码版本对应继续待核。

[固定CC0段](https://github.com/audreyt/lingua-sinica-perlyuyan/blob/08b4d8294876903ed7ff193fa3a08f247d66b637/lib/Lingua/Sinica/PerlYuYan.pm#L103-L110)、README与Makefile.PL一致采用CC0 1.0。技术Changes记0.10的MIT阶段及2009-11-04转CC0；[切换提交513eef3a…](https://github.com/audreyt/lingua-sinica-perlyuyan/commit/513eef3ae505f5362e29c8a47bc85cc7635f7a24)明确范围含全部文件。GitHub自动许可字段null按机器元数据保存。AI开发参与待核实。

技术文档只采用Changes中的版本和贡献记录；作者其他个人叙述保持资料源内部背景。

## 二、脑语言：新候选，词表／输入工具／组合平台分层

### 发现与作者资料

发现入口为[腾讯云原创《脑语言v0.5.8 2500令【单字编程】》](https://cloud.tencent.com/developer/article/2045815)，页面作者账号脑语言，显示2022-07-11 19:35:08，时区待核。词汇表可见如→if、返→return、虽→while等对应；末尾自述正在制作JavaScript单字编程教程。

GitHub检索找到：

- [naoyuyan/naoyuyan@986be50b55d60ce9e5869c9e6d0edc80dbed629f](https://github.com/naoyuyan/naoyuyan/tree/986be50b55d60ce9e5869c9e6d0edc80dbed629f)，完整树6项；提交署名脑语言，index.html Author为广。
- [2500ai/dshjs@82b1d5029a7d7acbd58633e106fd6165b0f1841d](https://github.com/2500ai/dshjs/tree/82b1d5029a7d7acbd58633e106fd6165b0f1841d)，README与核心源码头明确使用“脑语言2500单字”，署名齐庄，Git提交账号2500ai。

两仓自身对脑语言的描述支持技术主题关联。腾讯云、naoyuyan与2500ai的自然人身份和互链继续核实。二手社交搜索页Sotwe仅为dshjs名称的发现渠道，实际技术结论采用GitHub固定原件。

### 2025代码输入阶段

固定[脑语言说明](https://github.com/naoyuyan/naoyuyan/blob/986be50b55d60ce9e5869c9e6d0edc80dbed629f/脑语言说明)自述旧名快语言、云语言、广语言、虚语言，并介绍单字包装现有常用函数。旧名归入该仓项目沿革，各同名外部项目保持独立身份核验。

[html/asi2500.html第316—339行](https://github.com/naoyuyan/naoyuyan/blob/986be50b55d60ce9e5869c9e6d0edc80dbed629f/html/asi2500.html#L316-L339)定义变→let、返→return、条→if等代码块映射；[第500—527行](https://github.com/naoyuyan/naoyuyan/blob/986be50b55d60ce9e5869c9e6d0edc80dbed629f/html/asi2500.html#L500-L527)按长按状态选取代码文本并插入Monaco，预览直接设置innerHTML。该固定材料支持中文单字代码输入工具分类。

[README](https://github.com/naoyuyan/naoyuyan/blob/986be50b55d60ce9e5869c9e6d0edc80dbed629f/README.md)直接声明“所有代码由AI生成，vibecoding 氛围编码可以走多远？”。这属于原作者对该仓的AI开发声明；工具、模型、文件比例和复核方式待核。

建库2018-12-20T03:23:33Z；根提交898c79e00eb26e2a2db49070bd0b5b39dd39d0b7为2018-12-20T03:29:24Z；完整可达历史7条。2025头为2025-03-20T10:42:50Z。完整树6项、自动许可字段null，许可待核。

### 2026函数组合平台阶段

[固定README第77—113行](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/README.md#L77-L113)将中文单字明确称为函数aliases，组合示例采用JSON。源码[registry.js第13—39行](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/src/fn/registry.js#L13-L39)将原名及中文别名放入Map，通过atom.run调用；[第45—78行](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/src/fn/registry.js#L45-L78)实际解释pipe、map、if、parallel结构。中文函数名与英文结构语法分别记录。

[naoyuyan2500.js](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/src/fn/naoyuyan2500.js)定义1.5.0、2500个汉字、100类和每类25字，解析TSV并检查字与编号。词表定义、可调用函数覆盖和中文语法能力各自保存。README自述46个函数原子，精确覆盖待核；2500词表规模按数据规范层记录。

[package.json](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/package.json)为dshjs0.0.7、Node>=22。[LICENSE](https://github.com/2500ai/dshjs/blob/82b1d5029a7d7acbd58633e106fd6165b0f1841d/LICENSE)为MIT，署名Copyright (c) 2026 2500.ai。dshjs建库2026-08-23T19:35:27Z，根提交86007ba516d3021b496d0bc72ffecc21e7f67268为19:35:28Z，head为19:40:46Z；完整可达历史2条。两仓Releases和matching-refs/tags均为空数组。

项目含DeepSeek API适配与LLM工具循环，源码头感谢deepseek与dsh。AI产品功能、平台上游关系和开发协作比例分开核实；2025仓的AI声明仅适用于其原始陈述范围。

### 收束与下一步

本轮材料支持“中文单字词汇规范／代码输入工具／中文函数别名与JSON组合DSL平台候选”。满足正式门槛的中文语法连续原作程序继续待核。后续优先取得原作者示例与对应解析／转换入口，再核账号互链、词表演进、旧仓许可与B站原BV。平台及旧名保持一组研究对象口径。

## 三、背景筛选与遗漏风险

- [历史目录program-in-chinese/overview](https://github.com/program-in-chinese/overview)用于定位原仓：文言Perl已转原作者固定文件；HTWX Klang、CTS、圈3／4／5、孔Caml、Z语言等为Issue #5旧线索。
- [股票Klang／K浪文档](https://klang.org.cn/docs/)自称股票公式语言，中文段落原例为中文变量和函数名配英文if；按中文命名背景记录。该页面指向asmcos/Klang，和HTWX/klang_dlang按原仓身份区分。本轮深入计数为0。
- 衍真已在Issue #3与第六轮日志中留档，本轮网页再次命中同一GitCode入口，保持旧候选状态，深入增量0。
- CNlua的原仓名xgongya/cnLua可供后续轮换；本轮仅仓库搜索背景，深入增量0。
- 2024—2026优先查询命中大量编程教程、中文标识符与AI宣传。日期词为检索条件，结果需按原件核验。搜索返回“推荐时间”“爬取时间”分别处理。
- B站泛词与脑语言精确查询返回教程、脑科学及无关视频；本组可核相关原BV为0。网页搜索的索引与排序存在遗漏，低播放量原片和站内未索引投稿留待专门入口核验。
- MetaCPAN部分普通open返回Cache miss或不可访问；原仓固定文件可读，采用GitHub原件完成核心核验。Cocos公开主题104733普通open返回Cache miss，保存发现背景后收束。GitCode衍真普通open返回InternalError，沿用既有受限记录。授权和登录边界保持原状。

## 四、实际关键词与平台

普通网页检索34条查询，按实际执行分组：

1. “CNlua” 中文；“Klang” 中文 编程；“文言Perl” 原作；“中文编程语言” “2025” “自制” -易语言 -文言 -仓颉 -凹语言 -光明 -段言 -豫言。
2. “CNlua” 编程 代码；“文言Perl”；“Lingua::Sinica::PerlYuYan”；“中文编程” “Klang” 源码。
3. site:bilibili.com/video “中文编程” “2026” “自制” -易语言 -仓颉 -文言 -凹语言；site:bilibili.com/video “中文语法” “编程语言” 2025；site:github.com “中文关键字” “2026” -CNplus -PyCN -python -cantonese -qilang；“中文编程语言” “论文” “关键字”。
4. “衍真” “yzcc”；“衍真” “编译器” 代码；“nextOS” “yzcc” github。
5. “脑语言” 编程 源码；“脑语言” “函数”；“中文关键字” “2026” “新语言” -cnplus -奇语言 -pinyin。
6. “脑语言” “JavaScript单字编程”；“脑语言” “如” “返” 编程；“脑语言” site:bilibili.com/video；“naoyuyan” github。
7. “脑语言” “单字编程” 源码 -site:bilibili.com；“naoyuyan” -site:bilibili.com；“脑语言” “2500.ai”；“dshjs” github。
8. “脑语言” “单字编程” “如(”；“脑语言” “JavaScript单字编程” -site:cloud.tencent.com -site:developer.cloud.tencent.com -site:sotwe.com；“脑语言” “naoyuyan” github；“脑语言” “bilibili” 编程。
9. site:metacpan.org/release “Lingua-Sinica-PerlYuYan-0.01”；site:metacpan.org “Lingua-Sinica-PerlYuYan” “2002”；“Lingua::Sinica::PerlYuYan” “2002-01-21”；“Filter::Simple::Compile” “FILTER”。

GitHub仓库搜索6次：脑语言（20结果上限）、脑语言（30结果上限）、CNlua、naoyuyan、dshjs、2500ai。目录／原仓读取采用观察到的真实仓库与固定SHA。原作者历史资料覆盖2002—2026，优先目标窗口2024—2026；最晚固定实现为2026-08-23。

## 静态核验

资料结构、原始引用与连续示例已核对。独立运行结果待核实。
