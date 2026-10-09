# Bilibili 中文编程语言补录研究

核查时间：2026-10-09，UTC。只读研究。先尝试读取百科仓库，web 返回 cache miss；随后使用GitHub API 验证的18项基线去重：豫言、易语言、文言、凹语言、洛书、粤语、言序、段言、光明、天工语、奇语言、结绳中文、中蟒、周蟒、草蟒、习语言、入墨答、CNPL。未研究豫言本体。

## 可补录结论

本文件对应 JSON 含2个经实际语法验证的独立目录遗漏：玄铁、Calculator.rs 中文试验分支。后者是2023年历史遗漏，不能包装成2024–2026新语言。玄铁的中文语法与源码可验证，首次公开日期仍待核实。没有将未经查看语法的B站视频标题升级为已验证语言。

## 具体待核实候选

1. 中嘞!：原视频 https://www.bilibili.com/video/BV13Q5xzyEE5/ 。标题《[整活] 中嘞!中文编程语言、 好い言語日文编程语言发布会》，发布账号东北大学张引，2025-04-19 16:45:32；搜索索引可确认标题、作者和日期。网页标签为娱乐、搞笑。待核实：视频中的实际中文语法、是否有实现/仓库、是否是演示性设计、方言归属、发布账号与语言作者是否相同。暂建议建立核查Issue，不能仅凭“发布会”当作完成实现。好い言語是日文对象，不计入中文候选。
2. 元语言：索引标题《解释型中文编程语言：元语言》，账号遽火，显示07-13（年份待核实），2分57秒。检索命中地址 https://search.bilibili.com/all?keyword=%E6%98%93%E6%B5%B7%E7%BC%96%E7%A8%8B%E8%AE%BA%E5%9D%9B 。原BV、作者主页、语法、仓库均待核实。搜索页地址只是发现来源，不能冒充原视频。
3. 语程：账号旭猜囱，索引标题《语程中文编程语言，代码格式与易语言一样》（06-06，年份未知）、《语程中文编程-代码易语言版本-语程IDE功能完善中》（07-08，年份未知）、《语程中文编程全免费-易语言版本-大家喜欢的旧老友64位版本》（06-16，年份未知）。来源 https://search.bilibili.com/all?keyword=%E7%BC%96%E7%A8%8B%E8%A7%A3%E9%87%8A%E5%9E%8B%E7%A8%8B%E5%BA%8F%E8%AF%AD%E8%A8%80 及 https://search.bilibili.com/all?keyword=E%E8%AF%AD%E8%A8%80 。精易论坛首页 https://s.125.la/ 另有《语程中文编程-64位程序-易代码(2026-10-07)欧拉插模块已支持》链接文字、发帖账号韩萌㙑，但原帖未定位。需要确认是新语言、易语言兼容实现还是IDE；暂无实际语法证据，不入正式条目。
4. 未命名AI中文编译器：索引标题《Ai开发中文编程编译器自举阶段》，账号神丶樱空释，显示07-01（年份未知），12秒。来源 https://search.bilibili.com/all?keyword=%E7%BC%96%E7%A8%8B%E8%AE%BA%E5%9D%9B 。名称、BV、语法、实现及是否与玄铁等重复皆待核实。
5. 如意III：索引标题《如意III中文编程v1.2测试版IDE操作示例》，jjh345，2024-01-25，19分20秒；来源 https://search.bilibili.com/all?keyword=%E7%BC%96%E7%A8%8B%E7%8F%A0%E7%8E%91 。原视频、语法、与早期如意的关系待核实。

以上5个是去重后具体待核实项目线索，其中只有中嘞!已取得原视频URL，另4个仅索引级线索。严格区分这两种证据等级。无法声称这5个都是新语言。

## 其他发现与跨平台去重

