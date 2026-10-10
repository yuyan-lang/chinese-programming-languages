# Bilibili 第三轮核验：PandaM、容语言、甲辰Lang

核验日期：2026-10-10。范围为 Issue #11 的三组线索，采用作者原视频、公开评论、官方文档与源码平台页面。

## 结果与去重

- 收录容语言 1 项，条目编号 lang-043。
- 中文语法待核实：PandaM、甲辰Lang 2 项。原片已核看，语言示例为英文关键字，保留研究记录。
- 基线目录为 41 项，data/languages.json 的文件 SHA 为 be2a07596a68b9570dd3fdc54d2f98b6f519f518；本轮三项均尚未列入该基线。
- 已读取 AGENTS.md、Issue #11 及评论（当时评论数为0）、2026-10-10/bilibili.md。另检查 2026-10-09 的 bilibili/repo/community 和 2026-10-10 的 repositories/existing 日志，三项名称在这五份日志中未出现。豫言保持本轮范围之外。
- Issue #11 仍有其他子项，整项进度应由总研究记录汇总。

输入：
- https://github.com/yuyan-lang/chinese-programming-languages/issues/11
- https://github.com/yuyan-lang/chinese-programming-languages/blob/main/AGENTS.md
- https://github.com/yuyan-lang/chinese-programming-languages/blob/main/data/languages.json
- https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/bilibili.md

## 容语言：中文语法已核实

### 作者与来源链

原线索：https://www.bilibili.com/video/BV1inph6zEYS/
标题：【容程序IDE】第三集：简易成绩单！容语言？中文编程，自制编程语言！
发布账号：文醒青年，https://space.bilibili.com/406482868/

第三集简介直接给出 rongyuyan.cn 和 rongyuyan.cn/docs。官网提供语言语法、教程、安装/便携下载和版本历史。因此语言名称、IDE、域名之间的关联来自作者自己的公开页面。

- 官方语法：https://rongyuyan.cn/docs/#quickstart
- 当前官网：https://rongyuyan.cn/
- 历史版本：https://rongyuyan.cn/history
- 第一集原视频：https://www.bilibili.com/video/BV18FHb6HE24/

### 日期与版本

- 第一集 video:release_date = 2026-10-05T15:20:33.000Z，UTC与北京时间均为2026-10-05。
- 第三集 video:release_date = 2026-10-09T16:51:51.000Z，北京时间为2026-10-10 00:51:51。
- 官网历史页将 v1.0.0 标为“首个公开版本”，日期2026-10-08。
- 当前主页标注 v1.1.0，日期2026-10-10；语法文档仍标注 v1.0.0。
- 条目采用“至少于2026-10-05公开演示；官网将2026-10-08标为v1.0.0首次公开发行”，分别记录演示和发行。
- 网站页面存在标准库数量差异：主页的数字与文档的396条表述不同。条目采用实际可读的语法与组件描述。

### 中文实码

官方“快速上手”的完整 你好.rcx 代码块已按 DOM pre 原文摘录至条目，保留Tab缩进、双空格、标点。包含：
- 载入 系统库
- 窗口【名称…大小…】
- 函数 窗口函数【】：
- 函数 主函数【】：
- 当 开始 = 点按：
- 系统库.消息框(...)

代码出处：https://rongyuyan.cn/docs/#quickstart

05:34原片画面显示中文代码、成绩单设计预览及正在运行的成绩单窗口。视频代码分辨率限制逐字转录，目录代码取自更清晰的官方文档。

### 实现与关系边界

官网当前下载页和历史页均标注内置Python运行环境。文档“编译与分发”描述把整个工程打包为独立Windows可执行文件。
- 安装包说明支持记录Python运行环境关联。
- 解析器、执行器和打包器实现语言/架构仍待源码核验。
- v1.1.0新增的Mac/Linux、MicroPython、PLC/ST能力为官网自述，本轮记录保留为待验证能力。
- 容语言、容程序和容程序IDE在本目录合为一个语言项目；IDE单独计数会重复。
- 与易语言、语程等对象的继承、移植、兼容关系待核实。
- GitHub按“容语言”“rongyuyan”检索与官网链接核查，尚未定位作者确认的公开实现仓库。

### 原片评论

第三集评论区最终显示1条公开评论，评论者为 -Logic-罗辑-（UID485953759），内容为鼓励及宣传 https://logicyolo.com/。该地址与Chinese++候选有关，保留给相关子项核验；容语言作者归属不据此改变。

## PandaM：原片有英文关键字语法；中文语法待核实

原片：https://www.bilibili.com/video/BV1DhpM6YEMf/
作者：星空空空525，https://space.bilibili.com/3546712874421199/
video:release_date = 2026-10-07T06:56:41.000Z，UTC与北京时间均2026-10-07。
标题标注1.1.2；语言初次公开日期待核实。

简介给出官网 http://starrytech.top/pandam，云端浏览器最终导航到 https://starrytech.top/pandam，返回502及“Certificate verify failed: unable to get local issuer certificate”。该来源核验止于错误页，证书安全控制保持原状。

### 视频证据

06:43暂停帧标题“聚合与模式匹配”，包含 struct、variant、match，以及 int、double 等英文关键字/类型。中文位于解释说明和字幕。另核看了可选值、try/catch以及完整shape示例等幻灯片；原片总时长14:01，本轮采用关键帧抽查。

影片首页自述LLVM与原生编译性能，后续幻灯片称全静态和自动内存管理。实现源码、具体LLVM版本、性能与编译可复现性待核实。

### 作者评论

