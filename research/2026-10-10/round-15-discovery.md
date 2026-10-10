# 第15轮：Gitee与中文社区发现分项
研究日期：2026-10-10。基线：yuyan-lang/chinese-programming-languages@757ddd0d875cb114b7261e389aa9a8a002f86c80。

## 本轮结果
- 正式候选2项：calvinwilliams/zlang；知语言（知心编译器，位中原／zhiyuyan/tcc）。
- 初筛线索1项：汉源码（liu-guanglin/lglCode）；保留在日志，深核待核新增数为0。
- 2项正式候选均属于目录新发现。zlang自身历史始于2022年，中文编程功能有2024年原作者记录；知心源码版权含2019年，所读正式发行日期为2025年。首次发现日期与项目创制日期分别记录。
- AI参与：两项原作者AI开发声明待核实。本轮发现数量不等同于AI生成语言数量。

## 去重范围
读取基线AGENTS.md、全部80项data/languages.json、research/2026-10-10/round-14.md、24个开放Issue正文，以及这些Issue的63条评论；比对名称、别名、作者、原仓URL。calvinwilliams/zlang、zhiyuyan/tcc、知心编译器、知语言、汉源码、lglCode均逐项检索。
- 已录cnzkai/Zlang按作者和原仓辨识。calvinwilliams/zlang的对象克隆模型、C词法／解释执行实现与中文阶乘原例单独取证。
- zyw98020/Zlang---Chinese-programming-language由本轮登记待核；Xiaofei-it/Zlang作为同名辨识项，关系待原作者证据核实。
- 墨香080、脑语言Issue43、RuleDSLCore35、说了算31、墨言26按既有条目处理。
- skywalk163中文语言系列命中既有Issue5及第6／14轮关系背景。zhixing、traeyan、yanzhi、xinyu、moyan、yanlv、mingdao、hanyu等此次只保留检索背景。
- 文言003、言序007与csg按对应专题核验；豫言原状保留。

## 1. zlang（calvinwilliams）
原仓：https://gitee.com/calvinwilliams/zlang
固定头：07a764e6ba76ee95bed61ee839a42c2ca51782cd，release分支页面时间2026-09-27 23:32:54 +0800，标题UPDATE TO V0.12.8.0J。

### 作者、历史、版本和许可
固定AUTHORS署名calvin，联系邮箱位于原文件；账号calvinwilliams。自然人中文姓名待核实。固定ChangeLog-CN记2022-03-22创建0.0.1.0、2022-05-29跑通hello.z；0.2.1.0（2024-02-08）写“开始支持中文编程”，次日添加存量对象中文别名。首项0.12.8.0日期2026-09-22，另列0.12.2.0日期2026-08-13。固定根LICENSE为Apache License 2.0，所读token.c有相应版权许可头。依赖与对象库逐项许可待核实。
固定链接：
- https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/AUTHORS
- https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/ChangeLog-CN
- https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/LICENSE

### 原例和实现
固定中文章节：https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/doc/chinese_programming.md
摘录该章test_factorial_chinese.z完整连续19行，保留charset、英文库名、空白与缩进；导入、函数、如果、否则、返回构成中文语法。作者紧接展示720。本轮读取该输出，实际运行结果待核实。章节页面最后修改日期2026-08-03 21:46 +08:00。
固定charset_UTF8.h第17、25、40行分别含主函数入口、“如果”“函数”；lexical.c的MATCH_ALL_CHARSET_ALIAS把不同编码的中文别名映射为TOKEN_TYPE_IF、TOKEN_TYPE_FUNCTION等。interpret.c的InterpretStatement、InterpretKeywordStatement、InterpretExpression可见解释执行路径。上述源码路径均已逐项读取；未执行项目。
- https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/src/zlang/charset_UTF8.h
- https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/src/zlang/lexical.c
- https://gitee.com/calvinwilliams/zlang/blob/07a764e6ba76ee95bed61ee839a42c2ca51782cd/src/zlang/interpret.c
AI参与声明待核实。第三方AI辅助介绍页含自拟演示和提示性免责声明，正式条目引用原作者章节。

## 2. 知语言（知心编译器）
原仓：https://gitee.com/zhiyuyan/tcc
固定头：04434cfef8000dd8f9868816016abdeb0f6b0214。固定README介绍知语言关键词、知心编译器、.z文件和zhi工具；关键词表含50项。

