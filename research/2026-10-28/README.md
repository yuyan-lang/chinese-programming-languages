# 开放议题处理台账

核验日期：2026-10-28（UTC）。沿用[上一轮资料](../2026-10-25/README.md)及[PR #79](https://github.com/yuyan-lang/chinese-programming-languages/pull/79)，重新读取根规范、当前目录、研究日志、全部21项开放议题正文及评论、两项开放PR的差异和评论。工作基线为 `4e00d5240ff5ca99c745c2b00179c11e42bef800`，语言110项、内核20项。

本轮按互不重叠的议题组并行核验，来源与分类由独立sol审阅。收录依据为具体中文语法与原始程序，或内核自身实现与公开作者／社区关联；作者声明、静态源码、作者演示与独立运行分别记录。具体证据未知时继续标明待核实。非必要的完整历史、精确首发日与独立运行结果作为可继续完善的字段保存。

## 本轮落地资料

- 新增语言4项：lang-111中文编程IDE（天文苑）、lang-112语程（旭猜囱演示）、lang-113如意III中文编程、lang-114飞鱼中文编程。
- 新增内核4项：KrcyOS、hudos／hodos、BearOS／小熊操作系统（作者技术文档阶段）、NeoRunST（官方v0.13.0发行物阶段）。KrcyOS按主站所在地自述记录中国关联，国籍待核实；hudos按固定资源分工记录为ARM64 UEFI承载实验内核。
- 完善既有语言3项：lang-090天河的关联实现历史、lang-104教材语言的实训编辑与传输链、lang-110客舍的原站论坛正文和时间。
- 完成 #43 已核发布物的词表／输入工具／JavaScript教学手册／API与JSON组合平台分类，语言目录增量0。

## 逐项结果与最小剩余材料

“合并后关闭”表示本轮资料达到该议题合理处理范围；远端关闭以关联PR合并和证据评论为前提。复合议题存在实质未决子项时继续开放。

| 议题 | 本轮结果 | 处置／剩余实质材料 |
| --- | --- | --- |
| [#3](https://github.com/yuyan-lang/chinese-programming-languages/issues/3) | 19组中17组完成收录或范围分类；CN_Interpreter归为理念草案，PYCH全部17发行源码已读 | 保留：PYCH作者完整中文程序；衍真公开原仓或迁移互链 |
| [#4](https://github.com/yuyan-lang/chinese-programming-languages/issues/4) | 语程与如意III原片公开720P可读连续中文原例；原五组均已有处理结果 | 已随PR #80关闭；来源限定、同名与版本关系保留条目字段 |
| [#5](https://github.com/yuyan-lang/chinese-programming-languages/issues/5) | TRAE原帖及原图补成天文苑条目；无极日期与公开范围、Wxe工件定向核对 | 保留：无极公开语法／原例，Wxe作者程序／编译器原件 |
| [#13](https://github.com/yuyan-lang/chinese-programming-languages/issues/13) | KunOS沿用完成成果；NeoRunST官网互链及官方VHD的独立内核链已核 | 合并后关闭；TheseusOS完整历史继承、源码／许可及运行留条目待核 |
| [#16](https://github.com/yuyan-lang/chinese-programming-languages/issues/16) | SPCNYY两个安装脚本七模块的字符串与GUI插入路径均静读 | 保留：作者连续中文用户程序；其他六组维持已收录／范围分类 |
| [#22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22) | 中文Rust五次提交树及全部34份Rust源码已读；历史Compute为英文Python演示 | 保留：中文Rust作者连续中文程序；52zwbc关联组继续遵守PR #62取消边界 |
| [#23](https://github.com/yuyan-lang/chinese-programming-languages/issues/23) | BearOS自身保护模式、任务／FS／Shell分工的详细作者技术文档与发布链已核 | 已随PR #80关闭；全部功能限作者声明，源码继承与发行物细节保留待核 |
| [#24](https://github.com/yuyan-lang/chinese-programming-languages/issues/24) | ThLang主线96提交、分支用途、Cython五提交及周蟒默认词表比较补证 | 保留：视频compiler与ThLang／zhpy的具体源码继承对应 |
| [#29](https://github.com/yuyan-lang/chinese-programming-languages/issues/29) | 固定VDI／EFI的有界静态分析取得内嵌Rust内核实现证据 | 保留：视频作者与发布仓直接身份互链、固定盘与Halo演示版本对应 |
| [#31](https://github.com/yuyan-lang/chinese-programming-languages/issues/31) | 已有说了算CLI及LightLang条目保留；原始Web来源继续缺失 | 保留：Saysuan Web与原始结果材料；PR #76保持草稿 |
| [#32](https://github.com/yuyan-lang/chinese-programming-languages/issues/32) | TX公开分发页资料与既有Open成果分别记录 | 保留：TX／FendosPE自身内核与Open关系的原件 |
| [#33](https://github.com/yuyan-lang/chinese-programming-languages/issues/33) | 飞鱼官方第17课清晰原例、微信开发者工具生成目标与日志已核 | 已随PR #80关闭；转译源码、保存格式及全面支持范围保留条目字段 |
| [#40](https://github.com/yuyan-lang/chinese-programming-languages/issues/40) | 玄沿用完成成果；Lua正常公开Git读取连接重置 | 保留：lyzavng/lua作者连续中文原例 |
| [#43](https://github.com/yuyan-lang/chinese-programming-languages/issues/43) | 2500js原件、dshjs固定源码及作者说明完成工具范围分类 | 已随PR #80关闭；未来新增语法依据新材料重新评估 |
| [#46](https://github.com/yuyan-lang/chinese-programming-languages/issues/46) | HanOS范围问题保持待答 | 保留：用户明确决定是否按“中国关联、国籍待核实”收录 |
| [#48](https://github.com/yuyan-lang/chinese-programming-languages/issues/48) | E#10提交、CH-VM5提交、易深IDE5提交完整静读；ESIL／CHIL文本关系已核 | 保留：完整中文用户程序、具体句法及实际语言前端 |
| [#49](https://github.com/yuyan-lang/chinese-programming-languages/issues/49) | hudos自身ELF→EL0→SVC→协作式恢复链与UEFI资源分工已核 | 已随PR #80关闭；回收覆盖准确限定，独立运行及完整隔离保留待核 |
| [#52](https://github.com/yuyan-lang/chinese-programming-languages/issues/52) | MimicryOS沿用完成成果；Causenix历史与公开工件定向核对 | 保留：Causenix内核本体、公开来源及继承关系 |
| [#59](https://github.com/yuyan-lang/chinese-programming-languages/issues/59) | 教材使用说明→实训站→编辑及WebSocket传输链已核；取得博流公司原文 | 保留：教材语言与博流正式命名／版本对应，服务端语言实现 |
| [#63](https://github.com/yuyan-lang/chinese-programming-languages/issues/63) | FCary原站两主题RSS、原文及首帖UTC已核 | 保留：FCary与Fancyary／Wang Zhangli的直接身份互链、方案与源码版本对应 |
| [#64](https://github.com/yuyan-lang/chinese-programming-languages/issues/64) | KrcyCode当前API所在地HeFei与作者／主仓互链已核 | 已随PR #80关闭；所在地自述与国籍分别记录，固件与运行细项保留待核 |

本轮目录总数为114项语言、24项内核；合计完成7项议题的资料核验，保留14项的具体实质缺口。

## 证据分组

- [历史原件、TRAE原图与E#关系](issues-3-5-48.md)，[固定提交及资产摘要](issues-3-5-48-evidence.json)。
- [视频原例与compiler关系](video-backlog.md)，[原站元数据与原帧摘要](video-primary-evidence.json)，[固定关系证据](video-relations-evidence.json)。
- [SPCNYY、中文Rust、Lua与脑语言范围分类](mixed-scope-review.md)，[固定来源及访问结果](mixed-scope-evidence.json)。
- [KrcyOS与hudos资源分工](kernels-a.md)，[实时API回执摘要及固定源码链](kernels-a-evidence.json)。
- [NeoRunST、BearOS、Halo、TX与Causenix](kernels-b.md)，[固定发行物摘要](kernels-b-artifact-metadata.json)，[Halo短反汇编摘录](halo-static-evidence.txt)。
- [NeoRunST官方VHD内核链](neorunst-vhd.md)，[文件与符号摘要](neorunst-vhd-static.json)，[短指令摘录](neorunst-static-excerpts.txt)。
- [教材实训与客舍论坛](root-primary-review.md)，[公开原件摘要](root-primary-evidence.json)。

## 验证与操作边界

既有语言与内核的ID、顺序、字段、原始主例及全部原参考URL保留。豫言语言、豫言内核、其他仓库及官网原样保留。JSON、HTML代码与引用、内部链接／锚点、索引集合、证据图摘要及差异空白检查纳入验证；独立sol审阅发现的hudos回收范围和视频时间已修正。

本轮来源读取及二进制分析均为静态资料处理。候选软件安装、构建、启动、测试及程序执行均为0。PR #62取消合并持续有效；PR #76来源未恢复前保持草稿；#46的用户范围决定继续待答。部署核验限已有GitHub Pages自动流程及发布页面的只读检查。
