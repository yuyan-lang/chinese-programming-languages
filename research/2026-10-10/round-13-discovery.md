# 第十三轮新语言发现：Gitee、GitCode与中文社区

核验时间：2026-10-10 20:31—20:39 UTC。基线提交：[65e45d07d80a36412625665931ce4a4402641480](https://github.com/yuyan-lang/chinese-programming-languages/tree/65e45d07d80a36412625665931ce4a4402641480)。

## 本组结果

真正新发现并深入2组，正式条目0项，待核实2组：

1. 玄（2301_77161129/xuan.ide）：2026年中文C++转译前端／Win32 IDE候选。原仓标题、账号、版本及低关注元数据可读；连续中文程序和转译器全文目前来自注明转载的二手页。原作者CSDN入口已追到，正文读取超时，固定源文件继续待核。
2. Lua 5.4中文版（lyzavng/lua）：历史Lua派生中文前端。固定源码明确包含22项中文词元及与英文共享的编号机制；连续中文用户程序继续待核。发现来自近期目标搜索，项目阶段依据源码与公开时间记录为较早历史项目。

深入范围保持上述两组。第十二轮hscript-c、EC2沿用已收录状态。AI参与均待原作者声明核实。

## 开轮与排重

已读取固定根AGENTS.md、data/languages.json完整76项、第十二轮总览round-12.md、全部39个Issue／PR集合条目，以及全仓67条评论。筛除PR后共有21个开放Issue和56条Issue评论。按名称、别名、原仓URL及作者账号检查：

- xuan.ide、2301_77161129、lyzavng/lua及Lua 5.4中文版均无目录／Issue／评论匹配。
- 检索共享的历轮研究日志、待核JSON，相关原仓与账号同样无匹配。
- LightLang（NomiLight2026）属于Issue #31，墨言属于Issue #26，CNSH、玄铁、Nuzo已在目录，作为既有命中处理。
- 玄语lang-044原仓chy818/xuanyu，自述旧名ZHCC／XY Language；本候选账号2301_77161129，保留账号限定名称与独立原仓链，同源关系待核。
- 言序在当前目录为lang-007，原仓YanXuLang/yanxu；lang-006为粤语。Lua各中文分支与CNlua的具体继承仍需原作者或源码差异证据。
- OldDragon/lua的公开发现页标明Forked from lyzavng/lua，按一个上游候选合并。

## 第一组：玄（xuan.ide）

原仓：[GitCode](https://gitcode.com/2301_77161129/xuan.ide)，同账号[AtomGit入口](https://atomgit.com/2301_77161129/xuan.ide)。

### 当前已核

公开根页直接称项目为《玄》中文编程语言IDE v3.8.2、用中文书写并编译为C++。公开网页浏览器观测0星、0Fork、main、1个分支、0标签及1次提交。这些是2026-10-10观测值。

原仓搜索索引列xuan_ide.cpp与data目录；提交摘要列patterns.txt中文映射、types.txt类型映射、help.txt内置手册和translate_xuan()。原仓当前公开文件区域持续占位，提交入口显示登录，因此固定SHA、实际实现正文及日期保持待核。

[技术栈转载页](https://jishuzhan.net/article/2099289452661886978)提供中文函数与循环程序、词表、Win32转译器源码。该页末尾明确说明转载。点击“查看原文”打开同账号[CSDN文章165223767](https://blog.csdn.net/2301_77161129/article/details/165223767)。原文标签标题显示“啊呜啊呜～中文编程新突破：《玄》让代码更懂中文！”。CSDN两次页面读取分别出现Emulation.setFocusEmulationEnabled、DOMSnapshot.captureSnapshot及Page.getFrameTree超时。

待核JSON保存转载求和函数的连续三行短片段及原文链接，证据层级标为二手，原件对应待核。转载显示的日期有索引2026-09-14 08:09与客户端2026-09-13 17:09两种值，时区解释待核；这两值均保留为转载观测，首次公开日期继续待核。

### 阶段与后续

当前材料支持中文C++转译前端候选方向，原件核验待继续。短连续原例、词法映射和g++调用应在原作者公开文件内建立同一版本关联。许可、发行、AI开发声明及与玄语／玄铁的关系待原始资料。项目规模和关注度按原仓观测保存。

## 第二组：Lua 5.4中文版（lyzavng）

原仓：[lyzavng/lua](https://gitee.com/lyzavng/lua)。固定头：[c0e0b83f7bd323bac7e0326886652075d85d55db](https://gitee.com/lyzavng/lua/tree/c0e0b83f7bd323bac7e0326886652075d85d55db)。

### 固定词法源码

已通过公开blob页面完整读取[固定src/llex.c](https://gitee.com/lyzavng/lua/blob/c0e0b83f7bd323bac7e0326886652075d85d55db/src/llex.c)，608行含末尾空行；页面URL、全文和来源链接保存在研究摘记。

- 第39—56行：22项中文保留字与22项英文保留字顺序对应。中文控制词包含果真、即、否则、要么、因为、当、重复、直至、函数、返回等。
- 第78—91行：luaX_init把两表分别建立字符串并设置同样的extra=i+1。
- 第554—581行：扫描名称时接受高位字节，保留字由isreserved与extra返回语法token。
- 第590行后：luaX_next和lookahead通过llex读取后续词元。

这里是实际中文词法实现证据。目录中还可见lparser.c、lcode.c、lvm.c、lua.c及lbaselib.c。固定lparser.c页面标题可打开，正文提取返回Page.getFrameTree超时。解析与执行全链路具体分支继续待核。

中文词元表归类为实现片段。正式条目的连续中文用户程序原例待补，因此本轮保留候选。

### 历史、许可与维护

公开根页显示头提交消息5.4.0、3分支、0标签、12提交、暂无发行版；浏览器观测16星、4Watching、10Fork。较早搜索缓存为14星、9Fork，分别保留观察时点，维护频次与热度趋势待核。

词法文件页关联最近修改fa00ad33fff1456094dac9865dabe487e470dd4a，时间显示6年前。doc目录最后提交29e016a33a3811c41483d35ded8151e1166fca77，消息5.4.0.20200523。提交消息中的日期与绝对Git时间分别处理。

公开[doc目录](https://gitee.com/lyzavng/lua/tree/master/doc)内嵌readme.html为Lua上游英文说明，保留Lua 5.4.0-beta、Lua.org／PUC-Rio及MIT许可、1994—2019版权。这些属于分发内上游文档；项目侧栏另外标MulanPSL-2.0，适用层级与贡献权利待核。doc/manual.html导航后所见内容仍是原目录readme且标题未更新，按未成功读取手册正文保存。

根README内容被平台屏蔽，已停止该内容读取。提交详情跳转登录后停止该入口。后续仅访问正常公开独立doc与source页面，取得固定词法文件。AI原作者声明、最早公开、准确版本及上游差异继续待核。

## 实际平台、关键词与时间窗

发现目标为2024—2026低关注微型或AI辅助项目。首先做三组高信息搜索，再限定两对象深入。历史结果保留其实际阶段。

### 三组发现查询

第一组：
- site:gitee.com "中文编程" "AI" "2025"
- site:gitcode.com "中文编程语言" 2025
- site:csdn.net "自制" "编程语言" "中文" "2026"

第二组：
- site:gitee.com "语言" "中文关键字" "2025"
- site:gitcode.com "中文编程语言" "AI" -cnsh -moyan -Losu
- site:v2ex.com "中文" "语言" "自制" after:2024-01-01
- site:trae.cn "中文编程语言"

第三组：
- site:gitee.com "中文关键字" "2026"
- site:gitcode.com "中文" "解释器" "玩具" -cnsh -moyan -losu -article
- site:oschina.net "中文编程语言" "2025"
- site:zhihu.com "中文编程语言" "AI" "自制"

### 限定对象追溯查询

- "xuan.ide" 中文；"lyzavng" "lua"
- "《玄》IDE v3.8.2" site:csdn.net；"2301_77161129" "玄"
- "lyzavng/lua" "如果"；"lyzavng" "github"
- "《玄》" "学习智者" 编程；site:blog.csdn.net/2301_77161129 "玄"
- "xuan_ide.cpp" github；"lyzavng/lua" -site:gitee.com/OldDragon
- "lyzavng" lua 中文 关键字；"《玄》IDE" "CSDN"；"xuan.ide" "AI"
- "《玄》IDE v3.8.2重磅发布" "原文"；"学习智者" "玄" "csdn"
- "lyzavng/lua" "结束"；"Lua 5.4 中文版"
- "165223767"；"啊呜啊呜" "中文编程" "玄"
- site:blog.csdn.net/2301_77161129 "重复 3 次"

GitHub原生仓库搜索：lyzavng lua（0项）；xuan.ide（2项近名无已核作者互链，保持背景）。普通网页打开原仓、根页可见目录和提交链接；GitCode／Gitee公开页面的普通open多返回InternalError或Cache miss，转公开网页浏览器阅读可见内容。

## 覆盖与遗漏风险

1. Gitee/GitCode目录索引可发现低关注项目，搜索结果亦混入中文变量／API框架、AI提示词、语言教程和无关文章。此类结果保持背景。
2. V2EX、知乎与CSDN泛词查询受排序、未索引内容和多义词影响；所见结果主要为旧讨论和无关教程。平台名与日期词构成查询条件，搜索返回日期需要逐页核验。
3. Root公开标题、索引缓存和客户端页面日期各自保存。仓库登录边界、README屏蔽及超时造成原件缺口，收录状态相应保留待核。
4. 本轮采用公开网页、GitHub只读接口及公开网页浏览器进行静态研究；独立运行结果待核实。
5. 进一步核验优先等待《玄》原件与Lua中文连续程序；固定词法实现支持后续分类，独立运行结果另列。
