# 第14轮：墨香中文编程（MxIDE）核验

核验时间：2026-10-10 21:02:58—21:08 UTC。
工具范围：公开网页浏览器公开网页、公开网页搜索、GitHub 只读连接器、公开资料核对记录。

## 结论
建议正式收录“墨香中文编程（MxIDE）”，分类为“中文 JavaScript 语法方案与转换配置／AI 辅助开发环境”。
资格依据为原作者固定提交中的连续中文条件分支、中文流程指令及对应 JavaScript 模板。
实现内部、运行结果、正式版本与许可继续标为待核实。

## 排重与仓库规范
- 已通过 GitHub fetch_file 读取百科主分支固定提交 46734fc65a9a5da4cdc230c78c9f835134973e9a 的 AGENTS.md、README.md。公开写作采用肯定陈述，资料缺口明确标记。
- 已读取77项语言的名称、别名及全文并匹配“墨香”“Mxide”“liuyunsishui”；匹配结果为空。
- 已搜索同一审计的议题及评论正文；匹配结果为空。公开轮次总览采用本轮核实的23条开放议题、60条议题评论、0 PR。
- 已以 GitHub search_issues 对 yuyan-lang/chinese-programming-languages 搜索“墨香”，返回空结果。
- 历轮研究日志的“墨香”“Mxide”全文检索结果为空。
- “墨言”按另一名称保留；两者关系待作者来源确认。

规范固定源：
https://github.com/yuyan-lang/chinese-programming-languages/blob/46734fc65a9a5da4cdc230c78c9f835134973e9a/AGENTS.md
https://github.com/yuyan-lang/chinese-programming-languages/blob/46734fc65a9a5da4cdc230c78c9f835134973e9a/README.md

## 搜索词与发现路径
公开搜索词：
1. "墨香中文编程"
2. "墨香中文编程" "CMS"
3. "墨香中文编程" site:bilibili.com
4. "Mxide" "墨香"
5. B站站内搜索：墨香中文编程
6. GitHub百科议题：墨香

种子与检索页：
https://gitee.com/liuyunsishui/projects
https://search.bilibili.com/all?keyword=%E7%BC%96%E7%A8%8B%E8%AE%BA%E5%9D%9B
https://search.bilibili.com/all?keyword=%E5%A2%A8%E9%A6%99%E4%B8%AD%E6%96%87%E7%BC%96%E7%A8%8B

作者projects实际链接明确指向：
https://gitee.com/liuyunsishui/Mxide

## 逐项证据
### 21:03 作者主页与仓库
- projects页显示维护账号 Smile_Admin（liuyunsishui），公开仓库1个。
- 仓库首页明确显示1 Stars、2 Watching、0 Forks、16次提交。按2026-10-10观测快照记录；早先种子数字次序已校正。
- master首页最新提交显示804962bbe027da7386e7c553dd49fa2d23cd13d2，标题为更新MxIDE_Mx_AI/网站服务操作库.txt。
- 首页可见README、demo/墨香中文JavaScript、基础中文命令库、MxIDE_Mx_AI、MxIDEServerAI、MxIDE_Vant4_AI与55IDE_Server目录。
- 首页时间元素title明确给出最新提交2025-05-28 01:47:39 +0000。相对“1年前”按提示原文保存，不折算发布日期。

### 21:04—21:06 原作者中文语法和例程
连续例程固定链接：
https://gitee.com/liuyunsishui/Mxide/blob/4923c5cb6ae321d2bad9d2a2973860907fe63043/demo/%E5%A2%A8%E9%A6%99%E4%B8%AD%E6%96%87JavaScript/1%E5%9F%BA%E7%A1%80%E6%A8%A1%E6%9D%BF%E6%9C%8D%E5%8A%A1%E7%AB%AF.txt#L34-L42

- 正常公开blob页面成功显示固定提交4923c5c和91行例程。
- 文件页作者为Smile_Admin，提交标题“基础语法0.1”，时间title为2025-05-22 02:47 +08:00。
- 第34—42行连续包含“如果(数据 == null)”、对象赋值、中文内存API、“调试输出”“否则”“如果结束”。
- 第45—54行包含中文计次循环与共享内存修改。
- 前文以“网站服务器”“共享内存对象”定义变量，并按世界初始化、世界核心更新、用户进入／离开、用户网页消息／网络消息组织事件。
- 原文件使用U+0001、U+0002、U+0004等控制字符和数字结构码。正式code字段取第34—42行，保留U+0001，以JSON标准转义保存。网页显示时可保留控制字符；如要以␁可见替身表示，须明确声明展示替换。

流程操作库固定链接：
https://gitee.com/liuyunsishui/Mxide/blob/d139b0dae46b2dda0febaafc2e589e1ee70c91db/MxIDE_Mx_AI/%E6%B5%81%E7%A8%8B%E6%93%8D%E4%BD%9C%E5%BA%93.txt