置顶评论由同一UID作者发布，说明此片使用手机重新拍摄PPT，PPT及文档有AI参与，人工提供文案和检查。因此证据级别明确为作者幻灯片语法展示。
作者在“未来会开源吗”的评论下回复“会的会的”。这记录了作者的未来意向；本轮可确认的公开源码仓库仍待核实。

### 分类结论

目前确认PandaM是一组带英文关键字示例的语言发布资料。中文关键字或中文控制结构的第一方示例待补充，本轮维持待核实状态。
网页搜索的 pandcorps/pandam 是Java/Android游戏引擎。GitHub检索出现的 lbframe/pandam-style 为设计系统样式语言；StarryTech/StarryTech.github.io 是早期网页仓库。三者与本片项目的身份关联均待证，本轮仅把它们列作同名检索噪声。

## 甲辰Lang：原片英文关键字，找到作者发布渠道

原片：https://www.bilibili.com/video/BV1gbhU6iEvT/
作者：南京甲辰语言工作室，https://space.bilibili.com/1823337404/
video:release_date = 2026-09-25T14:09:01.000Z，UTC与北京时间均2026-09-25。
原简介将用途写为游戏脚本和跨平台界面开发。

### 视频证据

- 12:56附近：容器和函数代码使用 public static void、Vector<String>、new 等写法，中文内容在字符串中。
- 13:06附近：运算符重载使用 class、public static int operator、if、return 等英文关键字，注释为中文。
- 保存的稳定暂停帧为13:57：FunctionObject类示例，包含 class、void、public、return、if。中文位于注释和中文文件名中。
- 精确暂停帧来源使用原BV，不把旁边推荐视频当作本项目；总时长21:21，本轮为关键段抽查。

### 作者评论与Gitee

作者置顶评论把以下地址标为“语言和编辑器下载链接”：
https://gitee.com/yiwan1000/sine-code--learning-version/releases/tag/SineCode

同作者公开回复说明“解释执行”。本轮将执行模式写为作者自述；实现源码待核验。

Gitee云端浏览器已核查：
- 仓库名：Sine Code-学习版，账号yiwan1000
- 默认分支master，页面显示1次提交
- 根目录列出README.md和README.en.md
- README主要为模板段落，软件架构写“软件架构说明”，安装/使用说明为xxxx占位
- 发行页标题SineCode，页面日期2026-09-25 22:01
- 对应提交：5fbf78e480a3ff624a591d8410c7e8d3337229be
- 附件名：Sine Code-学习版.exe
- Gitee自动提供的Source code zip/tar.gz链接表示仓库快照；该仓库当前文件列表提供README级材料
- 页面未声明许可证

来源：
- https://gitee.com/yiwan1000/sine-code--learning-version
- https://gitee.com/yiwan1000/sine-code--learning-version/blob/master/README.md
- https://gitee.com/yiwan1000/sine-code--learning-version/releases/tag/SineCode
- https://gitee.com/yiwan1000/sine-code--learning-version/commit/5fbf78e480a3ff624a591d8410c7e8d3337229be

### 分类与关系结论

甲辰Lang与Sine Code-学习版之间的语言/编辑器发行关联已由原作者置顶链接建立。具体改名沿革、编辑器和语言版本对应关系仍待核实。当前可见语法为英文关键字；中文关键字或中文控制结构的第一方证据待补充，本轮维持待核实状态。
作者对性能的评价属于宣传性自述，相关基准数据和实现细节属于后续验证范围。

## 检索覆盖与遗漏风险

### 实际平台与关键词

- GitHub接口：按PandaM、PandaM language、starrytech、容语言、rongyuyan、甲辰、甲辰Lang、jiachenlang检索仓库；读取百科现有目录、Issue和研究日志。
- 公共网页搜索：三条精确BV号；PandaM+编程+星空；容语言+文醒；甲辰Lang；rongyuyan.cn；PandaM+starrytech；甲辰Lang+编程+语言；文醒青年+容程序+源码。
- Bilibili：直接打开三条精确原BV、查看作者/简介/公开热评/置顶、读取日期元数据、关键帧暂停；经第三集推荐位进入同作者第一集。
- 作者网站：容语言主页、/docs/、/history；PandaM官网错误页。
- Gitee：甲辰作者置顶链接指向的发行页、仓库根和README。

### 实际限制

- 公共网页搜索对这三组新项目收录稀少，精确BV查询返回空；名字检索大量返回同名、甲辰干支与自然语言相关内容。
- 初始web open的Bilibili、Gitee页返回Internal Error；云端浏览器正常访问了原片和Gitee。
- B站评论需要滚入页面并等待正常加载。早期AX显示“正在玩命加载”；最终PandaM和甲辰公开置顶/热评、容语言1条评论均已读取。其余PandaM19条及甲辰43条完整评论需要登录，完整讨论仍可能包含新链接。
- B站服务端页面日期、客户端显示日期与带Z的video:release_date存在时区展示差异；报告保留带Z元数据并明确北京日期。
- 播放器快进之后有异步画面变化；关键时间点通过暂停后再次检查播放时间固定。自动连播曾切至推荐片，已识别并重新打开原BV；推荐内容未用作原项目证据。
- 容语言视频画质限制精确抄录；官方文档可提供逐字语法。
- 三条原视频均采用关键段抽查。作者全部投稿、完整长片、全部评论、群文件以及发行包内容仍在本轮覆盖范围之外。
- 本轮属于有限候选核验，结果不代表中文编程语言的穷尽搜索。


### 时间范围

检索重点为2026年9—10月的原作者发布资料，三条指定候选逐项核验。查找首次公开资料时采用作者历史页和较早投稿，保留演示日期与发行日期的区别。
