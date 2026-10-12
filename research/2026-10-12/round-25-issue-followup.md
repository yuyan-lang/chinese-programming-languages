# 第25轮：旧议题补证与博流候选

核验日期：2026-10-12，12:32—12:40 UTC。百科基线a857fa023fd66e44963378c91d04642bf9817421，95项语言、10项内核。已读根AGENTS.md、目录、最近研究日志、全部27个开放议题正文与当前PR列表；本轮涉及的Issue3、16、40评论另逐项读取。PR58的Pages部署38249250068于本轮核对为success。

本轮正式新增0项、已有正式条目修改0项。新发现待核线索1项：博流；旧线索完成范围分类1项：Sneko；旧候选补证2项：SPCNYY、Lua5.4中文版。独立运行0项。现有95／10目录保持原样。

## Sneko：文档层面范围分类

[原仓README](https://github.com/ShineNeko-meow/Sneko-Lang/blob/eb03bcebac4ad6b4dcfffb1c9b2789c57727c293/README.md#L5-L30)明示中文拼音关键字shu、chu、ruo，当前按拼音关键字工具保存范围外研究记录。[完整树](https://api.github.com/repos/ShineNeko-meow/Sneko-Lang/git/trees/eb03bcebac4ad6b4dcfffb1c9b2789c57727c293?recursive=1)为README.md与SnekoEditor.exe，truncated=false。[保留提交](https://api.github.com/repos/ShineNeko-meow/Sneko-Lang/commits?per_page=100)共三项，根ac7b24302a33d947188702ab060004fb686f02e1、上传43c0f08038608e1765e255af0c8a1a55c6f9b556、当前eb03bcebac4ad6b4dcfffb1c9b2789c57727c293。

建库2026-09-18T11:02:17Z；根提交2026-09-18T13:55:29Z；当前提交2026-09-18T13:59:33Z。提交署名ShineNeko-meow。README自标0.1.0和MIT，实际许可正文、词法解析实现、汉字扩展与首次公开待核。二进制执行0次。关联sneko-lang/sneko公开接口404；sneko.dev及/docs、/play通过网页工具未能读取。后续取得作者汉字程序及规范／实现后重新评估。

[Issue3结果](https://github.com/yuyan-lang/chinese-programming-languages/issues/3#issuecomment-6124390012)：累计13/19组完成收录或范围分类，余CN_Interpreter、PYCH、RexLang、青语言、意语言、衍真6组；议题保持开放。13项是处理分类数。

## SPCNYY：原例缺口与实现语义

固定2d9087cade68fff2c966a7bf057141935b439ec0。[翻译模块L289—311](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh#L289-L311)对整段文本按映射键长度降序str.replace，继而进行计次循环正则转换。[运行入口L600—618](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh#L600-L618)调用Python exec；字符串、注释及标识符内的匹配内容均参与替换。

初始化L355调用_new_file；[L563—578](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh#L563-L578)说明新建清空缓冲区、打开读取外部.spc。当前完整树四文件和两次提交的静态核验仍留下作者连续中文程序缺口。Linux与Windows脚本七个内嵌Python模块正文逐段相同；Shell生成结果、打包与运行待核。DeepSeek问答／纠错按配套功能保存，AI开发参与待核。

根提交2b99fb85eaf91284d5d0bd0aa047772db41dd75c时间2026-08-15T16:43:42Z；源码加入时间2026-08-15T16:46:47Z。许可、正式版本和首次公开待核。[Issue16补证](https://github.com/yuyan-lang/chinese-programming-languages/issues/16#issuecomment-6124399150)，议题继续开放。

## Lua5.4中文版：解析与虚拟机资料

lyzavng/lua固定c0e0b83f7bd323bac7e0326886652075d85d55db。原词法器的22项中文与22项英文词设置相同语法词元。本轮取得以下固定公开源码正文：

- [lparser.c](https://gitee.com/lyzavng/lua/blob/c0e0b83f7bd323bac7e0326886652075d85d55db/src/lparser.c)：L1875—1945语句分派，L1954—1996建立闭包与Proto并解析语句。
- [ldo.c](https://gitee.com/lyzavng/lua/blob/c0e0b83f7bd323bac7e0326886652075d85d55db/src/ldo.c)：L789—816选择反序列化或源码解析，L458—504进入luaV_execute。
- [lua.c](https://gitee.com/lyzavng/lua/blob/c0e0b83f7bd323bac7e0326886652075d85d55db/src/lua.c)：L226—236加载文件并调用docall，L138—145通过lua_pcall执行。
- [lvm.c](https://gitee.com/lyzavng/lua/blob/c0e0b83f7bd323bac7e0326886652075d85d55db/src/lvm.c)：L1134—1165虚拟机取指分派；另含OP_CALL、OP_RETURN、OP_FORLOOP、OP_FORPREP分支。
- [lua.h](https://gitee.com/lyzavng/lua/blob/c0e0b83f7bd323bac7e0326886652075d85d55db/src/lua.h)：L19—29版本5.4.0，L493—514保存MIT式许可及1994—2020 Lua.org, PUC-Rio版权。

上述材料支持Lua5.4派生中英双语词法前端、Lua解析与字节码VM结构。库接口逐函数串联、中文库覆盖和完整上游差异待核。

公开时间提示：[固定根页](https://gitee.com/lyzavng/lua/tree/c0e0b83f7bd323bac7e0326886652075d85d55db)头提交2020-08-10 17:06:36 +0800；lparser.c／lua.h关联fa00ad33fff1456094dac9865dabe487e470dd4a为2020-08-10 16:43 +08:00；[doc目录](https://gitee.com/lyzavng/lua/tree/c0e0b83f7bd323bac7e0326886652075d85d55db/doc)关联29e016a33a3811c41483d35ded8151e1166fca77为2020-05-23 19:57:51 +0800。页面时间的作者／提交者语义及首发日期待核。doc/readme.html旧5.4.0-beta资料与源码5.4.0分别记录。源码上游MIT、文档1994—2019 MIT、根页MulanPSL-2.0声明分层保存，中文贡献授权范围待核。

[xgongya/cnLua](https://github.com/xgongya/cnLua/blob/90a2926c5a09208e5ef6455453c0cd5f4edf4c31/README)为LuaJIT2.0.5基线，中文词表及test2.lua保留其自身来源；与lyzavng的继承关系待核。OldDragon明确Fork关系归并。言序lang-007另按其固定Rust资料保存。

lyzavng连续中文原例仍待核，候选继续保留在[Issue40](https://github.com/yuyan-lang/chinese-programming-languages/issues/40)。原README平台屏蔽、manual.html跳转登录后停止对应读取，其余公开源码静态核验完成。

## 博流：新增待核线索

[公司原始介绍](https://www.gdchenyi.com.cn/col.jsp?id=133)“2018 厚积薄发”栏目列发布博流中文编程语言，记录为广东辰宜信息科技有限公司发布自述。中文程序、语法、实现、独立语言／DSL／平台分类、版本和许可待核。[Issue59](https://github.com/yuyan-lang/chinese-programming-languages/issues/59)保存入口及检查项。公司关联可信云操作系统的自身内核关系另待核。官网文章14及251的正文读取失败，索引用于定位。

## 检索范围与遗漏

GitHub／Gitee原仓、公司官网、B站与普通网页搜索。关键词：Sneko-Lang ShineNeko、Sneko shu ruo、SPCNYY、spcnyy 打印、xs-smz 编程、lyzavng/lua、Lua5.4中文版、果真 函数 2020、CNlua、言序、博流中文编程 官方 语言、博流 编程 github、博流中文编程 如果、博流 编程语言 语法。

补充发现检索：site.bilibili.com/video 中文编程语言 2026 自制；site.bilibili.com/video 中文编程 2025 AI 语言。检索重点2024—2026，历史沿革追至2018—2020。B站结果包含教程和评论等混杂内容，原作者程序与技术资料逐项核验。百科“博流”代码搜索0项、incomplete_results=false；现有95条目和开放议题同步排重。未索引文档、图片内代码、小程序、历史页面、受限访问和搜索排序均可能造成遗漏。

本轮安装、构建、候选程序执行、测试和第三方联系均为0。研究结果按静态源码、作者说明、范围分类及待核字段保存。
