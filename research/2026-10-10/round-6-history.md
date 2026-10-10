# 第六轮现有条目核验：习语言与入墨答

核验日期：2026-10-10。范围为原有lang-016、lang-017。先读取仓库AGENTS.md、data/languages.json、Issue #1及其五条评论。豫言条目保持原状。本轮仅静态读取网页、仓库和发布资料，资料稿交由主任务统一提交PR。

## 结果

- lang-016取得原发布账号的中文原例、C产品定位、名称沿革及发行公告。建议按作者2023年更名公告使用“细雨言”主名，保留“习语言”“曦语言”历史别名和原ID。编译器源码、真实首发日和实名仍待核实。
- lang-017取得原作者源码、正式名称、作者署名、中文规则与完整阶乘原例，改为有源码可核验的中文λ演算解释语言。

## 习语言／细雨言

### 原始来源链

1. 旧条目仅引[program-in-chinese/overview](https://github.com/program-in-chinese/overview)。README“关键词为中文的编程语言和开发环境”指向网易博客blog.163.com/xiyuyan@yeah/。
2. [xiyuyan的2016年原文](https://blog.csdn.net/xiyuyan/article/details/51894021)继续链接xiyuyan.blog.163.com的发行页；[作者专栏](https://blog.csdn.net/xiyuyan/category_926424.html)包含作品、原始时间、维护回应和与同系列工具的关系。
3. [更名公告](https://blog.csdn.net/xiyuyan/article/details/133143752)标题明确写“习语言改名了，新名字：细雨言，曾用名：曦语言”；正文确认以后使用细雨言名称。页面明确列首发2023-09-21 18:50:47、修改2023-10-18 11:25:37。
4. [细雨言4721公告](https://blog.csdn.net/xiyuyan/article/details/133143826)直接将细雨言、习语言和曦语言对应，并说明其为支持全中文编程的C语言工具；首发2023-09-21 18:52:53。

### 中文语法与原例

[作者数学求解程序](https://blog.csdn.net/xiyuyan/article/details/7340234)正文包含连续原代码，能直接确认#包含、#定义、整数类型、自然数、汉字类型、如果、步进循环、继续、返回，以及等于、大于、加加等中文表达。条目摘录清零数组的连续两行，明确依赖先前声明，保留全角标点与中文运算符。

同一程序正文还展示文章内容与代码区域，以〖和〗包围代码。算法正确性、全部中文词法和版本兼容性需要后续源码或运行验证。

### 日期与版本

- 作者专栏列2011-11-22《中文编程与习语言》，2012-03-10《一道人工无法求解的数学题的计算机求解》，2012-05-29《习佳佳1.82版介绍》，2015-09-14《精简C语言》、2016-09-09的4715-3.6版、2019-04-25的4717版。
- [旧名4721公告](https://blog.csdn.net/xiyuyan/article/details/129316614)的专栏首发时间为2023-03-03；文章正文顶部“最新推荐文章”显示2024年日期，按各自含义处理。
- [细雨言4722公告](https://blog.csdn.net/xiyuyan/article/details/135997765)标题、下载入口可读，归在作者2024年文章中。精确首发日待核实。正文“最新推荐文章于2024-11-13”属于推荐时间。
- 2008或2009起源说法出现在二手百科及历史线索中，对应初始发行材料待核实。

### 实现与同源范围

- [作者精简C说明](https://blog.csdn.net/xiyuyan/article/details/48437253)说明编译执行和中英文混写能力；实现语言、预处理层、编译器后端和工具链源码仍待核实。
- [原作者系列清单](https://blog.csdn.net/xiyuyan/article/details/7340234)区分习佳佳（中文C++）、习佳娃（中文Java）、习51（中文C51）、习丽妞（Linux中英文C）、中汇（中文汇编器）和构建（中文构建工具）。
- [习佳佳1.82介绍](https://blog.csdn.net/xiyuyan/article/details/7613927)具体说明混用习语言标准函数与C++类库。
- 作者专栏把习姐／曦姐定位为解释执行习语言或C语句的配套工具。
- xiyuyan发布账号可确认。微风／梦飞翔创作室出现在该博客读者粘贴的编译日志中，原版署名与实名仍待核实。

### 访问限制

网易博客本次无法读取。CSDN部分2009—2013年原文、栏目与原图返回Cache miss，包括4589785、5480832、7405452、20130829010554218等；已取得文字版完整数学求解程序作为主证据。宝峰科技版块目录可见xiyuyan于2011年发文，具体帖子本次不可读取。GitHub按xiyuyan、细雨言、习语言检索，与原发布账号对应的正式源码仓库链待核实；搜索结果中的其他同名项目保持独立。

## 入墨答

### 原作者与名称

经旧中国编程语言目录追到[ProjectDimlight/RuCalculus](https://github.com/ProjectDimlight/RuCalculus)。[固定README](https://github.com/ProjectDimlight/RuCalculus/blob/403e8369b93afe0da1f5c911364194117da88d5a/README.md)首行直接使用“入墨答（Rumbda Calculus）”，正文列RuCalculus、入算术、入语言同名。中文名属于原作者自命。

[Main.hs](https://github.com/ProjectDimlight/RuCalculus/blob/403e8369b93afe0da1f5c911364194117da88d5a/src/Main.hs)帮助文本按SOL、AntonPing、许兴逸顺序署名；提交记录与此相符。

### 固定证据

- 核验提交：403e8369b93afe0da1f5c911364194117da88d5a，2023-06-20T19:20:49Z。
- 递归树35项，truncated=false，包含README、语法手册、教程、中文库和示例、Haskell源文件。
- [中文解析器](https://github.com/ProjectDimlight/RuCalculus/blob/403e8369b93afe0da1f5c911364194117da88d5a/src/MonadicParse.hs)明确解析入、以、为、则／并、令、时、否则、引等句式。条件表达与递归绑定展开为AST。
- [阶乘原例](https://github.com/ProjectDimlight/RuCalculus/blob/403e8369b93afe0da1f5c911364194117da88d5a/samples/%E9%98%B6%E4%B9%98.%E5%85%A5)全文连续六行（含空行），已逐字采用。
- [语法手册](https://github.com/ProjectDimlight/RuCalculus/blob/403e8369b93afe0da1f5c911364194117da88d5a/doc/Manual.md)区分函数应用、名称绑定、中文条件、中文字符串，以及Haskell宿主函数与入语言库。
- [闭包解释器](https://github.com/ProjectDimlight/RuCalculus/blob/403e8369b93afe0da1f5c911364194117da88d5a/src/Interp.hs)处理环境、函数闭包、宿主函数和文件引入；[HostFuncs.hs](https://github.com/ProjectDimlight/RuCalculus/blob/403e8369b93afe0da1f5c911364194117da88d5a/src/HostFuncs.hs)实现基本算术、比较、布尔与输出。
- [Cabal](https://github.com/ProjectDimlight/RuCalculus/blob/403e8369b93afe0da1f5c911364194117da88d5a/RuCalculus.cabal)给出0.1.0.0、Haskell2010、Parsec等依赖。LICENSE为Apache-2.0。
- 根提交c53679dda0d1f7edc896b3a994f6d04d5875c64b为2022-05-15T13:15:09Z，parents字段为空数组，README已含RuCalculus／入算术。仓库创建时间与根提交时间分开记录。公开可见的首次时间仍待原始公告确认。
- GitHub仓库归档字段archived=false，pushed_at为2023-06-20T19:20:49Z；updated_at按平台元数据记录，代码维护情况依据提交历史核实。Releases响应为空数组。

### 核验边界

原始材料确认Haskell宿主函数机制。二手目录“可与Haskell混编、正在兼容F#”的范围及实现尚待核实。当前公开实现以Haskell源码为主；F#互操作的具体实现与支持范围待核实。README的-d逐步演算说明对应当前Main.hs中已解析的debug标志，其实际运行路径效果待核实。源码中存在TypeChecker模块，当前入口的类型检查流程继续待核实。

### 原有PDF

[国产编程语言蓝皮书2023](https://www.ploc.org.cn/ploc/CNPL-2023.pdf)的搜索索引将涉及入墨答的文字定位到印刷页43/46。官网HTTPS、HTTP及无www版本均未取得可用PDF正文；截图请求因未取得PDF响应失败。官方GitHub文档另指向Gitee CNPL-2023工作区，本次也未读到。原有引用保留，页码作为后续定位线索，截图复核状态为待核实；本轮事实依据全部采用原作者仓库。

## 后续缺口

1. 细雨言：原始编译器源码或可核验发行包、开发者署名、最早首发证据、4722精确发布日期及当前最新版本。
2. 入墨答：首次公开公告、正式发行物、跨语言互操作范围、当前维护计划及独立执行结果。
3. 蓝皮书相关页截图仍待可用PDF来源。

## 实际检索范围与遗漏风险

### 搜索关键词

- 习语言网页检索实际使用：“习语言” 编程 作者、“习语言” “习佳佳”、“习语言” “源码”、“习语言” “如果”、“习语言” “关键字”、“xiyuyan” “微风”、“xiyuyan” “2009” “整数类型”、“习语言 例子（一）”，以及site:blog.csdn.net/xiyuyan搭配“习语言”“曦语言”“语言”“整数”。
- 入墨答网页检索实际使用：“入墨答” 编程、“入墨答” 语言 GitHub、“入墨答” SOL。
- 文献检索实际使用：“CNPL-2023.pdf”及“CNPL-2023.pdf” filetype:pdf；GitHub代码搜索使用CNPL-2023.pdf。
- GitHub仓库搜索实际使用：xiyuyan、细雨言、习语言。原作者仓库通过中国编程语言目录中的具体链接追踪，随后读取默认分支、完整目录树、提交列表及固定文件。
- 沿已取得页面的作者栏目、原文链接、上下一篇和发行公告继续追溯；搜索语句与直接链接读取均采用静态资料方式。

### 历史时间范围

习语言沿2008／2009起源线索向后追踪，主要可核验记录覆盖2011—2024年；精确首发仍待原始发行材料。入墨答提交历史覆盖2022-05-15至2023-06-20，版本和正文固定在2023-06-20提交。检索于2026-10-10进行，网页搜索采用全时间范围，检索日与网页缓存时间分别记录。

### 遗漏风险

公开索引、作者当前栏目及默认分支构成本轮主要覆盖范围。网易博客早期资料、网盘发行物、已删除页面、独立分支及公开索引更新延迟均可能影响历史完整性。CSDN推荐时间、首发时间和修改时间需要按字段辨别；本轮已在可读专栏交叉核对关键日期。源码静态阅读、作者运行自述和独立执行验证按各自证据范围记录，安装包可用性、版本兼容性及运行效果继续待核实。