- Y++／Y语言：2026-07-15 10:46:10，一点滴-侠之大者，https://www.bilibili.com/video/BV1tSNq6AE7g/ 《Y++高级界面【3】标签组件》。原简介说明x32/x64、Unicode、IDE/组件库。官方站 https://www.yddphp.cn/index.html 显式提及函数、如果语法。已合并跨平台研究，不计入本JSON独有新增数。
- hanyu-lang：https://pypi.org/project/hanyu-lang/ ，v0.1.2 2025-04-23，描述中文关键词如果、循环、函数定义；已列入跨平台线索。
- 未核实的TRAE链接：https://forum.trae.cn/t/topic/165813 。不同检索结果的描述未能用可靠原文复核，本轮不确认标题、日期、功能或文件扩展名，留待后续调查。
- 炫语言：https://www.bilibili.com/video/BV1KM411h7KK/ ，炫彩界面库，2023-01-09 14:31:12。介绍中英文切换、C++代码转炫、IDE。真实语法未在本次视频文本中显示，适合其他研究线核验旧项目。
- 极语言／SEC：https://www.bilibili.com/video/BV1Bb421Y7qY/ ，极语言中文编程，2024-04-26 20:26:57；https://www.bilibili.com/video/BV1be411M76o/ ，2022-09-22 21:44:44。前者中文指令集/系统编程演示，后者基础课程。此次未取得代码文本。
- 天问：https://www.bilibili.com/video/BV1mA4m1c7Jp/ ，电子芯，2024-04-04 17:29:10。已有大量单片机教学视频；不能因该期日期认定语言2024首发。
- 墨香：独游墨客，索引2025-05-29 CMS教学；飞鱼：跨13平台宣传视频；仅索引未定位原BV，属于其他平台研究线。

## 不计入

- 结绳中文、言序：已有目录，排除重复。
- 仓颉教程：其英文if/while等关键词在课程章节可见，不能仅因中文宣传标题收入。
- mihama（有村ろみ／BIYUEHU，2025-08-17，https://www.bilibili.com/video/BV1JaYrzEEpk/ ）：函数式/依赖类型项目，但本轮没有中文语法证据。
- Key、L语言、Vix：自制语言视频线索，不等于中文关键词语言；不计入。
- AI自然语言提示词、中文字幕教程、中文标识符补全插件、游戏控制台物品代码：排除。
- ZhCode Bridge 显式说不是新语言，是中文入口词到JavaScript的学习桥。若百科收中文前端/DSL可另评估，但不把它悄悄当独立语言。

## 检索覆盖和证据局限

使用web搜索的公开索引与原站页面，及只读GitHub fetch_file。实际读取Calculator.rs Chinese-test README成功，blob SHA 50854fba1829c852d66347bc071586328d13594b；玄铁仓库README成功。没有下载或运行未知代码。

B站搜索URL的直接打开出现“浏览器版本过低”重定向；中嘞!视频直接打开返回内部错误，作者/日期来自其原视频URL的搜索索引。没有绕过登录或反爬。未能实际读取候选视频的评论区、完整动态、字幕或逐帧画面，因此评论/动态和视频内嵌语法仍是明确盲区，不能宣称已经“搜遍B站”。搜索索引常把目标视频夹入无关搜索页，且很多日期不含年、抓取滞后、原BV未暴露；“无源码”在本报告仅表示本次没找到，不等于作者没有源码。2024–2026已优先，但年份不明线索保留不硬填。

## 精确检索词日志

下列为本轮实际提交的查询，按阶段排列；多个查询在同一web调用中批量执行。为避免误导，返回相关搜索页但未命中原视频的查询仍保留。

