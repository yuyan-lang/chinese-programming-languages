# 第十六轮：Californium-252作者链与天河语言ThLang

核验日期：2026-10-10（UTC）。本组核验时段约22:01—22:09。

## 结果与计数

- 旧候选深入补证1项：Issue #24的Californium-252中文编译器视频。
- 沿旧候选作者链新发现1项：天河语言（ThLang，旧名天狐语言）。
- 建议正式新增1项：天河语言，采用中文关键字编译语言／C++—LLVM实验工具链分类。
- 旧视频候选继续待核1项；ThLang与视频的具体实现关系分别保存。
- 后续补证分为2组：旧视频候选、ThLang正式条目的剩余字段。补证分组与待核候选数分别记录。
- 飞鱼Issue #33已读第十五轮补证与最新评论。本轮保留后续核验范围，复用既有低清风险记录。

## 基线、规范和去重

本轮基线为[93815086f1778802ea57ddeeec8ad717e355814f](https://github.com/yuyan-lang/chinese-programming-languages/tree/93815086f1778802ea57ddeeec8ad717e355814f)，语言目录86项。固定研究规范已读，待核范围逐项标注。

读取86项名称、别名和相关对象，重点比较周蟒lang-014及Python中文项目。阅读第七轮B站日志与Issue #24正文／全部1条评论，第十五轮视频日志、待核文件及Issue #33正文／全部2条评论。第十五轮记录的飞鱼360P细字、CDP超时及连续原例缺口作为后续范围保留。

新项目按ThLang、Thlang、天河语言、天狐语言、tianhuzong、thzsen排重。86项目录和既有研究资料的对应项目匹配为0；百科Issue搜索ThLang及天狐返回空。新条目的发现来源为Issue #24作者链延伸，旧视频身份和新仓库身份分层记录。

## 一、Issue #24：作者跨站互链得到补足

### 原片复核

原片：[整活——自制中文编程语言编译器](https://www.bilibili.com/video/BV1bm421x7AK/)。

公开浏览器本轮读取到：

- 发布者Californium-252，作者链接指向UID3494354284972407。
- meta video:release_date为2024-04-20T10:11:27.000Z，与第七轮一致。
- 简介称自写中文编译器，并计划以后介绍原理。
- 评论区显示4条评论，读到两组鼓励性评论及作者回复；可读作者文字为致谢，技术沿革仍待核实。
- 作者投稿页显示31项视频。本轮读取的标题列表包含2024-04-20中文编译器、2024-04-13中文C++及2023-08-12汉语拼音C三条；原理续篇的明确入口待核实。

原视频已有连续原例继续采用第七轮及Issue #24记录：01:30.296两行for循环、02:08.679两行输入输出。其缩进或空格曾按可读排版整理，本轮按旧证据复用。02:43.189的compiler、函数.zh、输出55和zhpy工作目录亦保持原证据层级。

### 身份链

1. [同UID视频BV191GVzGEwU](https://www.bilibili.com/video/BV191GVzGEwU/)的简介直接给出tianhuzong/DD-web-demo仓库地址。视频作者仍为Californium-252／同一UID。
2. [GitHub个人README固定提交52feca7b](https://github.com/tianhuzong/tianhuzong/blob/52feca7bcfc158c376958c57d0708bb24559315e/README.md)自称Sen，列出GitHub tianhuzong、Gitee thzsen以及B站UID3494354284972407，并把天河语言ThLang列为作品。
3. [Gitee thzsen主页](https://gitee.com/thzsen)显示sen，简介直接列相同B站UID。两页公开仓库列表共33项，含ThLang及TinyToyCompiler。
4. 原作者GitHub仓库查询列出ThLang、TinyToyCompiler和python_compiler等。python_compiler的README自述Cython编译Python为C及可执行文件，该项目与视频compiler的实际对应待核实。

这些原作者互链支持Sen、tianhuzong、thzsen与Californium-252之间的公开账号关系。作者关系按上述公开账号互链记载。

### 与周蟒及ThLang的关系边界

视频的zhpy目录继续属于实现身份线索。周蟒gasolin/zhpy的扩展关键字机制已在既有目录记载。ThLang现有固定源码采用中文类型前置、花括号以及.th／.thlang输入；2024视频保留Python风格缩进和.zh例程。上述差异用于版本关系核对，直接继承或独立实现结论仍需原作者说明或对应源码。

Issue #24的剩余问题包括视频compiler源码、目录zhpy含义、正式语言名、版本许可、AI开发情况和与两项目的具体对应。原视频按旧候选继续保留。

## 二、新发现：天河语言ThLang

### 身份与沿革

- [原仓](https://github.com/tianhuzong/ThLang)，当前README称天河语言（Tianhe Language），工具称始皇编译器。
- 固定main提交：779844e806391ca79421378f48b2aa7de2f4f837。
- 作者／提交者日期：2026-06-21T04:22:56Z；仓库pushed_at为2026-06-21T04:28:57Z。
- 仓库创建：2023-08-13T06:18:09Z。主线提交集合返回96项，最早列2023-08-14T12:41:56Z的.gitignore提交，随后13:17:17Z增加README。
- [2023初版README](https://github.com/tianhuzong/ThLang/blob/f72dd88b0d353eb4e2cab26113deb187237e54b3/README.md)称天狐语言（Tianhu Language）、Python解释型方向。该说明按早期定位保存，早期实现可用性待核。
- [2024-03-14 README](https://github.com/tianhuzong/ThLang/blob/fd6325be8db0325fdf21dd7d0d57587d5064342f/README.md)改为C++／LLVM编译方向，仍称天狐语言。
- [2025-01-12原始改名提交](https://github.com/tianhuzong/ThLang/commit/84bf8805bbd7d8e192bb2f84da8e237a1f91efae)明确将天狐／Tianhu改为天河／Tianhe。两名称按同一仓库沿革归一。
- [作者Issue #1](https://github.com/tianhuzong/ThLang/issues/1)于2026-05-05提出重写计划；2026-06-21提交进一步调整架构目录。仓库archived=false。

### 连续中文原例

[固定bin/thlang/main.th第1—3行](https://github.com/tianhuzong/ThLang/blob/779844e806391ca79421378f48b2aa7de2f4f837/bin/thlang/main.th#L1-L3)：

```text
整数型 入口(){
    返回 0;
}
```

文件blob为84c8e1a8e1915371e29e23cfd53e4ec2df043251。三行完整连续原文，四空格缩进、半角符号逐字保留，展示时省略末尾换行。该文件历史定位到2025-06-15T13:54:10Z的567d7deab1939ff6f2b5f51c766fa118cf8d720d提交，提交说明为继续编写CLI并分离libthlang.so。

src/acli.cpp的ThInit同时保存这一模板。src/codegen.cpp第494行将中文入口名映射为main，中文函数例程与实际实现之间具有直接对应。另读bin/main.th与bin/main2.th作为语法交叉材料，正式展示选上述完整入口函数。

### 实现分类依据

静态阅读15个第一方文本文件，主要依据如下：

- src/lex.l第45—57行：且／或、如果／否则、整数型、返回、外部和Unicode标识符规则。
- src/parser.y：程序和语句结构、变量与函数声明、返回及条件分支分别构造AST节点。
- src/codegen.cpp第470—503行：返回节点调用LLVM CreateRet，函数声明创建LLVM函数并处理入口名称。
- src/TypeSystem.cpp：中文基础类型映射到LLVM整数、浮点、布尔、指针及void类型。
- src/libthlang.cpp第40—71行：compile_toir调用yyparse、root_module.codegen并输出LLVM IR。其后包含对象文件生成、LLD链接以及.th／.thlang输入处理。
- src/CMakeLists.txt：thlang共享库连接LLVM、RE-flex和LLD；compiler目标采用main.cpp。
- src/acli.cpp：提供init、info、build的源码入口，并以用户参数构建项目元数据。当前构建目标与该CLI的分发对应继续待核。

证据支持“中文关键字编译语言／C++—LLVM实验工具链”。parser中还保存for／while节点，当前词法文件的中文循环入口仍需补核，正式features采用已明确对应的中文结构。

### 当前实现与重构计划

固定递归树返回8116项，truncated=false，大量项目属于third_party。README后半的目录图和模块说明属于重构计划。实际新分层目录include/thlang/ast、frontend、sema及src对应目录中的多项文件为0字节；非空的既有词法、语法、代码生成和编译驱动仍位于src/lex.l、src/parser.y、src/codegen.cpp、src/libthlang.cpp等路径。

独立复核重取固定三行原例、README、src/lex.l、libthlang.cpp及完整树，复核原例、中文映射和LLVM／LLD入口一致，并核对README计划与实际目录边界。

### 版本、许可和AI范围

- GitHub Releases集合为空。本轮[Git refs完整集合](https://api.github.com/repos/tianhuzong/ThLang/git/refs)读取列出2个分支：main（779844e806391ca79421378f48b2aa7de2f4f837）和shared_ptr（d29a468）。编译器版本引用状态以这次完整refs读取为据。
- bin/thlang/ThlangProject.json的version=1.0.0、license=MIT属于示例包字段。src/acli.cpp显示这两个字段由用户输入，并具有1.0.0和MIT默认值。
- README称开源，GitHub license检测值为null。README计划目录图中的LICENSE为规划路径，项目级许可正文及适用范围继续待核。
- third_party保存各依赖许可证。具体依赖许可保留和编译器本体许可分别核实。
- AI工具、模型、生成比例和人工复核范围待核实。

### 同作者工具关系

[TinyToyCompiler固定README](https://github.com/tianhuzong/TinyToyCompiler/blob/e2d09969694ba940c3594e556105e3c2c18747c4/README.md)自称测试用编译器，说明用于探索ThLang开发遇到的问题，引用stardust95/TinyCompiler并标MIT。该旁支的作者关系和借鉴说明按原文记录；源码具体继承以及MIT对ThLang本体的适用范围待核。

## 检索和访问记录

公开网页检索使用Californium-252与编译器、BV1bm421x7AK、Californium-252与GitHub、飞鱼中文编程与变量四组定向词。结果主要为同名元素资料或有限标题入口；技术事实转向已确认原站与作者仓库核验。

GitHub定向仓库检索包括zhpy、Californium-252、ThzHashMap、DD-web-demo和user:tianhuzong。DD-web-demo命中原作者仓库，继而通过原片简介与个人README建立身份链。前两种同名检索用于身份定位，核素项目归入同名检索背景。

公开浏览器读取B站原片、同UID桥接视频、作者主页／投稿页、Gitee作者页及其两页公开仓库列表。普通网页读取工具对B站原片和Gitee主页返回不可访问；浏览器成功取得所需DOM和元数据。原片后续标签Runtime.evaluate超时，已取得身份与仓库证据后有限收束。公开评论存在登录提示，保存可见评论边界。

本轮研究采用普通网页、GitHub只读接口和公开浏览器。项目安装、编译、运行、测试和二进制执行保持待核。源码固定链接及短原例承担主要复核依据。