### 作者、历史、版本和许可
src/zhi.c署名版权(C)2019-现在 位中原，并保留Fabrice Bellard／TCC版权与派生背景。2019是源码版权起点，准确首次公开日期待核实。
发行：https://gitee.com/zhiyuyan/tcc/releases/tag/0.9.30
可读发行标题zhixinV0.9.30，发布者位中原，页面2025-04-01 14:46，标签0.9.30，短提交bea6483；说明同时支持main()和开始（）函数。附件列出zip，本轮只读页面。
固定根LICENSE为MulanPSL-2.0；完整上游与组件许可边界待核实。
- https://gitee.com/zhiyuyan/tcc/blob/04434cfef8000dd8f9868816016abdeb0f6b0214/README.md
- https://gitee.com/zhiyuyan/tcc/blob/04434cfef8000dd8f9868816016abdeb0f6b0214/LICENSE

### 原例和实现
连续原例取固定src/zhi.c第52—71行，原文包含中文如果／返回及英文if／return，按源文件混合写法保留。该片段是开始函数内部的一段，外层代码块在后文闭合。README另有中文hello示例，其全角括号／逗号原貌可能影响可执行性，采用源码上下文作为正式连续原例。
src/token.h第19—36行用GBK／UTF8编码定义中文类型，第51—72行定义if／else／switch／case／do／while／for／continue／goto／break／return的中文词元。源码中文预处理指令和中文控制流为实现证据。
- https://gitee.com/zhiyuyan/tcc/blob/04434cfef8000dd8f9868816016abdeb0f6b0214/src/token.h
- https://gitee.com/zhiyuyan/tcc/blob/04434cfef8000dd8f9868816016abdeb0f6b0214/src/zhi.c#L52-L71
src/语法分析.c路径转向登录页，读取止于登录要求；该文件内容与语法分析内部路径待核实。未登录、未下载发行包、未编译或执行。运行、性能、自举与平台兼容性待核实。AI参与声明待核实。

## 3. 初筛与排除
### 汉源码
组织项目／关注索引给出liu-guanglin/lglCode及刘光林署名描述，目标为中文编程外壳并逐步替代Python。原仓完整内容和连续语法例待核实，分类为转换层或独立语言待核实，未计正式新增。
- https://gitee.com/organizations/liu-guanglin/projects?lang=C%2B%2B
- https://gitee.com/liu-guanglin_admin/watched?sort=watches.created_at+desc
- https://gitee.com/liu-guanglin/lglCode
### Basic4AI同名对象
二手中文文章将Basic4AI描述为中文Basic式语言并给出安装示例；原GitHub仓1033020837/Basic4AI的README是机器学习／深度学习／NLP学习笔记。词法实现及中文连续程序证据待核实，本轮按同名对象误配风险排除。
- https://github.com/1033020837/Basic4AI
- https://blog.51cto.com/u_12227/14718465

## 检索记录与风险
时窗以2024—2026为主，必要时追溯原作者历史。检索日期2026-10-10。
- Gitee：中文编程 2026、中文语言 2025 如果、中文编程语言加已知项目排除词；随后calvinwilliams zlang、知心编译器 位中原、汉源码 刘光林原仓追踪。
- GitCode／AtomGit：中文编程语言 2025／2026，排除CNSH、凹语言等已有对象；命中多为已知对象和介绍页。
- CSDN／51CTO：中文编程语言 AI 2026、自制 中文编程语言 2025、Basic4AI、skywalk163系列。二手文章和代码块仅用于线索发现。
- Bilibili：中文编程语言 发布 2026，排除文言、豫言、玄铁等既有词；命中课程与已知项目背景，未获得本分项新的可独立核验原仓。
- 中文社区：linux.do 中文编程 AI 我、forum.trae.cn 中文编程语言、V2EX 中文编程 语言；命中旧线索与宣介背景，回归原仓去重。
- 同名检索：zlang v0.12.2.0、zlang calvin 中文编程、知心编译器 源码／语法／如果、Basic4AI中文编程GitHub。
平台限制：普通网页读取Gitee部分源码返回405或缓存失败，使用公开网页浏览器读取同一公共页面；未使用用户桌面。个别路径要求登录，停止该路径并标注内容待核实。
风险：搜索覆盖不代表平台穷尽；页面相对更新时间与源码版权年份不能替代首发日期；同名语言须保留作者／URL限定；作者演示输出与本轮实际测试分开；第三方AI文章的示例不能替代原作者连续原例；许可按所读文件具体范围描述。
本轮仅搜索、读取公共网页／GitHub与整理本地研究文件，未执行、编译、测试或安装项目。