```text
site:github.com/yuyan-lang/chinese-programming-languages
site:bilibili.com/video "自制" "中文编程" 2025
site:bilibili.com/video "中文解释器"
site:bilibili.com/video/ "中文" "自制编程语言"
site:bilibili.com/video/ "中文" "手搓编译器"
site:bilibili.com/video/ "AI" "中文" "编译器"
site:bilibili.com/video/ "全中文代码"
site:bilibili.com "自制" "中文编程语言"
site:bilibili.com "自研" "中文编程语言"
site:bilibili.com "AI开发中文编程"
site:bilibili.com "中文编程能自举"
"Ai开发中文编程编译器自举阶段"
"玄铁" "编程语言"
site:bilibili.com "中文" "编程语言" "2025" -课程 -教程 -配音 -Python -仓颉 -单片机
site:bilibili.com "中文" "编程语言" "2026" -课程 -教程 -配音 -Python -仓颉 -单片机
site:bilibili.com/video "玄铁"
site:bilibili.com/video "中文编程语言" -仓颉 -课程 -教程 -天问 -易语言 -文言 -洛书
site:bilibili.com "神丶樱空释" "编译器"
site:bilibili.com "中文解释器"
site:bilibili.com "中文编程" "自制" -单片机 -天问 -unity -易语言
"中文编程语言" "2025" bilibili 自己
"中文编程语言" "2026" bilibili 自己
"编程语言" "手搓" "中文"
"编译器" "AI写" "中文"
site:bilibili.com "汉语编程" "自制"
site:bilibili.com "中文语言" "解释器"
site:bilibili.com "中文编译器"
site:bilibili.com "编程语言" "纯中文"
"自制编程语言" 中文 bilibili 语言
"手搓编译器" bilibili
"AI写编译器" bilibili
"全中文代码" 编译器
site:bilibili.com "中文" "语言" "自研" "AI"
site:bilibili.com "中文" "语言" "解释型"
site:bilibili.com "中文" "语言" "我写了"
site:bilibili.com "中文" "语言" "我做了"
site:bilibili.com/video 中文编程语言 自己开发
site:bilibili.com/video 中文编程 新语言
site:bilibili.com/video 中文语言 编译器 开源
"中文编程" "自创"
"中文编程语言" "哔哩哔哩" -site:bilibili.com
"Ai开发中文" 编译器 神
"玄铁中文编程语言 v1.0"
玄铁 编程 问号盒 bilibili
神丶樱空释 中文 编程 bilibili
中文编程 bilibili 自制 2024 2025 2026
中文编程语言 site:bilibili.com/opus
site:search.bilibili.com "中文编程语言"
site:bilibili.com "中文编程" "编译器" "AI"
site:bilibili.com "自制" "汉语"
site:bilibili.com "编程语言" "中文关键字"
"解释型中文编程语言" "元语言"
"中嘞" "发布会"
"语程" "编程" bilibili
"元语言" "遽火"
"中嘞" 编程 GitHub
"元语言" 编程 遽火 bilibili.com/video
"语程中文编程" bilibili.com/video
"神丶樱空释"
语程中文编程 [domains=bilibili.com]
解释型中文编程语言 元语言 [domains=bilibili.com]
Ai开发中文编程编译器自举阶段 [domains=bilibili.com]
玄铁中文编程语言 [domains=bilibili.com]
"中嘞" 编程语言
"语程中文编程" -site:bilibili.com
"元语言" "中文编程" -site:bilibili.com
"神丶樱空释" 编程
语程中文编程
"Calculator.rs" "Chinese-test"
"中文编程语言" site:bilibili.com/read
site:bilibili.com "中文编程语言" "自制" -天问 -炫 -仓颉
site:bilibili.com "中文" "编程语言" "AI生成"
site:bilibili.com "手写" "中文编程"
site:bilibili.com "中文编程" "小学生"
site:bilibili.com "中文编程" "高中生"
site:bilibili.com "中文编程" "AI" "语言发布"
```

直接打开核查（含失败）：百科GitHub URL；B站“自制中文编程语言”和“Ai开发中文编程编译器自举阶段”搜索URL；玄铁官方GitHub；B站“编程论坛”搜索URL；Calculator.rs主仓库、Chinese-test分支、raw README；中嘞!原视频。其余原视频作者/日期来自原站索引内容。可复核的原URL已列各节。

## 固定来源与冻结

GitHub API 补充核验：Calculator.rs Chinese-test提交189e8e23d95c215b1fbb7ff9d31ea2f740b43c89，2023-07-19T03:46:48Z；玄铁master提交17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83，2026-10-06T23:42:05Z。固定README链接已加入JSON。本轮文件冻结，2026-10-09 22:25 UTC。
