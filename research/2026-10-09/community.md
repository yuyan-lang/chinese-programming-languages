# 社区检索结果与未决线索

检索时间：2026-10-09 UTC。只读研究；没有发布、修改仓库、安装或运行项目。

## 本批可审查条目

JSON 中收录 Nuzo、Y++、ikdxhz 中文Python解释器。前两者有原作者中文关键字程序；第三者必须归入转换层。完整实现、当前状态未能独立验证的字段均已注明。

## 需要继续核实

- Hanyu-Lang / 汉语编程语言：https://pypi.org/project/hanyu-lang/ 。PyPI 维护者 lin8092_76；0.1.2 上传时间 2025-04-23，Python>=3.8，Alpha，MIT。发布者说明中文关键字「如果、循环、函数定义」、REPL、AST/中间码与 GUI；但本次没有取得源代码或实际中文示例，不能把这些功能写成独立验证。Author 字段是模板「你的名字/团队名」，不是可信作者名。公开上传日期不等于语言最早出现日期。不要采用“首个”宣传。
- 易码2.0：作者 jinglei（道友）2026-02-20 17:33 原帖 https://linux.do/t/topic/1631327?tl=en 。后缀 .ym，原帖说使用 AI 业余开发，展示 RPG 中「让 勇者名 = 问 ...」「如果 勇者名 是 空的」「结束」「当 游戏继续 等于 1 的时候」。另有仓库 jinglei88/Yima---Minimalist-Chinese-Programming-Language，创建日 2026-02-22，不应覆盖更早公告。需核对作者与语法关系，避免重复计数。
- 无极：原作者 CSDN https://blog.csdn.net/qq_28759809/article/details/104977727 指向 https://gitee.com/zhf888/wuji 。文中自述参考《自制编程语言》，拟用 C、lex、bison 构建解释器。全文/仓库本次读取失败，未拿到中文语法实例，保留线索不进正式条目。搜索显示“最新推荐文章于2025-06-21”不能当成首发日期。
- 言叶 / 文言心 / 言：天马行空skywalk 于 2026-05-05 的设计规范 https://deepseek.csdn.net/6a059cdf662f9a54cb746b14.html 明示对比三者，含 定x=5、若…则…否则、函、遍历，分别声称 Python 转译、SBCL、Python 转译后端。很可能是后续段言/光明研究脉络，但关系及独立仓库待核实，不能将一个作者的阶段名称自动计成三门独立语言。文档例子不证明实现存在。
- Wxe-ChineseCoding：聚合索引指向 https://github.com/WangXingwen957/Wxe-ChineseCoding ，称配套 WxeEditor/编译器。GitHub 本次失败，尚无原始中文语法证据。聚合索引 https://aichina.news/repositories/20/ 仅作发现渠道，不作为技术依据。
- TRAE 线索 https://forum.trae.cn/t/topic/165813 本次不能获取，精确检索也没有可靠匹配，不推断标题或作者。另发现 https://forum.trae.cn/t/topic/165845 是 Python++ 混合编程环境；仅 AI 构建编译器不自动满足中文关键字标准。
- 历史目录 https://github.com/program-in-chinese/overview 提供 Klang、CTS、圈3/4/5、孔Caml、Z语言、文言Perl、亲密数、标天汇编、丙正正、O语言等线索。它是目录而非所有项目的原作者技术证据；本批未逐一深查。

## 误命中与分类风险

