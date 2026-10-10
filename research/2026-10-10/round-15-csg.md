# 第十五轮新发现：csg 中文 C# 翻译层

核验日期：2026-10-10；研究窗口21:30—21:35 UTC。百科基线为 [757ddd0d875cb114b7261e389aa9a8a002f86c80](https://github.com/yuyan-lang/chinese-programming-languages/tree/757ddd0d875cb114b7261e389aa9a8a002f86c80)，语言目录80项。

## 结果

本组真正新发现1项，建议正式收录1项：**csg**，作者展开名为 **Chinese programming language by SourceGenerator**。分类为“C# 中文关键字翻译层／Source Generator 教学实验”。本组新增待分类候选0项；该正式条目的后续字段另列 pending。

固定原仓包含可完整读出的六项关键字文本映射、从 .csg 到 C# 的实际生成入口、配套中文输出 API、宿主配置和连续中文用户程序。教学性与代码规模按项目定位记录，正式条目可依据这些原始证据独立成立。

核验方法为公开网页与 GitHub 接口只读查阅、源码静态阅读及研究文件整理。项目构建、测试和独立执行结果待核实。

## 开轮及去重

已读取根 [AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/757ddd0d875cb114b7261e389aa9a8a002f86c80/AGENTS.md)、80项完整 languages.json、第十四轮总览、发现日志及搜索日志。公开写作采用直接事实陈述，资料缺口标“待核实”。

当轮开放 Issue 共24项，编号为1、3、4、5、11、13、16、18、19、22、23、24、26、27、29、31、32、33、35、36、38、40、41、43，均逐项读取全部评论，共63条。开放列表中的 PR 为0。对目录全字段、全部开放正文与评论扫描 csg、lindexi、林德熙、SourceGenerator、Jelallnalukebaqe 及完整英文展开名，相关匹配0项。第十四轮相关日志同样保留去重背景。

命名按原作者正文使用 csg。JelallnalukebaqeLairjaybearjair 是原例的解决方案、项目及目录名称。该名作为源代码定位依据保存。CsgIncrementalGenerator 是转换器类名。

## 一、原作者及原始来源链

1. [作者个人博客](https://blog.lindexi.com/post/dotnet-%E7%94%A8-SourceGenerator-%E6%BA%90%E4%BB%A3%E7%A0%81%E7%94%9F%E6%88%90%E6%8A%80%E6%9C%AF%E5%AE%9E%E7%8E%B0%E4%B8%AD%E6%96%87%E7%BC%96%E7%A8%8B%E8%AF%AD%E8%A8%80.html)署名林德熙／lindexi，明确给出 csg 英文展开、学习源代码生成技术的目的与演示用途，直接链接固定代码目录。
2. [腾讯云作者同步文](https://cloud.tencent.com.cn/developer/article/2259535)标示林德熙，末尾声明由作者个人站点／博客同步。页面日期为2023-04-07。
3. [固定代码目录](https://github.com/lindexi/lindexi_gd/tree/bba0c728bbc1d850f6f1929ab14a42e995e23e3b/JelallnalukebaqeLairjaybearjair)包含主项目、Analyzers项目和解决方案，共6个文件。两个子树递归结果 truncated=false，全部文件均已读取。
4. 博客还给出同作者 [Gitee 镜像](https://gitee.com/lindexi/lindexi_gd/tree/bba0c728bbc1d850f6f1929ab14a42e995e23e3b/JelallnalukebaqeLairjaybearjair)。本次核心实现采用 GitHub 固定原件核验；镜像可用性留待单独核对。

## 二、连续中文原例

采用 [这是测试类型.csg 第1—11行](https://github.com/lindexi/lindexi_gd/blob/bba0c728bbc1d850f6f1929ab14a42e995e23e3b/JelallnalukebaqeLairjaybearjair/JelallnalukebaqeLairjaybearjair/%E8%BF%99%E6%98%AF%E6%B5%8B%E8%AF%95%E7%B1%BB%E5%9E%8B.csg#L1-L11)全文，blob 为328d351d05d8a86f2900b628f1381b46f54d41ec。

原文件实际为11行，其中9个非空行和2个空行。条目保留连续正文、缩进和两处空行；显示时去除首位 UTF-8 BOM 与末尾换行。原例依次写命名空间引用、文件范围命名空间、类、公开静态无返回值方法及控制台输出调用。

[Program.cs](https://github.com/lindexi/lindexi_gd/blob/bba0c728bbc1d850f6f1929ab14a42e995e23e3b/JelallnalukebaqeLairjaybearjair/JelallnalukebaqeLairjaybearjair/Program.cs)使用 C# 顶层语句，引用“这是一个命名空间”并调用“这是测试类型.测试输出()”。作者文章报告的演示输出为“你好”。本次执行状态为待核实。

## 三、完整映射与生成路径

核心文件：[CsgIncrementalGenerator.cs](https://github.com/lindexi/lindexi_gd/blob/bba0c728bbc1d850f6f1929ab14a42e995e23e3b/JelallnalukebaqeLairjaybearjair/JelallnalukebaqeLairjaybearjair.Analyzers/CsgIncrementalGenerator.cs)，共77行，blob 为654eccd7a1f768342c2d1975b579e8c5a8cc1104。

### 六项完整映射

第27—35行的字典完整列出如下对应，左右两侧各附一个尾随 ASCII 空格：

- 引用命名空间 → using
- 定义命名空间 → namespace
- 类型 → class
- 公开的 → public
- 静态的 → static
- 无返回值类型的 → void

第37—50行逐行读取 SourceText，依次调用 string.Replace，再用 StringBuilder.AppendLine 收集结果。映射在文本层完成；匹配边界由原字面字符串及尾随空格决定。根据此静态实现，含同样匹配文本的注释、字符串或其他行内片段也会经过相同替换流程。完整 C# 词法上下文兼容性与更多语法覆盖继续待核实。

### 生成与宿主路径

1. [宿主 csproj](https://github.com/lindexi/lindexi_gd/blob/bba0c728bbc1d850f6f1929ab14a42e995e23e3b/JelallnalukebaqeLairjaybearjair/JelallnalukebaqeLairjaybearjair/JelallnalukebaqeLairjaybearjair.csproj)设置 net6.0、OutputType Exe；AdditionalFiles 只列“这是测试类型.csg”。ProjectReference 将生成器设为 Analyzer，ReferenceOutputAssembly 为 false。
2. 生成器第11—18行用 Generator(LanguageNames.CSharp) 标记，实现 IIncrementalGenerator；AdditionalTextsProvider 以大小写不敏感的扩展名比较筛出 .csg。
3. 第20—25行通过 RegisterSourceOutput 注册输出，先生成框架代码，再读取匹配文件的 GetText()。
4. 第27—50行进行上述六项字符串替换。
5. 第52行 AddSource 的提示名为原文件名加 .g.cs；内容进入 C# 编译。中文类型与方法命名依靠 C# 自身标识符能力。
6. [生成器 csproj](https://github.com/lindexi/lindexi_gd/blob/bba0c728bbc1d850f6f1929ab14a42e995e23e3b/JelallnalukebaqeLairjaybearjair/JelallnalukebaqeLairjaybearjair.Analyzers/JelallnalukebaqeLairjaybearjair.Analyzers.csproj)目标 netstandard2.0，依赖 CodeAnalysis.Analyzers 3.3.3、CodeAnalysis.CSharp 4.2.0。解决方案记录 Visual Studio 17.2.32630.192；作者文章要求较新版本 VS 2022。现代工具链适配需另行验证。

### 中文 API 边界

第59—75行 AddFrameworkCode 拼入一段 C# 源码：命名空间“系统”、静态类“控制台”、方法“输出一行文本(string 文本)”，内部调用 Console.WriteLine(文本)。生成提示名为 DefaultConsole。

“系统”“控制台”“输出一行文本”属于配套 C# 命名和包装 API。六个映射词属于语法文本转换。两层证据分开记录。框架源码随每个匹配文件进入输出回调；重复生成提示名与多文件扩展行为继续待核实。

## 四、历史、当前状态与版本

### 代码史

原始 [bba0c728提交](https://github.com/lindexi/lindexi_gd/commit/bba0c728bbc1d850f6f1929ab14a42e995e23e3b)标题“中文编程”，署名 lindexi；作者和提交者时间均为2022-10-07T03:41:52Z。该提交一次加入全部6个文件。

根仓为“博客用到的代码”集合，创建于2015-11-28T03:50:10Z。本轮读到默认分支 master 头 [5ad7b74e](https://github.com/lindexi/lindexi_gd/commit/5ad7b74e91a6e26807e38ac64018e26031b85578)，时间2026-10-10T12:56:17Z，archived=false。

[以该头固定的示例目录](https://github.com/lindexi/lindexi_gd/tree/5ad7b74e91a6e26807e38ac64018e26031b85578/JelallnalukebaqeLairjaybearjair)仍对应：

- Analyzers树：929d82cca22a12542804162323cd5f2f532c87e4
- 主项目树：323e9cb60ca8a8c3e92c89e1701a4c389c517d54
- 解决方案blob：eaa13ed7c4e5284862aa14552f42d70ee0727e1c

这些值与2022固定快照一致。路径过滤提交接口在 sha=5ad7b74e 下返回1项，即bba0c728。根仓活动时间与此子项目技术状态分别保存。该教学子项目保留2022年快照，维护计划、独立版本号及发行包待核实。

### 文稿史及公开时间边界

作者 lindexi.github.io 的同名原稿路径历史返回5项：

- 1da6d975b8cade28e0a0f322ba77f985ce5fa150，2022-10-16T06:32:19Z
- 02f8d4eb09f9b51fd7119118faeeafcf2439e919，2022-10-18T00:59:14Z
- 848c060ddd227be1d71ea3400929849fa0ad5994，2022-10-19T00:14:44Z
- 693a2da062b52f6584a4fa757508684af8bdc7ac，2023-06-05T00:32:44Z
- 9a6d62b47f25f4270e22f19a91d024ea534f7057，2024-08-06T12:44:27Z

已读[最早可达原稿](https://github.com/lindexi/lindexi.github.io/blob/1da6d975b8cade28e0a0f322ba77f985ce5fa150/dotnet%20%E7%94%A8%20SourceGenerator%20%E6%BA%90%E4%BB%A3%E7%A0%81%E7%94%9F%E6%88%90%E6%8A%80%E6%9C%AF%E5%AE%9E%E7%8E%B0%E4%B8%AD%E6%96%87%E7%BC%96%E7%A8%8B%E8%AF%AD%E8%A8%80.md)，其中已经包含 csg 名称、完整中文例程、实现及固定代码链接。[现存文章元数据](https://github.com/lindexi/lindexi/blob/df6b37e3fe769ac3395c807d7d46dff48e46f1e9/_posts/2022-10-17-dotnet-%E7%94%A8-SourceGenerator-%E6%BA%90%E4%BB%A3%E7%A0%81%E7%94%9F%E6%88%90%E6%8A%80%E6%9C%AF%E5%AE%9E%E7%8E%B0%E4%B8%AD%E6%96%87%E7%BC%96%E7%A8%8B%E8%AF%AD%E8%A8%80.md#L1-L7)同时列 CreateTime=2022/10/17 8:06:00 与 date=2024-8-6 20:43:31 +0800。这些元数据按各自标签保存。

腾讯云同步刊载日期为2023-04-07。该页面不同抓取结果的时分秒出现00:43:38与08:43:38两种显示，本条采用一致的日期粒度，显示时区待核实。项目准确首次对外公开时刻仍待核。

.NET周报的搜索结果还指向[2022-10-19博客园原文入口](https://www.cnblogs.com/lindexi/archive/2022/10/19/16804899.html)。archive与/p/16804899.html两种普通网页访问均返回Internal Error／Cache miss；该线索留作发现背景，技术事实采用已读取的作者原稿和代码。

## 五、许可与 AI

固定代码快照根 [LICENSE](https://github.com/lindexi/lindexi_gd/blob/bba0c728bbc1d850f6f1929ab14a42e995e23e3b/LICENSE)为 MIT，署名 Copyright (c) lindexi；许可证blob为529c61d151862147fc3a0354fd0ba3003d812329。代码的六文件目录范围与根许可一并核验。

作者博客页面另列 CC BY-NC-SA 4.0。条目区分源代码许可与文章许可。原站后续其他 AI 主题文章及腾讯云页面的“AI代码解释”界面控件属于各自页面背景；csg 的 AI 开发参与情况待核实。

## 六、实际检索关键词与时窗

本组从已发现的原作者同步文深入，不重复泛搜计数。网页实际查询：

1. "csg" "林德熙" SourceGenerator
2. "csg" "Chinese programming language by SourceGenerator"
3. "dotnet 用 SourceGenerator 源代码生成技术实现中文编程语言" "2022"
4. "dotnet 用 SourceGenerator 源代码生成技术实现中文编程语言" "2023"
5. "csg" "SourceGenerator" "2024"
6. site:cnblogs.com/lindexi/p/16804899.html
7. "dotnet 用 SourceGenerator 源代码生成技术实现中文编程语言" "2022-10-19"

GitHub代码搜索使用 org=lindexi、完整文章标题，取得作者的lindexi.github.io原稿、lindexi站点源及CSDNBlog副本。本组核心补证采用前两者。API继续读取示例固定树、全部源码、根LICENSE、目录路径历史、文章路径历史和当日默认头。

检索含2022—2024历史日期词，当前状态固定到2026-10-10观测头。日期词帮助定位，原件字段决定正文结论。

## 七、遗漏风险与后续边界

- csg 与计算机图形学 CSG 等英文缩写重名；识别依赖作者、英文展开、文章和固定项目目录四重对应。
- 六项带尾空格的字符串映射代表实际实现范围；完整 C# 语法、诊断、编辑器体验与复杂上下文兼容需具体补证。
- 中文控制台包装 API、原生中文标识符与六项关键字映射分别归类。
- 同名文件、多 .csg 文件、DefaultConsole重复提示名和字符串／注释替换属于后续工程行为核查范围。
- 代码commit、作者稿件CreateTime、博客date、腾讯云同步日期与真实公开时刻分别记录。博客园入口目前受抓取失败影响。
- 博客集合仓的2026更新属于全仓活动；csg子目录保持2022树对象。
- 作者定位为教学演示。独立运行、当前IDE与SDK适配、发行历史、维护计划和AI参与继续待核实。

