# 中文语法仓库研究记录

核验时间：2026-10-09 UTC。只读GitHub连接器与网页搜索，未运行代码、未改动外部仓库。

## 基线
仓库README读到百科收集中文语法编程语言。本轮研究已读取 data/languages.json，18个现有名：豫言、易语言、文言、凹语言、洛书、粤语、言序、段言、光明、天工语、奇语言、结绳中文、中蟒、周蟒、草蟒、习语言、入墨答、CNPL。

## 精确查询日志
网页搜索按实际顺序：
1. site:github.com/yuyan-lang/chinese-programming-languages
2. site:github.com "中文编程" "2025" 语言
3. site:gitee.com "中文编程语言" "2024"
4. "中文编程语言" "2025" github -wenyan -yuyan -仓颉
5. "中文编程语言" "2026" github
6. site:gitee.com "中文编程语言"
7. site:gitee.com "中文编程语言" "2025"
8. site:gitcode.com "中文编程语言" "2026"
GitHub仓库搜索：
9. 中文编程 created:>=2024-01-01（前100条；噪声多，未作总数）
10. "中文编程语言" created:>=2024-01-01（43条，page1/per_page100）
11. "中文关键字" created:>=2024-01-01（7条，page1/per_page100）
12. "chinese programming language" created:>=2024-01-01（9条，page1/per_page100）

## 核验与产出计数
初筛24个候选README请求，20个成功，4个README.md 404（可能另用文件名，不视为仓库不存在）；14个候选读取完整GitHub API元数据，12个读取顶层文件目录，5个递归树。11个条目完成作者/账号、中文语法、实现、状态、版本或待核实、沿革、日期与不可变链接，详见 data/languages.json。日期均分离仓库创建与语言首发。未复测宣传中的性能、测试数量、跨平台保证。

## 仍有价值的线索（未作为已核实条目）
- CP语言 https://github.com/mycplang/cplang ：2026-05-10建库、1星，README中文关键字、VM/JIT/AOT声明；已经读到src/lexer/lexer.cpp及完整实现树。可下一轮补核，不把其95x等性能声明视为事实。
- zwpy/zw https://github.com/52zwbc/zw ：2026-05-27建库、0星，README明确Python中文外壳和中文关键词表，但仓库仅README与赞赏图片，运行时实现待核实。
- 智语言ZLang https://github.com/cnzkai/Zlang ：2026-04-09建库、0星，README语法明确；仅README+test，所称自举未核实。不能与其他Zlang或Z语言合并。
- Atlanage https://github.com/wc772/atlanage ：README称全中文、自举、M:N调度；待检查样例与源码。
- 中文编程语言设计 https://github.com/Citric1acid/ChineseProgrammingLanguage ：README明确当前只有规范/例程、无编译器/解释器；设计型项目，不误记运行实现。
- CN_Interpreter https://github.com/whitesnowmoon/CN_Interpreter ：README自称开坑不填，只有理念；实现及正式语法待核实。
- CN Language https://github.com/HeiKe-Tom/CN-Language ：README仅宣传、下载盘与截图；关键词与实现待核实，另有tomkiyang/CN-Language可能分支须查。
- PYCH https://github.com/qingsububao/PYCH-Language ：README称Python中文解释器，尚缺实际语法证据。
- Sneko https://github.com/ShineNeko-meow/Sneko-Lang ：仅拼音关键字shu/chu/ruo；是否属汉字中文语法百科边界需明确，不强行收录。
- https://github.com/xxiaoxiong/DaLang 、https://github.com/zf199606/ling-code 、https://github.com/CodeWatcher-Smal/Smal-lang ：README.md 404，其他文件尚待检查。
- coCN https://github.com/3477856804/coCN ：README有让/函数/返回/结束及自举声明；还需核查解释器与引导链，勿仅凭宣传记已自举。
- Gitee 道：作者页 https://gitee.com/kaisen-wang 有“道-中文编程语言”项目卡，四范式声明；项目直链与源码待核实。
- Gitee RexLang：作者 https://gitee.com/xinlengyuer / 原始名RonxBulld，需追查原始项目；不能用SalHeLi fork当原创。
- Gitee 青语言：搜索返回 https://gitee.com/ABBDSB 的fork，原作者数心开物；原始项目待核实。
- CNSH https://gitcode.com/UID9622/longhun-cnsh ：原作者README显示Python生态、中文关键字、v2.1.2 2026-09-20；Gitee原库 https://gitee.com/uid9622/longhun-cnsh ，需下一轮读源码，不把旧提交日志中的未通过3例当当前状态。
- 意语言 https://gitcode.com/gcw_2sDxn3gI/ai-agent-recommends-intent-language ：2026-10-04作者与AI共同评估文章，自述40%及JS宿主；核心源码项目待追。
- 衍真 https://gitcode.com/nextOS/yzcc ：自称全汉语语法nextOS编译器；实现和具体语法待核实。

## 覆盖风险
查询命中数不等于全网总数；GitHub连接器结果不含总命中或incomplete_search字段，不能宣称穷尽。只按关键短语会漏无README、用方言名、仅视频/压缩包、私有或未索引项目。Gitee/GitCode查询主要靠网页索引，原生站内搜索和分页尚未覆盖。2024–2026是仓库过滤条件，非首发年份。低星不是排除条件；没有测试不否认语言存在，但明确未运行。项目性能/“100%兼容”均作者宣称而非独立结论。镜像、改名、fork关系需分别核实；拼音语言与仅中文标识符项目不能混为中文语法。