- V2EX 2025“我们将使用母语编程”指日常自然语言提示生成 C++，链接 DSPy/IBM PDL，没有证明独立中文关键字语言，未收录：https://www.v2ex.com/t/1102281 。
- nature、仓颉、MoonBit 的国产身份或中文文档不能证明中文关键字；中文变量名也不够。
- 同名 Nuzo 搜索大量命中 nuzo-memory，与本次 Rust 语言无关，不能借用其版本/提交/许可证。
- CSDN 的推荐时间、搜索摘要的 Published/Crawled 时间会混淆首次发布；仅正文明确日期可作“可证公开时间”，不是绝对首发。
- 2026 年 SEO 内容出现可疑“腾讯轻舟Studio简码”等产品及仓颉中文语法误报，未采用。
- Zhihu/OSChina 检索结果稀薄，Gitee、CSDN、TRAE 及部分 GitHub 的直接读取间歇性 cache miss。可读取的搜索索引保留了原始页面内容，但不能据此宣称当前可用、活跃或已运行。
- 本轮没有覆盖所有历史学术库、公众号、B站视频画面或登录后社区内容，不应声称穷尽。

## 精确搜索日志（依实际执行顺序，查询之间用换行分隔）

site.zhihu.com 中文编程 语言 GitHub 2025
site.v2ex.com 中文 编程语言 2025
site.oschina.net 中文编程语言 新 2024
site.oschina.net "中文编程语言"
site.v2ex.com/t/ "中文" "语言" "GitHub" "编译器"
site.blog.csdn.net "中文编程语言" "2025"
site.zhihu.com "中文编程语言" "自制"
"中文编程语言" "2026" -豫言 -site:reddit.com
"中文编程语言" "2025" "自制"
"中文编程语言" "Claude"
"中文编程语言" "DeepSeek"
"中文编程" "AI" "编译器" -豫言 -仓颉 -site:reddit.com
"中文编程语言" site:oschina.net/p/
"中文编程语言" site:zhihu.com -易语言 -豫言 -凹语言
"无极" "zhf888"
"中文编程" "言叶"
"中文编程" "AI" "语言" "GitHub" -豫言 -仓颉 -site:reddit.com -Claude
"1631327" "编程"
"Wxe-ChineseCoding"
"无极" "编程语言" "如果"
site:pypi.org/project/hanyu-lang/
site:forum.trae.cn/t/topic/165813
site:linux.do/t/topic/1631327
site:yddphp.cn "Y++"
"闲的蛋疼" "中文编程"
site:forum.trae.cn "中文" "编程语言"
"YStudio" "编译" "C++"
"hanyu-lang" "github"
"Nuzo" "github"
"hanyu-lang" "lin8092"
site:forum.trae.cn "165813"
site:linux.do/t/topic/1631327 "github" "语言"
site:linux.do/t/topic/1631327 "大白话" "2026"
site:forum.trae.cn/t/topic/165813 "语言"
site:yddphp.cn "编译器"
"闲的蛋疼，就用用AI编程做了一个中文编程语言玩" "让"
"Nuzo" "语言" -site:nuzo.com.br
"Wxe" "中文编程"
"YStudio" "一点滴" "2026"
"易码" "jinglei"
"中文编程语言" "AI" "TRAE" -段言 -豫言 -仓颉 -Nuzo
"165813" "TRAE" "中文"
"nimamasl114514/nuzo"
site:yddphp.cn "v2.2" "2026"
"hanyu-lang" "函数定义"
"自制中文编程语言一" "2020"

## 主要直接访问

成功读取：program-in-chinese/overview、ikdxhz/chinese-python、TRAE /14494。搜索索引可靠显示但直接读取失败/不稳定：yddphp.cn 官网和文档、hanyu-lang PyPI、Linux.do /1631327。失败：wuji Gitee、CSDN /104977727、Wxe GitHub、nuzo GitHub、TRAE /165813。不得把读取失败理解成项目已失效。

## 语法证据 QA

三个正式条目均附 code_source 指向原始例子位置。Nuzo 与中文Python只保留各自连续函数定义，避免遗漏中间注释造成拼接引文。中文Python README 自署2024年6月24日与 GitHub 创建时间2025-06-22不同，是否迁移或日期错误待核实；1.0仅为README徽章自述，不等于已核实正式发行。Nuzo所有功能与实现声明均标注作者自述。