- 固定公开页面正常显示。
- 中文命令表配对如果与if(%s){，判断循环首与while(%s){，计次循环首与for模板，返回与return(%s)，调试输出与console.log(%s)。
- 文档规定代码块结构标记、单行参数和事件接口布局，另有Vue响应式对象和组件示例。
- master文件页时间title为2025-05-22 02:37 +08:00。
- 文档映射及例程支持中文语法前端归类；转换器、解析器与运行时源码继续待核。

README固定链接：
https://gitee.com/liuyunsishui/Mxide/blob/1aa3ca7a1fd3fab469f17beeb5d8defa19e5c381/README.md

- 固定公开页面正常显示“mxide”、项目中文编程目标与www.mxide.com。
- 主要文档介绍JSON、WebSocket、流程、数组、网站服务、文本和转换库。
- 作者列出事件驱动、对象设计、特殊代码块格式及网站／游戏服务端用途。
- 这些范围按作者文档陈述记录。

基础命令库：
https://gitee.com/liuyunsishui/Mxide/blob/master/%E5%A2%A8%E9%A6%99%E4%B8%AD%E6%96%87%E5%9F%BA%E7%A1%80%E4%B8%AD%E6%96%87%E5%91%BD%E4%BB%A4%E5%BA%93.txt

- 正常网页显示1420行文档，可见CSS属性、Vue.ref、v-if、v-for等原生项对应中文接口。
- 只采用公开可见文本，按master动态来源记录。

### 21:04与21:06 B站原页
CMS教程：
https://www.bilibili.com/video/BV1wtj6z5E8n/
- 标题“墨香中文编程零基础开发CMS网站”。
- UP独游墨客，UID395604335。
- 原页显示2025-05-29 05:11:49；搜索页显示5月28日，优先原页并保留时区待核实。
- 简介写Vue3和Element Plus，构建注册、登录、文章发布／管理与会员浏览CMS。
- 合集“墨香中文零基础开发网站”含18项，提供开发环境、组件、CSS、Vue布局、MYSQL及HTTP等章节。
- 仅核验标题、简介和页面元数据，视频画面代码与运行效果待核实。

近期游戏服务端教程：
https://www.bilibili.com/video/BV17QK261EK8/
- 标题“8.墨香中文游戏服务端SKILLS全自动开发”。
- 原页显示2026-07-20 10:34:38；时区待核实。
- 同一UP，简介自述服务端自动化skills与编译测试、AI修正。
- 该页证明2026年仍有同名教程发布。仓库当前实现与视频版本对应待核实。

UP公开主页：
https://space.bilibili.com/395604335/
- 主页链接由原视频页取得。
- Gitee账号与UP的同一人身份关系待明确互链。

## 访问风险与边界
- 官网http://www.mxide.com在浏览器正常导航后转为https://www.mxide.com/，显示502及“Certificate verify failed: unable to get local issuer certificate”。在错误页止步。当前可用性待核实。
- Gitee提交详情https://gitee.com/liuyunsishui/Mxide/commit/4923c5cb6ae321d2bad9d2a2973860907fe63043跳转登录。保留该访问结果；固定blob页面独立正常公开展示。
- 仓库首页提示LICENSE文件缺失；公开可读和开源许可分别记录。
- 本次采用公开网页正文、DOM公开title属性、固定链接和短原文摘录。操作范围为只读研究。
- 后续若干浏览器元数据读取超时；结论采用超时前成功读取并确认的原始结果。
- 最早公开日、正式版本、转换器实现、独立运行、跨平台作者身份、AI分工、与墨言／55IDE关系保留待核字段。


## 固定源短摘录与展示说明

例程第34—42行按固定文件逐行核对。下方为人读展示，U+0001使用可见符号␁标识，其余字符和空行保持原顺序：

```text
␁!!如果(数据 == null)
数据 = {}
数据.生命 = 100
数据.名称 = '流云思水'
内存.添加数据(#网站_内存分类_怪物, '全局', 数据)
调试输出(数据)
␁##否则

␁""如果结束
```

流程操作库同一固定提交 d139b0dae46b2dda0febaafc2e589e1ee70c91db 的映射原文短摘录（U+0001同样显示为␁）：

```text
|if(%s){|␁!!如果()||面向过程|if 条件判断|
|while(%s){|␁!!判断循环首()||面向过程|while 当满足条件时候退出 如果不退出将永远循环可能导致程序崩溃|
| for (let j001 = 0; j001 < %s; j001++){|␁!!计次循环首(10,i)||面向过程|for 循环指定次数|
|console.log(%s)|调试输出()||面向过程|支持连续输出多参数|
```

映射摘录由已读取公开网页正文取得。后续对固定流程库的精确行号回读连续超时；该摘录保留文件级固定引用，行号待核实。例程的第34—42行已直接从固定页面pre源文本逐行计数核验。

