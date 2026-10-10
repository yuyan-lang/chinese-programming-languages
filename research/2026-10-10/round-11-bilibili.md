# 第十一轮 Bilibili 旧标题入口补证

- 核验时间：2026-10-10，约19:29—19:36 UTC。
- 百科基线：yuyan-lang/chinese-programming-languages，固定提交b8bced915e093ccdfde6b32804f7bd2b4c6a0786，语言目录71项。
- 已读根AGENTS.md、完整data/languages.json及第十轮B站日志／待核文件，读取当前18个开放Issue正文并按名称、别名、作者UID、BV和源码路径排重。
- 深入范围为2组第十轮标题入口：白易VC++、壬通中文C++。
- 统计口径：新发现0组，旧标题入口补证2组，正式语言新增0项，待核语言候选1项；另确认中文C++开发工具资料1组。已收录语言补写0项。相同项目的多个视频和官方文档按一组计数。
- 交付：round11-bili-entry.json为空数组；round-11-bilibili-pending.json含壬通1项；本日志含白易工具分类核验。round11-bili-evidence保存5份静态源码文本及来源清单。
- 操作范围：普通网页、GitHub只读连接器与公开网页浏览器。项目代码、安装器、构建脚本和发行物执行数为0。仓库写入数为0。文件写入限定于本轮研究交付。

## 一、白易VC++：中文C++插件与支持库的分类已核

### 作者、原片和时间

原发布者为小白菜软件，B站UID173028284。已打开原片：

