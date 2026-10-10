# 第十四轮：三项语言资料、HOS内核与既有条目补证

核验日期：2026-10-10。基线：[46734fc65a9a5da4cdc230c78c9f835134973e9a](https://github.com/yuyan-lang/chinese-programming-languages/tree/46734fc65a9a5da4cdc230c78c9f835134973e9a)。

## 结果

- 真正新发现3项：墨香中文编程、脑语言、HOS（HuangCheng72）。
- 本轮资料核实后新增正式条目4项：3项语言与1项内核。其中言、文言Perl来自Issue #5既有线索；墨香与HOS为本轮新发现。
- 新发现中的待分类候选1项：脑语言，持续追踪于[Issue #43](https://github.com/yuyan-lang/chinese-programming-languages/issues/43)。
- 完善已有语言2项：Calculator.rs中文试验分支与玄铁；保留原6条引用，追加35条，合计41条。
- 整合后语言目录80项、内核目录9项。正式收录表示公开语法或内核实现资料达到当前收录门槛；具体运行、版本、身份和许可缺口按字段记录。

## 正式条目

1. [言（lang-078）](https://中文编程语言.yuyan-lang.org/languages/lang-078.html)：独立中文语言与Python转译实现，固定10行斐波那契原例；言叶、文言心及段言／光明的设计和历史关系分层记录。
2. [文言Perl／中書珨（lang-079）](https://中文编程语言.yuyan-lang.org/languages/lang-079.html)：Perl方言与源过滤转换层，固定11行筛法原例，原作者2002年版本史及当前CC0声明。
3. [墨香中文编程／MxIDE（lang-080）](https://中文编程语言.yuyan-lang.org/languages/lang-080.html)：中文JavaScript语法方案与转换配置，固定9行条件分支及流程模板；结构化资料保留U+0001，网页以␁显示并注明。
4. [HOS（HuangCheng72）](https://中文编程语言.yuyan-lang.org/内核/hos-huangcheng72.html)：个人教学／实验宏内核，作者固定资料明确自述来自中国；x86与ARM阶段、自身初始化与管理逻辑、教学及移植来源分别记录，共35条原始参考。

完整入口见[语言目录](https://中文编程语言.yuyan-lang.org/)。

## 既有条目

[Calculator.rs](https://中文编程语言.yuyan-lang.org/languages/lang-033.html)补齐中文分支九对词元、Rust求值路径、分支历史、GPL及8行连续原例。[玄铁](https://中文编程语言.yuyan-lang.org/languages/lang-034.html)补齐Go／玄铁源码到LLVM的调用链、C运行时、MIT、候选版及AI作者声明，采用10行连续原例。两项旧代码和来源完整保存在分项日志。

## 研究记录

- [既有语言补证](round-14-existing-log.md)
- [言语言及谱系](round-14-yan-log.md)；[后续字段](round-14-yan-pending.json)
- [历史语言与脑语言发现](round-14-discovery-log.md)；[待核范围](round-14-discovery-pending.json)
- [墨香中文编程](round-14-moxiang-log.md)；[后续字段](round-14-moxiang-pending.json)
- [HOS内核](round-14-kernel-log.md)；[后续字段](round-14-kernel-pending.json)
- [补充搜索关键词](round-14-search.md)

## 开轮与协作

已读取根AGENTS.md、根目录、77项语言与8项内核、第十三轮日志、全部23项开放Issues及60条相关评论；开放PR为0。Issue #1对应既有资料完善，Issue #5对应言及文言Perl旧线索。相关议题的其余任务继续开放。新增脑语言待核议题独立跟踪。

## 来源、静态审阅与范围

固定中文例程、词法／解析或映射入口、作者原件、时间与版本分别核验。独立审阅补核了言的739个文件、HOS的444个文件、脑语言输入与组合路径，以及原引用保留情况。HOS调度说明按当前任务状态与其他就绪任务条件收紧；文言Perl的CC0及AI待核进入标准展示字段。

结构化资料、详情页、引用ID、链接目标、连续原例、原对象保留和全文差异列入提交审阅。适用GitHub检查及Pages发布状态在关联PR记录。项目独立运行、自举、性能和硬件结果继续待核实。

## 检索覆盖与下一轮

本轮轮换Bilibili、Gitee、GitHub、腾讯云原创技术文章、CSDN／DeepSeek技术社区、GitCode／AtomGit和知乎入口。发现查询主要面向2024—2026，历史补证追溯2002年与2018年起的记录。具体关键词、固定提交、时间范围及访问结果见分项日志。

遗漏风险包括B站索引及视频画面覆盖、平台账号互链、公开日期与Git时间区别、控制字符展示、同名项目混淆、源码与发行及演示的版本关系、词表与实际中文语法边界、教学移植与组件许可、默认构建资料完整性。下一轮优先补B站短视频的连续原例，轮换Gitee／GitCode小型项目与中文社区，同时继续既有薄弱条目和内核作者归属证据。
