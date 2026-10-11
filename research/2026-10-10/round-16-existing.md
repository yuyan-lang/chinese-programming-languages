# 第十六轮：coCN与Atlanage既有条目补全

核验日期：2026-10-10（UTC）。资料窗口：22:00—22:10。基线：[93815086f1778802ea57ddeeec8ad717e355814f](https://github.com/yuyan-lang/chinese-programming-languages/tree/93815086f1778802ea57ddeeec8ad717e355814f)。对象：coCN lang-036、Atlanage lang-037。

## 结果与计数

- 完善既有正式语言2项；新发现0项，新增正式语言0项，新增内核0项。基线目录为86语言、9内核。
- coCN简介398字符，其中340个基本汉字；Atlanage简介427字符，其中355个基本汉字。汉字计数采用U+4E00—U+9FFF范围，两条简介均超过250汉字。
- 保留两对象全部原字段、ID、名称和别名。所有旧值完整保存于下方原对象记录。
- 原JSON共24条参考URL全部保留：coCN 13条、Atlanage 11条。coCN原详情页另有1条独立示例来源，纳入references；原资料独立来源URL合计25条全部保留。
- 新补35条引用：coCN 19条、Atlanage 16条。最终coCN 33条、Atlanage 27条，合计60条。单与原JSON比较增加36条，其中1条为原网页来源归并。
- coCN保持第33—42行原10行中文代码，Atlanage从第8—11行4行扩为完整hello.at第1—11行。两段均固定提交逐字核对，Atlanage原代码完整保留于下方。
- 新增作者／历史、包版本与引导版本分层、许可声明层级、AI参与待核、实现流程和局部关系证据。项目安装、执行、编译、测试、自举与性能为待核实事项。
- 本分项采用公开来源静态阅读与资料整理。豫言沿用基线。
- coCN根提交旧引用标题调整为“最早可达根提交：Git记录时间与首次公开时间分列”，URL保持；原title完整保存于下方旧对象。许可与AI信息同步记录于核验说明。

## 启动与前轮成果复用

已读[研究规范](https://github.com/yuyan-lang/chinese-programming-languages/blob/93815086f1778802ea57ddeeec8ad717e355814f/AGENTS.md)、基线语言目录的两对象、[coCN详情页](https://github.com/yuyan-lang/chinese-programming-languages/blob/93815086f1778802ea57ddeeec8ad717e355814f/languages/lang-036.html)、[Atlanage详情页](https://github.com/yuyan-lang/chinese-programming-languages/blob/93815086f1778802ea57ddeeec8ad717e355814f/languages/lang-037.html)、[第十五轮总报告](https://github.com/yuyan-lang/chinese-programming-languages/blob/93815086f1778802ea57ddeeec8ad717e355814f/research/2026-10-10/round-15.md)、第十五轮既有补全报告和[第二轮原仓库研究](https://github.com/yuyan-lang/chinese-programming-languages/blob/93815086f1778802ea57ddeeec8ad717e355814f/research/2026-10-10/repositories.md)。

[Issue #1](https://github.com/yuyan-lang/chinese-programming-languages/issues/1)现有15条评论，[Issue #3](https://github.com/yuyan-lang/chinese-programming-languages/issues/3)现有5条评论，均已读取。[Issue #3首条进度评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/3#issuecomment-6097444847)已记录coCN、Atlanage经PR #10收录，以及引导、单线程任务、种子物化和版本差异。本轮沿两项已收录身份补资料，发现计数保持0。[第十五轮Issue #1进度](https://github.com/yuyan-lang/chinese-programming-languages/issues/1#issuecomment-6102618745)记录文言、言序补全，本轮保持旧对象和页面来源并集口径。

两目标默认提交均与第二轮相同。新引用表示本轮补入条目参考列表的来源URL；同一固定文件的不同证据行段独立定位；项目计数按完整语言对象归并。

## coCN补证

### 固定快照与时间

- master仍为c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07；完整树118项，truncated=false。当前可达提交63条，已通过固定sha的提交集合复读。
- 最新提交作者／提交者时间为2026-10-08T08:13:13Z，仓库pushed_at为同日08:58:22Z；当前仓库archived=false。
- 根bbb29bf8记录2026-07-24T08:33:28Z；GitHub仓库创建2026-09-12T15:24:29Z，Release v0.0.1公开发布2026-09-12T15:25:15Z。Git历史日期、托管创建及公开发行时间分别记录。
- 历史作者字段包含COSMOnb666、cosmo、coCN、王煜鑫等公开署名；账号和署名之间的身份对应继续待核实。

来源：[固定提交集合](https://api.github.com/repos/3477856804/coCN/commits?sha=c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07&per_page=100)、[完整树](https://api.github.com/repos/3477856804/coCN/git/trees/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07?recursive=1)、[发行元数据](https://api.github.com/repos/3477856804/coCN/releases?per_page=100)。

### 实现历史及语义层级

- 历史f930c811仍保存C实现。2026-10-08的[df0d3b8](https://github.com/3477856804/coCN/commit/df0d3b8d614231a193f7d3d2fea48c013333c7ce)加入.co解释器模块，[303a917](https://github.com/3477856804/coCN/commit/303a9179b47708bbef5007390a8693e0248f02db)移除C实现、Makefile和自举运行时模板，[ef32d0e](https://github.com/3477856804/coCN/commit/ef32d0ec370dd41a49ebafa6539b1a29ee8d9b78)整理src与编译器路径。
- [模块规范第11—95行](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/%E9%87%8D%E5%86%99%E8%A7%84%E8%8C%83.md#L11-L95)保存token、AST、值、父环境链和控制流字典的数据形状。实现由固定词法表、parser、求值器相互核对。
- [用户函数调用第1062—1093行](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L1062-L1093)显示闭包环境、子环境和形参绑定；[第1440—1463行](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L1440-L1463)显示变量及函数构造的实际字段。
- [parser第664—719行](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E8%AF%AD%E6%B3%95%E5%88%86%E6%9E%90%E5%99%A8.co#L664-L719)收集参数与返回类型；当前求值器全文对“类型标注／参数类型／返回类型”字段读取的进一步静态核对见核验摘要。条目以类型标注语法和强制检查待核分别表述。
- [第2497—2554行任务实现](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L2497-L2554)明示单线程延迟任务，等待时执行并缓存；历史或README的线程宣传保留为作者陈述层。
- [index.js第29—60行](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/index.js#L29-L60)与CLI同时走Node.js→引导cocn→src/解释器.co链，环境变量传入绝对目标路径。
- [安装器第145—179行](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/install.js#L145-L179)先尝试包内引导，再下载；本轮静态阅读脚本，安装副作用和下载资产均待运行核验。
- [L2脚本第1—35行](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/%E6%B5%8B%E8%AF%95/%E8%87%AA%E4%B8%BEL2.sh#L1-L35)仍引用根路径；当前完整树的运行时模板及引导二进制补齐方式待核。

### 版本、许可与AI

包清单、index.js和安装器为0.0.2，README为0.0.1；安装器BOOTSTRAP_VERSION为0.1.0。GitHub现有唯一正式Release v0.0.1提供四个命名资产：darwin-arm64、linux-aarch64、linux-x86_64、windows-x86_64。资产metadata有名称、大小及digest；本轮保存元数据事实，制品内容、源码对应和运行结果待核。

固定package.json第38行声明Apache-2.0，完整树的许可证正文及NOTICE待补，GitHublicense=null。README、重写规范、当前核心文件及63条提交说明中的明确AI开发参与材料继续待补。机器学习和张量用途单独作为项目功能方向记录。

Gitee与npm官方页面／注册表本轮访问仍失败。公开搜索的npm.io索引显示0.0.3及更新后的包描述，按搜索线索保存，官方发布状态继续待核。

## Atlanage补证

### 编译链、语法与发行

- main仍为da5b3a9b778ff546382990de35f2112efc9544f9；完整树322项，truncated=false，当前主线2个提交。
- [词法器第610—647行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_lexer.at#L610-L647)映射部分中文／全角符号；第351行起识别中文引号。实际支持范围依明确分支描述。
- [入口第880—950行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atlv1.at#L880-L950)呈现文件引用、包导入、模块导入展开，再到词法、解析、语义、汇编、COFF与链接。
- [链接器第142—162行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_linker.at#L142-L162)按符号分配Windows DLL；[第1156—1208行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_linker.at#L1156-L1208)填写AMD64、MZ／PE及PE32+头部。
- seed_builder的现有行为是十六进制解码、SHA-256核对与文件写出；自编译脚本使用既有AT-V1.exe，比较两代编译器对hello.at的汇编文本。完整源码引导、二进制复现、全程序等价性为单独待核事项。
- GitHub发行标签1.0、名称qwq、正文1.0.1、资产atlanage-v1.0.zip。published_at=2026-08-16T17:58:33Z；ZIP创建时间=2026-08-17T09:23:02Z，大小1,864,117字节，digest为sha256:dcf3a99fcffac4da4b013c97215a0ba055be95de495b766d2edbfc9b1b0e624c。资产内部版本待核。
- 许可证识别null，固定目录的项目级许可证正文和NOTICE待补。AI辅助开发的作者声明待补。

### 与玄铁的局部源码对应

比较固定版本：
- Atlanage：da5b3a9b778ff546382990de35f2112efc9544f9。
- 玄铁：16554746121c61d98429b498f4e8aee9ef650978，Git记录日期2026-08-08T10:03:02Z。
- 额外读取玄铁当前17ef9d35版本作路径定位，正式对应引用使用上述历史版本。

可复核观察：
1. Atlanage的[xt_runtime.c第170—185行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/runtime/xt_runtime.c#L170-L185)保留“玄铁运行时错误”文本；同文件第2427行保留XuanTie临时目录字符串。
2. [Atlanage线程池第146—196行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/runtime/xt_threadpool.c#L146-L196)与[玄铁同路径第146—196行](https://github.com/MARKJY-China/XuanTie-Lang/blob/16554746121c61d98429b498f4e8aee9ef650978/runtime/xt_threadpool.c#L146-L196)连续51行逐字相同，包括空白与缩进。
3. [Atlanage JSON解析第2880—3012行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/runtime/xt_runtime.c#L2880-L3012)与[玄铁第2878—3010行](https://github.com/MARKJY-China/XuanTie-Lang/blob/16554746121c61d98429b498f4e8aee9ef650978/runtime/xt_runtime.c#L2878-L3010)连续133行逐字相同。
4. 对应blob：线程池为704b1b3b27f5d7dcc8ef0915409661b5e1f2b4d8／e8175f172d3ae50432c64b47b0f40c607a18efb3；JSON源文件为5b8625870b1861b87765b52301820f3a18c779c3／decfcabbb509c9d5b6c1a56f19380b3e12f37b61。
5. [玄铁历史MIT文件](https://github.com/MARKJY-China/XuanTie-Lang/blob/16554746121c61d98429b498f4e8aee9ef650978/LICENSE)署名2026 问号盒。该许可按对照来源记录，Atlanage整体许可继续待核。

上述结果限定为运行时文件中局部文本的直接对应。整体工程派生范围、移植过程、作者协作、授权沿革及法律性质均继续待核。对照以摘要和双边固定链接呈现。

## 原代码与本轮例程

### coCN

沿用原code、原code_source和固定blob77ffa49b05a6aab4cd7e1cc11425d648ecb3b130。源文件第33—42行，10行连续原文：

```text
函数 判断(整数 n) -> 字符串
    若 n > 10 则
        返回 "大"
    结束
    返回 "小"
结束

输出 判断(12)

输出 判断(5)
```

本轮代码值保持不变，类型标注语法与执行检查效果分开描述。

### Atlanage原4行

原来源：https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/examples/hello.at#L8-L11

```text
声明 加法(a, b){
    返回值 a + b;
};
打印("1+2=" + 加法(1, 2));
```

### Atlanage本轮完整11行

来源：[examples/hello.at第1—11行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/examples/hello.at#L1-L11)，blob7884f0f829940f6748eeb2799cf88325cdc92ec9。

```text
打印("你好，世界！");

设 列表 水果 = ["苹果", "香蕉", "橙子"];
循环(设 果 : 水果){
    打印("我喜欢" + 果);
};

声明 加法(a, b){
    返回值 a + b;
};
打印("1+2=" + 加法(1, 2));
```

源文件以最后一行分号结束。已核对code等于固定文件全文；旧4行仍是新例程末尾连续子串。所有中文、引号、空格、空行与标点照原样保存。

## 原结构化对象完整保存

```json
[
  {
    "name": "coCN",
    "aliases": [],
    "category": "中文关键字通用编程语言（实验性；解释执行，并保留 coCN→C 编译器源码）",
    "author": "COSMOnb666（package.json 署名）；GitHub 仓库所有者为 3477856804。两者均为项目公开账号/署名，不据此推定真实姓名。",
    "first_publication": "2026-09-12（目前可确认的首个 GitHub Release 发布日期；语言首次对外公开日期仍未核实）",
    "description": "以中文关键字与标识符编程的独立语言项目。当前默认分支以 coCN 源码实现词法分析、递归下降语法分析及树遍历求值，Node.js 启动器再借助旧版 C 实现的引导二进制运行这些 .co 模块。不能把当前仓库概括为完全摆脱 C 依赖、可独立复现完整自举的实现。",
    "features": [
      "实际词法表识别让、变量、常量、函数、返回、如果、若、否则、当、对于、从、到、循环、结束、且、或、非等中文词；并非仅把英文示例翻译为中文。",
      "源码可见函数与返回、条件和循环、列表与字典、模块导入、异常、闭包/高阶调用、模式匹配等解析和求值分支；本次未执行测试。",
      "类型标注语法存在，但当前求值器未读取变量类型、参数类型及返回类型标注，不将 README 的静态类型/运行时强制检查主张列为已验证特性。",
      "当前并发/等待实现为单线程延迟任务，等待时在当前线程执行；并发执行依次等待，让出为空操作，不能标为已验证的真线程并行。",
      "保留 coCN 编写的生成 C 源码编译器，但它依赖当前树缺失的自举运行时.c，并调用系统 cc。"
    ],
    "code": "函数 判断(整数 n) -> 字符串\n    若 n > 10 则\n        返回 \"大\"\n    结束\n    返回 \"小\"\n结束\n\n输出 判断(12)\n\n输出 判断(5)",
    "implementation": "当前 master：src/词法分析器.co → src/语法分析器.co → src/求值器.co，src/解释器.co 读取 COCN_TARGET 指定的程序并调用运行(源)。bin/cocn.js 用 child_process.spawn 启动引导 cocn 二进制，执行 src/解释器.co；install.js 指定引导版本 0.1.0，优先 Gitee、其次 GitHub，并无 C 源码构建回退。求值器还复用宿主的原生内置函数。历史提交 f930c811e161f508fa7c6d61b26f2998e623a168 的 co.c 可见 C 解释器及生成 C 后调用 cc 的编译通道。当前编译器/自举编译器.co 仍读取自举运行时.c；该文件、co.c、Makefile 及 bin/cocn 均不在本次固定提交的完整树中。",
    "status": "公开、未归档，实验性开发中；最近默认分支提交日期为 2026-10-08。仅完成只读源码核查，未安装、编译、运行或证明全量兼容、自举成功与性能。当前引导与旧自举脚本存在可见缺口。",
    "version": "固定 master 提交的 package.json/index.js/install.js 为 0.0.2；README 仍称 0.0.1。GitHub Releases 仅查到 v0.0.1（2026-09-12 发布）；install.js 所需引导版本 0.1.0 的 GitHub Release 返回 404。以上分别为仓库包版本、文档版本、发行版和引导版本，不能混作最新语言版本；npm 注册表当前版本未核实。",
    "relations": "package.json 将 Gitee COSMOnb666/coCN 列为项目仓库/首页，GitHub 3477856804/coCN 为本次核查对象。与 C 的关系为历史实现语言、当前引导运行时以及保留编译器的目标/运行时依赖；Node.js 负责 npm 启动与安装。未发现足够原始证据证明它派生自 Python 或其他既有中文语言。",
    "references": [
      {
        "title": "GitHub 仓库元数据（创建、推送、归档状态）",
        "url": "https://api.github.com/repos/3477856804/coCN"
      },
      {
        "title": "本次固定默认分支提交",
        "url": "https://github.com/3477856804/coCN/commit/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07"
      },
      {
        "title": "包版本、作者署名与 Gitee 地址",
        "url": "https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/package.json#L1-L45"
      },
      {
        "title": "真实中文关键字表",
        "url": "https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E8%AF%8D%E6%B3%95%E5%88%86%E6%9E%90%E5%99%A8.co#L32-L36"
      },
      {
        "title": "递归下降 parser 与类型标注",
        "url": "https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E8%AF%AD%E6%B3%95%E5%88%86%E6%9E%90%E5%99%A8.co#L482-L505"
      },
      {
        "title": "自解释器入口",
        "url": "https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E8%A7%A3%E9%87%8A%E5%99%A8.co#L12-L31"
      },
      {
        "title": "Node.js 引导入口",
        "url": "https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/bin/cocn.js#L67-L78"
      },
      {
        "title": "引导版本与下载来源",
        "url": "https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/install.js#L20-L32"
      },
      {
        "title": "当前任务执行模型",
        "url": "https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L2497-L2554"
      },
      {
        "title": "生成 C 的编译器及缺失运行时依赖",
        "url": "https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/%E7%BC%96%E8%AF%91%E5%99%A8/%E8%87%AA%E4%B8%BE%E7%BC%96%E8%AF%91%E5%99%A8.co#L992-L1063"
      },
      {
        "title": "首个 GitHub Release v0.0.1",
        "url": "https://github.com/3477856804/coCN/releases/tag/v0.0.1"
      },
      {
        "title": "最早可达根提交（提交日期不是公开日期）",
        "url": "https://github.com/3477856804/coCN/commit/bbb29bf8db7f6d0e3fee3ef441267145dadc1451"
      },
      {
        "title": "历史 C 解释器与编译实现",
        "url": "https://github.com/3477856804/coCN/blob/f930c811e161f508fa7c6d61b26f2998e623a168/co.c#L7047-L7088"
      }
    ],
    "verification_notes": "已固定默认分支 master 的 c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07；完整 Git tree 返回 truncated=false。GitHub 仓库 created_at 为 2026-09-12T15:24:29Z；根提交 bbb29bf8… 的 author/committer 日期为 2026-07-24T08:33:28Z，不能由它推出当时已公开。唯一查到的 GitHub Release v0.0.1 published_at 为 2026-09-12T15:25:15Z，标签经 annotated tag 解引用到 9483dd20a4c1b45ced40f5ed0a2a662dde6bdc18。README 的自举、真线程、类型强制检查、性能和自动求导宣传不当作测试证据：当前并发代码直接显示单线程延迟执行；parser 收集类型标注但 evaluator 不读取。旧测试/自举.sh 和测试/自举L2.sh 仍默认 ./co、根目录自举编译器.co，未随当前删除/迁移更新。Gitee 页面及官方 npm 注册表未成功读取，故不判定其发行资产一定不存在，也不把 GitHub 包清单版本当成 npm 最新版。package.json 声明 Apache-2.0，但当前树未见 LICENSE 文件。全过程只读，未执行陌生源码。 待核实字段：语言首次对外公开日期（含 Gitee 首发）；GitHub 账号与作者署名背后的真实身份；npm 注册表最新发布版本及实际包内容；Gitee v0.1.0 引导资产是否可用；完整自举/可复现构建/全量语义兼容/性能/自动求导运行效果。",
    "code_source": "https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/%E4%BE%8B%E5%AD%90/%E8%87%AA%E4%B8%BE%E5%87%BD%E6%95%B0%E7%A4%BA%E4%BE%8B.co#L33-L42",
    "code_context": "从仓库例子/自举函数示例.co 第 33–42 行连续原样摘录，包含带类型标注的中文函数、若/则/返回/结束及两次输出调用。未补写、拼接或改写示例，未运行；函数按源码逻辑分别返回“大”“小”，但本条不把预期结果写成实测结果。",
    "verified_at": "2026-10-10",
    "repository_created_at": "2026-09-12T15:24:29Z",
    "code_source_detail": {
      "repository": "3477856804/coCN",
      "default_branch": "master",
      "commit": "c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07",
      "path": "例子/自举函数示例.co",
      "blob_sha": "77ffa49b05a6aab4cd7e1cc11425d648ecb3b130",
      "start_line": 33,
      "end_line": 42,
      "excerpt_kind": "连续原文；未运行"
    },
    "repository_pushed_at": "2026-10-08T08:58:22Z",
    "id": "lang-036"
  },
  {
    "name": "Atlanage",
    "aliases": [],
    "category": "中文通用编程语言（编译型）",
    "author": "wc772（仓库所有者及 Release 发布者；1.0 标签根提交署名 atra，两者身份关系未核实）",
    "first_publication": "2026-08-16（目前可核实的首个 GitHub Release 发布日；不等同于项目最早诞生或首次公开日期）",
    "repository_created_at": "2026-08-16T17:28:53Z",
    "description": "使用中文关键字、中文标识符与花括号/分号语法的编译型语言。仓库包含 .at 示例、以 .at 编写的词法分析器、语法分析器、语义分析器、代码生成器、汇编器和链接器源码；已检查的编译入口串联这些模块，目标为 Windows x86-64。此次仅作源码与发布元数据核实，未编译或运行程序。",
    "features": [
      "词法表实际映射“设、如果、又如果、否则、循环、返回值、声明、函数、类、继承”等中文关键字，并含中文字符标识符识别逻辑。",
      "语法分析器含变量声明、函数声明、条件、循环、类与接口等解析分支；示例使用中文函数名和内建打印调用。",
      "编译入口可见词法分析、解析、语义分析、汇编输出、COFF 对象生成与链接步骤；链接器定义 AMD64 目标。",
      "仓库提供 .at 编译器源码、含嵌入汇编的 .at 运行时、C 运行时相关文件及十六进制二进制种子。",
      "自举、M:N 调度、AUI、OpenGL/Vulkan 和包管理为项目宣称或对应源码/示例所展示的方向，其完整性、可运行性与性能未由此次研究验证。"
    ],
    "code": "声明 加法(a, b){\n    返回值 a + b;\n};\n打印(\"1+2=\" + 加法(1, 2));",
    "implementation": "主入口 self-hosted/atlv1.at 引入 atl_lexer.at、atl_parser.at、atl_semantic.at、atl_codegen.at、atl_assembler.at、atl_linker.at 等 .at 模块；907–950 行可见 lex → parse_program → sem_analyze → codegen → assemble/write_coff → link。self-hosted/atl_rt.at 使用“汇编(...)”嵌入 x86-64 汇编；runtime/ 另含 xt_runtime.c、xt_threadpool.c、xt_net.c 等 C 文件。seed/seed_builder.c 是解码并校验十六进制种子的物化器，输出 atlv1.exe 和 atl_rt.obj，并非从 C 源码重建语言编译器。rebuild_atlv1.ps1 依赖预存 AT-V1.exe；rt_build.ps1 依赖 atlc.exe、Python 与 NASM。GitHub 标记主要语言为 C 不能代替对实现结构的判断。",
    "status": "已有公开源码和 GitHub Release，仓库未归档；截至 2026-10-10，默认分支最后提交为 2026-08-17。未作运行、完整自举或持续维护状态验证；仓库元数据未识别许可证。",
    "version": "GitHub 唯一 Release/标签为 1.0（非预发布），发布正文为“1.0.1”，资产名为 atlanage-v1.0.zip；版本标注不一致，未消歧。",
    "relations": "AT-V1.exe / atlv1 为该项目的编译器命名，不能据此增列为独立语言。仓库 fork=false；未发现足以确认其与其他语言存在继承、移植或同源关系的第一方说明。",
    "references": [
      {
        "title": "仓库与公开元数据",
        "url": "https://api.github.com/repos/wc772/atlanage"
      },
      {
        "title": "1.0 Release",
        "url": "https://github.com/wc772/atlanage/releases/tag/1.0"
      },
      {
        "title": "固定默认分支提交",
        "url": "https://github.com/wc772/atlanage/commit/da5b3a9b778ff546382990de35f2112efc9544f9"
      },
      {
        "title": "中文示例原文（第 8–11 行）",
        "url": "https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/examples/hello.at#L8-L11"
      },
      {
        "title": "中文关键字与标识符实现",
        "url": "https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_lexer.at#L126-L238"
      },
      {
        "title": "语句解析实现",
        "url": "https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_parser.at#L967-L1015"
      },
      {
        "title": "编译流水线源码",
        "url": "https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atlv1.at#L907-L950"
      },
      {
        "title": "种子物化器",
        "url": "https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/seed/seed_builder.c#L115-L196"
      },
      {
        "title": "自编译与单示例输出比较脚本",
        "url": "https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/rebuild_atlv1.ps1#L18-L50"
      },
      {
        "title": "运行时构建脚本",
        "url": "https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/rt_build.ps1#L4-L12"
      },
      {
        "title": "1.0 标签对应根提交",
        "url": "https://github.com/wc772/atlanage/commit/837af6b15ca64ee2fc1b157d7bc15fc0818948a0"
      }
    ],
    "verification_notes": "固定读取 main=da5b3a9b778ff546382990de35f2112efc9544f9。中文语法有词法表、解析分支与原始示例三类静态证据，足以作为已实现项目候选收录，但不等于运行测试通过。唯一 Release 的 published_at=2026-08-16T17:58:33Z，与仓库 created_at 区分；首发标签指向 837af6b15ca64ee2fc1b157d7bc15fc0818948a0（作者署名 atra），当前 main 则有独立根提交 6bda6cec0b860c0456280c797d417f5360ab4fb5（2026-08-16T18:05:23Z），不可把当前主线根提交当成早于 Release 的发布证据。未核实更早公开史、作者真实身份、atra 与 wc772 的关系、二进制与源码对应性、完整引导可复现性、自举收敛、调度正确性、性能和跨平台支持。seed_builder 输出 atlv1.exe，而构建脚本使用 AT-V1.exe；默认树中未见 .exe/.obj 文件，README 的二进制目录示意不代表这些文件已跟踪。自举脚本仅设计比较 hello.at 的汇编文本，不证明所有程序或编译器二进制可复现。未下载或执行发布包。",
    "code_source": "https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/examples/hello.at#L8-L11",
    "code_context": "examples/hello.at 第 8–11 行的连续原文，独立的加法函数声明及调用片段；保留原始缩进、标点和文字，未拼接、改写或生成。",
    "code_source_detail": {
      "repository": "wc772/atlanage",
      "branch": "main",
      "commit": "da5b3a9b778ff546382990de35f2112efc9544f9",
      "path": "examples/hello.at",
      "lines": "8-11",
      "blob_sha": "7884f0f829940f6748eeb2799cf88325cdc92ec9",
      "verification": "GitHub 连接器按固定 commit 读取；未执行"
    },
    "verified_at": "2026-10-10",
    "repository_pushed_at": "2026-08-17T09:21:36Z",
    "id": "lang-037"
  }
]
```

## 本轮新增35条引用

- coCN：[项目用途与自解释器说明（固定README）](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/README.md#L5-L15)
- coCN：[模块数据交换、环境与控制流规范](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/%E9%87%8D%E5%86%99%E8%A7%84%E8%8C%83.md#L11-L95)
- coCN：[参数与返回类型标注的解析](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E8%AF%AD%E6%B3%95%E5%88%86%E6%9E%90%E5%99%A8.co#L664-L719)
- coCN：[父环境链及宿主内置复用](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L68-L105)
- coCN：[闭包环境、形参绑定及统一调用](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L1062-L1093)
- coCN：[变量声明与函数值构造](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L1440-L1463)
- coCN：[创建根环境与树遍历执行入口](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/src/%E6%B1%82%E5%80%BC%E5%99%A8.co#L1765-L1784)
- coCN：[Node.js程序接口run与版本号](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/index.js#L29-L60)
- coCN：[Node.js版本与平台声明](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/package.json#L47-L60)
- coCN：[优先检查包内引导、下载与失败处理](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/install.js#L145-L179)
- coCN：[L2自举脚本及保留的旧路径](https://github.com/3477856804/coCN/blob/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07/%E6%B5%8B%E8%AF%95/%E8%87%AA%E4%B8%BEL2.sh#L1-L35)
- coCN：[完整固定目录树：118项及许可／引导材料范围](https://api.github.com/repos/3477856804/coCN/git/trees/c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07?recursive=1)
- coCN：[发行集合与四平台资产元数据](https://api.github.com/repos/3477856804/coCN/releases?per_page=100)
- coCN：[现存63条Git提交与公开作者署名](https://api.github.com/repos/3477856804/coCN/commits?sha=c641a58067e1a7cc0d26bfd6cebc8b42ce37cd07&per_page=100)
- coCN：[自解释器模块加入的历史提交](https://github.com/3477856804/coCN/commit/df0d3b8d614231a193f7d3d2fea48c013333c7ce)
- coCN：[C实现与运行时模板移除的历史提交](https://github.com/3477856804/coCN/commit/303a9179b47708bbef5007390a8693e0248f02db)
- coCN：[包版本升为0.0.2的历史提交](https://github.com/3477856804/coCN/commit/639b35e496982e20c8ddd349aa7409b49b1e01fc)
- coCN：[源目录整理与入口路径变更](https://github.com/3477856804/coCN/commit/ef32d0ec370dd41a49ebafa6539b1a29ee8d9b78)
- coCN：[Gitee内容合并历史](https://github.com/3477856804/coCN/commit/66ff0a209d44aaba2950837da48b3c1ed4608f3b)
- Atlanage：[完整基础原例：问候、列表循环与函数](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/examples/hello.at#L1-L11)
- Atlanage：[项目功能范围说明](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/README.md#L1-L28)
- Atlanage：[中文语法与符号文档](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/%E6%96%87%E6%A1%A3/%E4%BB%8B%E7%BB%8D.md#L1-L32)
- Atlanage：[中文与全角符号词法分支](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_lexer.at#L610-L647)
- Atlanage：[引用、包、模块展开与完整编译入口](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atlv1.at#L880-L950)
- Atlanage：[链接器Windows系统DLL导入表](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_linker.at#L142-L162)
- Atlanage：[链接器PE32+／AMD64可执行文件头部](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/self-hosted/atl_linker.at#L1156-L1208)
- Atlanage：[现存C运行时中的玄铁名称字符串](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/runtime/xt_runtime.c#L170-L185)
- Atlanage：[线程池局部实现对照：本项目51行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/runtime/xt_threadpool.c#L146-L196)
- Atlanage：[JSON解析局部实现对照：本项目133行](https://github.com/wc772/atlanage/blob/da5b3a9b778ff546382990de35f2112efc9544f9/runtime/xt_runtime.c#L2880-L3012)
- Atlanage：[完整固定目录树：322项及许可材料范围](https://api.github.com/repos/wc772/atlanage/git/trees/da5b3a9b778ff546382990de35f2112efc9544f9?recursive=1)
- Atlanage：[发行时间、版本与ZIP资产摘要](https://api.github.com/repos/wc772/atlanage/releases?per_page=100)
- Atlanage：[当前主线根提交及署名](https://github.com/wc772/atlanage/commit/6bda6cec0b860c0456280c797d417f5360ab4fb5)
- Atlanage：[局部源码对照：玄铁历史线程池51行](https://github.com/MARKJY-China/XuanTie-Lang/blob/16554746121c61d98429b498f4e8aee9ef650978/runtime/xt_threadpool.c#L146-L196)
- Atlanage：[局部源码对照：玄铁历史JSON解析133行](https://github.com/MARKJY-China/XuanTie-Lang/blob/16554746121c61d98429b498f4e8aee9ef650978/runtime/xt_runtime.c#L2878-L3010)
- Atlanage：[对照来源玄铁的MIT原件及版权署名](https://github.com/MARKJY-China/XuanTie-Lang/blob/16554746121c61d98429b498f4e8aee9ef650978/LICENSE)

## 查询、限制与资料核验

1. GitHub只读读取基线研究规范、两对象、两详情页、第十五轮报告和初始仓库研究，以及Issue #1／#3全部评论。
2. 读取两目标仓库元数据、默认分支、固定递归树、发行集合、提交集合。默认提交与前轮一致；固定coCN提交集合再次返回63条。
3. 固定读取coCN README、重写规范、package、index、CLI、install、词法、parser、求值器、解释器、编译器、L2脚本、原始例程。
4. 固定读取Atlanage README、介绍、hello和函数例程、词法、parser、语义、入口、链接器、种子物化、自编译与运行时脚本，以及C运行时／线程池文件。
5. 发现玄铁名称字符串后，先比当前固定源，再通过路径历史取得2026-08-08版本；两组连续片段严格按原字符比较，相等值true。只保存摘要、blob和行段定位。
6. 公开搜索coCN／COSMOnb666、Atlanage／wc772和npm包名。Atlanage精确身份的新增网页证据待补；条目引用集中于可确认身份的项目来源。
7. web读取Gitee页返回不可访问，npm官方包页返回Cache miss，registry官方URL返回不可访问；项目与制品的可用性继续待核。
8. 资料核验覆盖字数、结构、引用保留、字段保留和已取得文本的逐字比对；目标项目代码采用静态阅读。
9. 两个完整对象的原字段、原详情页来源、元数据摘要、评论、固定双源对应和引用计数均完整保留。

后续最需要补齐：coCN官方npm版本／制品与Gitee引导、AI开发声明、许可正文；Atlanage版本消歧、引导制品与源码对应、整体许可及局部代码演化说明；两项独立运行、自举与性能证据。