1. [02 安装VS与白易插件](https://www.bilibili.com/video/BV1dEVU6hEa9/)：video:release_date为2026-05-31T13:18:34.000Z，时长329秒。初始原站页面显示2026-05-31 21:18:34。
2. [01 Visual Studio拼音补全 中文C++编程插件](https://www.bilibili.com/video/BV1dEVU6hEcK/)：video:release_date为2026-05-31T13:18:52.000Z，时长1282秒。初始原站页面显示2026-05-31 21:18:52。合集中的标题保留“白易语言”措辞，当前原片标题描述为插件。
3. [白易C++中文窗口编程+deepseekV4flash演示开发小项目](https://www.bilibili.com/video/BV1zN7j6RERz/)在原作者推荐列表出现；本轮把它作为AI辅助开发关系入口，其正文、日期和原片画面继续待核实。

视频简介直接给出[白易VC++帮助文档](https://wiki.xbcsoft.com/BEVCpp/)。文档又直接链接官方源码库，形成B站→官网→GitHub的公开身份链。

[小白菜软件官网“白易VC++插件”文章](https://xbcsoft.com/archives/bevcpp.html)显示作者admin、文章时间2026-05-26，是本轮确认的较早公开材料。项目最早首发时间继续待核实。官网文章时间、B站投稿时间与GitHub建库时间分别记录。

### 官方定位和版本

官方简介定位为Visual Studio上的可视化中文C++窗口编程插件，提供拼音补全、窗口表、程序集、资源表、模块表，以及MCP接口对接AI编程工具。当前简介列BE0.8.5.zip，更新日志首节为V0.8.5，文档说明VS2017／VS2019及C++17要求。官网当前更新日志未显示各版本日期，0.8.5的独立发布日期待核实。

[快速入门编写白易模块](https://wiki.xbcsoft.com/BEVCpp/?file=%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8%E7%BC%96%E5%86%99%E7%99%BD%E6%98%93%E6%A8%A1%E5%9D%97.html)说明，插件建立stdafx.h、BEMod/BEMod.h及BE.props，引入模块的C++头文件和源文件作为VC工程编译单元。项目打包和模块管理属于已核实的官方文档定位；实际运行和兼容性继续待核实。

[更新日志](https://wiki.xbcsoft.com/BEVCpp/?file=%E6%9B%B4%E6%96%B0%E6%97%A5%E5%BF%97.html)列MSBuild构建、C++模块、Win32与Sciter界面组件，以及AI提示和MCP接口变化。AI证据指向辅助开发功能。核心代码的AI生成范围继续待核实。

### 固定源码与实际语法

[官方基础库xbcsoft/BE-BaseLibrary](https://github.com/xbcsoft/BE-BaseLibrary)公开可读，GitHub属性fork=false、archived=false，创建时间2026-06-27T08:53:16Z，pushed_at为2026-08-30T09:10:12Z。

固定提交f1590462f0d7e2563bf0b8f32203cb4f6ff5cef5，committer时间2026-08-30T09:10:02Z，author时间2026-08-29T15:28:07Z，提交说明为0.7.1。完整递归目录树truncated=false。官方文档的0.8.5与所读仓库0.7.1快照分别保存。仓库元数据license=null；完整许可范围待核实。

已实读的文件包括：

- [README](https://github.com/xbcsoft/BE-BaseLibrary/blob/f1590462f0d7e2563bf0b8f32203cb4f6ff5cef5/README.md)：解释模块与基础库范围，说明bin2Lib.exe的私有发行状态。
- [BECore.h](https://github.com/xbcsoft/BE-BaseLibrary/blob/f1590462f0d7e2563bf0b8f32203cb4f6ff5cef5/BEModSrc/BECore/BECore/BECore.h)：声明作者xbcsoft、核心版本0.7、编译器msvc141；引入中文核心及中文扩展头文件。
- [中文核心.hpp](https://github.com/xbcsoft/BE-BaseLibrary/blob/f1590462f0d7e2563bf0b8f32203cb4f6ff5cef5/BEModSrc/BECore/BECore/%E4%B8%AD%E6%96%87%E6%A0%B8%E5%BF%83.hpp)：第4—20行使用C++ using和模板类型别名，第121—123行引出中文输出API宏；第142—149行为定义_枚举型宏。
- [behelper.hpp](https://github.com/xbcsoft/BE-BaseLibrary/blob/f1590462f0d7e2563bf0b8f32203cb4f6ff5cef5/BEModSrc/BECore/BECore/behelper.hpp)：第38—41行multiassign由do／while和C++折叠表达式实现；第62—67行multichoose展开为lambda与switch；第70行choose采用三元运算。
- [数组操作原例](https://github.com/xbcsoft/BE-BaseLibrary/blob/f1590462f0d7e2563bf0b8f32203cb4f6ff5cef5/BEModExamples/BECore/%E6%95%B0%E7%BB%84%E6%93%8D%E4%BD%9C/main.cpp)：中文数组接口与C++英文流程关键字并用。
- [分割文本原例](https://github.com/xbcsoft/BE-BaseLibrary/blob/f1590462f0d7e2563bf0b8f32203cb4f6ff5cef5/BEModExamples/BECore/%E5%88%86%E5%89%B2%E6%96%87%E6%9C%AC%E6%A1%88%E4%BE%8B/main.cpp)：展示英文／中文API及for、if、break、return。
- 仓库的BECore轻量参考文档：定义UTF-8约定、中文类型别名、普通C++函数调用、模板和英文流程结构；本轮作为项目文档数据阅读。

中文核心.hpp第5—12行连续原文：

```cpp
using 字节集 = Bytes;
using 文本型 = StrA; using 文本型W = StrW; using 宽文型 = StrW;
using 文本型U8 = StrU8; using 通用文本 = AutoStr;
using 文本型X = StrX; using 文本平台型 = StrPlat;
using 整数型 = int; using 整型 = int; using 无符整型 = uint;
using 字节型 = byte; using 字符型 = char; using 宽字型 = charW;
using 短整数型 = short; using 短整型 = short; using 无符短整 = ushort;
using 长整数型 = int64; using 长整型 = int64; using 无符长整 = uint64;
```

数组操作main.cpp第14—19行连续原文，保留代码和注释，缩进显示为制表符：

```cpp
	数组<int> arr1;

	// 测试加入成员
	加入成员(arr1, 10);
	加入成员(arr1, 20);
	加入成员(arr1, 30);
```

原例第87—93行用for和if遍历，末尾入口用int main与return。来源文件及原始Git blob SHA见证据清单；本地证据仅统一行尾。

### 分类结论与资料缺口

本轮将白易登记为“中文API／类型别名C++支持库与Visual Studio开发插件”工具资料，正式中文语法语言目录增量为0。

已核实范围包括中文类型名、中文函数、中文宏、模块封装和IDE自动化。定义_枚举型、选择、连续赋值等辅助宏体现C++库级扩展；项目级中文语法规范、连续汉字控制结构原例以及插件核心的潜在中文关键字处理机制继续待核实。若后续取得这类材料，可重新评估中文语法或宏DSL分类。

本轮语法证据使用静态源码。白易两支原片的作者、正文、日期与时长已核验，代码时间点逐帧补证保持待核。

## 二、壬通中文C++：原BV和录像已补，连续原例待核

### 身份与日期

[壬通中文C++编程](https://www.bilibili.com/video/BV1DaBaBNEE9/)由[沉默夏戌UID264330594](https://space.bilibili.com/264330594/)发布，原账号资料列壬通中文编程交流信息。

原片meta确认：

- video:release_date：2025-12-26T04:42:01.000Z
- video:duration：652秒，即10:52
- author：沉默夏戌

原站初始文本为2025-12-26 12:42:01；客户端后续显示2025-12-25 20:42:01。发布日期按明确UTC元数据记录，北京时间为2025-12-26 12:42:01。搜索卡片显示的2025-12-25属于另一页面显示结果。

发布者身份已核。实现作者身份、最早公开日、版本和许可证继续待核实。

### 视频时间点与公开评论

通过播放器时间输入和页面全屏观察以下片段：

- 01:00：公开交流信息页面。
- 03:03：Windows虚拟机内的安装进度界面。
- 07:01附近：开发环境创建工程及选取文件夹界面。
- 09:01：编辑器打开.cpp文件，源区域有中文代码、花括号及流插入运算符，下方控制台显示程序输出。页面HTML video.currentTime为540.448926，UI显示09:01。

09:01帧的汉字代码支持继续核验中文C++映射环境的候选方向。精确关键字、库名、字符串、标点与完整连续程序的逐字转录仍待核实，pending的code字段保留空字符串。

公开评论中，发布者在比较火山PC的回复里说明保留原生语法的定位。该说明以作者自述保存。源码继承关系、翻译层边界及后端编译器继续待核实。同账号还有火山和鸿蒙教程，投稿主题作为作者背景单列。

### 来源和访问边界

原片简介提供的静态信息较少。普通网页精确检索和GitHub名称检索已完成，直接关联的官方语法文档、关键字映射表和核心源码入口继续待核实。搜索结果中的同名命理项目作为无关结果跳过。

播放器画质菜单显示360P流畅可公开播放，480P、720P、1080P均标“登录即享”。公开video尺寸为640×360。代码字号加上画质限制使完整逐字核验留有缺口。原片曾自动弹出登录提示，关闭后继续阅读公开层。高清登录与18条评论的完整内容均保持待核实。

页面曾出现Page.getLayoutMetrics、Runtime.evaluate、DOMSnapshot.captureSnapshot超时。同一公开网页浏览器有限新页恢复后取得09:01代码与控制台画面，后续页面再次超时后收束视频核验。

本轮将壬通保留为待核候选1项。下一步优先取得公开静态原例或清晰代码图，再核对.cpp保存内容、关键字映射、构建调用、作者关系与版本许可。

## 三、检索覆盖与遗漏风险

### 实际关键词与平台

普通网页搜索共9个查询：

1. “白易” “VC++”
2. “壬通” “中文” “C++”
3. “白易VC” 编程
4. “壬通” 编程
5. “壬通中文编程”
6. “壬通” “C++” Github
7. “壬通中文” 编程 下载
8. “沉默夏戌” C++ 壬通
9. “壬通中文C++”

B站站内搜索2个查询，读取综合排序第一页：白易VC++、壬通中文C++。由结果直接进入原片、原作者相关视频及官方文档。

GitHub仓库搜索4个查询：壬通；“壬通中文” in:name,description,readme；“白易” in:name,description,readme；“壬通中文” in:name,description。末项返回0仓库；泛化查询含大量无关结果。白易源码采用官方文档直链确定。

GitHub另读取百科AGENTS.md、71项完整语言JSON、18个开放Issue正文，按名称、别名、UID、BV和xbcsoft路径匹配；匹配既有语言0项、开放Issue0项。本地既有日志仅第十轮含两个名称的标题级提醒，既有资料的本次三个BV／两个UID／xbcsoft链接匹配0项。

### 时间窗与排重

优先时间窗为2024—2026，按结果日期人工核对；搜索未施加硬日期过滤。本轮两组有效原始资料分别集中在2026年白易、2025年壬通。第十轮已收录的云易以及飞鱼Issue33作为排重背景，深入增量保持0。如意、唐姝和既有豫言项目均按授权范围跳过。

白易官网普通网页工具读取失败，公开网页浏览器可直接读取。普通搜索引擎对精确中文名称经常泛化成C++教程、汉字输入法和同名词条，B站站内查询召回较有效。

本轮覆盖两组已有标题入口，B站结果仅综合第一页，作者投稿列表、站内翻页和需要登录的高清／评论层待扩充。低播放量未索引视频、标题缺少项目名、中文标识符工具和映射语言之间的命名混用、搜索结果时区差异均构成遗漏或误分类风险。

## 四、本轮计数摘要

- 全新发现：0组
- 既有标题入口深入补证：2组
- 正式语言新增：0项
- 已有正式语言补写：0项
- 待核语言候选：1项，壬通中文C++编程
- 工具分类已核资料：1组，白易VC++
- 项目执行／构建／安装：0次
- 外部写入：0次

