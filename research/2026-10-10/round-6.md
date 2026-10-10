# 第六轮：既有线索收录、语言沿革与内核资料

核验日期：2026-10-10（UTC）。起始提交：38de4b3dc0580eb8c3dcad682d9c7e18c7798bdd。

## 结果与计数

- 本轮新发现项目0组，新增待核实项目0组；工作集中于既有候选的原始证据与有界扩展检索。
- 语言正式条目新增4项：道（Carson，lang-052）、CNSH（lang-053）、华夏编程（lang-054）、轻语言（VcnStudio，lang-055）。前2项来自[Issue #3](https://github.com/yuyan-lang/chinese-programming-languages/issues/3)，后2项来自[Issue #19](https://github.com/yuyan-lang/chinese-programming-languages/issues/19)。
- 完善已有5项：段言lang-008、光明lang-009、天工语lang-010、细雨言lang-016（历史名习语言／曦语言）、入墨答lang-017。
- 内核正式条目新增1项：NeoAetherOS／na-kernel，对应[Issue #18](https://github.com/yuyan-lang/chinese-programming-languages/issues/18)。
- 合计旧线索完成分类收录5项，目录语言条目51→55、内核条目6→7。条目数涵盖历史阶段，当前实现按项目沿革关联；段言和光明的统一工具链按同一沿革记录。
- 衍真、语程同名关系及言叶系列继续待核实，取得的补充来源保存在日志及相关议题。已收录项目的具体版本、源码与运行缺口保留在条目中。

“核实收录”表示达到相应分类的资料条件。作者说明、固定源码、发行元数据、原视频演示和独立运行采用各自证据层级。

## 本轮关键修订

道取得Gitee／GitHub相同提交、中文原例、解释器和虚拟机；CNSH取得固定Gitee中文原例、解析与运行入口、C99转译器及2.2.0发行。华夏编程与轻语言依据原作者视频公开资料收录，实际源码与编译模型继续待核实。

段言与光明的共同根、改名、双亲合流和迁移公告已交叉核实。细雨言采用作者正式更名公告，并保留习语言、曦语言别名及原ID。天工语区分Cargo版本与CLI显示字符串。入墨答补原作者Haskell源码、作者署名和完整阶乘原例。

NeoAetherOS补原BV、作者与源码关联、中国工作室公开关系、桌面演示、四架构构建入口及许可证沿革。2025年的旧naos链接与2026年新建naos系统工程分别记录，当前内核快照位于na-kernel。

## 研究材料

- [光明、天工语及段言沿革](round-6-existing.md)
- [细雨言与入墨答历史资料](round-6-history.md)
- [Gitee／GitCode：道、CNSH、衍真](round-6-gitee.md)
- [Bilibili：华夏编程与轻语言](round-6-bilibili.md)
- [NeoAetherOS／na-kernel](round-6-kernels.md)
- [语程同名线索](round-6-yucheng.md)

## 协作与审阅

起始已读取根AGENTS.md、目录与第五轮日志、全部9个开放Issues及其评论；开放PR为0。已有研究按固定来源沿用。新增与完善资料采用贡献分支和PR提交，原有其他条目保持原有内容。

光明、天工语、段言及道、CNSH经独立资料审阅，五段代码逐字核对；入口引用范围据实际行号修订。原始资料中的性能、测试数量及自举完成度采用作者说明或待核实。入墨答原例及解释入口、细雨言更名公告、NeoAetherOS归属与拆分差异分别复核。适用检查覆盖资料格式、引用、条目ID、目录链接、完整变更及GitHub检查状态。

## 检索平台、时间范围与风险

平台轮换至Gitee和GitCode，配合GitHub、Bilibili、PyPI、CSDN和原作者官网。新项目检索重点2024—2026，既有历史项目回溯2011—2024。各分项日志保存实际关键词、日期、固定提交、短代码和视频时间点。

访问风险包括B站公开画面分辨率、旧博客缺失、CSDN推荐日期与首发日期混排、Gitee内容限制、GitCode缓存与实时页面差异，以及PDF源站超时。平台提示限制按当前公开范围处理；资料缺口采用待核实。

## 下一轮策略

新语言发现继续优先低关注度及视频项目，轮换GitHub单文件仓库、中文技术社区与历史目录。优先追查Issue #3中的ZW／ZLang／PYCH和其他初始候选、Issue #4的语程身份与如意III原例，以及Issue #5中的言语言固定源码与继承关系。内核继续推进KunOS和NeoRunST的公开归属及源码关系，并寻找其他小型个人公开视频项目。已收录条目的缺口按版本与证据逐项补齐。
