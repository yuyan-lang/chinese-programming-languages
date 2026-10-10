# 第七轮普查汇总

核验日期：2026-10-10（UTC）。基线提交697f78bd2d10a85a0c0c8cce9444bf03bdbf415a。

## 范围与计数

开轮读取根AGENTS.md、55项语言目录、7项内核目录、第六轮研究日志、全部9个开放Issue正文与评论，以及开放PR列表（0项）。沿用既有证据并按项目、别名、原作者和源码关系查重。

- 新发现19组：语言及关联线索15组、内核线索4项。其中52zwbc的两个CPython仓库暂计1组关联线索，最终分组待核实。
- 本轮完成分类收录6项语言：新发现的PB、chinese-interpreter（ling0x）、龙语言（仍然）、灵创语言，以及旧Issue #3中的zwpy、智语言。核验指中文原例及资料证据层级成立；独立运行状态另行记录。
- 新发现中待核实15组：9项仓库语言、1组中文CPython关联仓库、1项B站中文编译器、4项个人内核。
- 已有正式条目完善2项：文语lang-019、灵语lang-020。
- 内核新增正式条目0项；QuantumNEC与racaOS取得固定内核源码和版本沿革，公开中国归属继续待核实。
- 合入后语言目录61项，内核目录7项。
- PYCH旧线索补充发行、标签与源码资产摘要；TRAE165813旧线索补充搜索索引中的作者介绍。两项计入旧线索进展。

## 正式资料

| ID | 名称 | 分类及证据 |
|---|---|---|
| lang-056 | PB（PengBooo） | Python中文语法转译语言；固定原例、实现、0.3.1发行 |
| lang-057 | chinese-interpreter（ling0x） | Rust微型解释器；中文声明／输出、pest语法与执行器 |
| lang-058 | 龙语言（仍然） | Rust实验性编译工具链；中文原例、寄存器IR、机器码、PE／ELF |
| lang-059 | zwpy（zw） | Python中文映射方案；固定文档与中文原例 |
| lang-060 | 智语言（cnzkai） | 中文语言规范；开发者指南与验收原例 |
| lang-061 | 灵创语言 | 中文语言生态；原视频、Rust解释器与C转译编译器 |

文语补充实际Compiler／VM执行链、精确关键词查询、协程接入待核点及版本差异。灵语补全递归原例、v1.0.0正式发行、词元转换及f-string／第三方库边界。原有参考链接全部保留。

龙语言的PE发射器按架构分为x86_64 PE32+路径与简化PE32路径；ELF按架构生成32／64位ET_EXEC文件。多目标、动态库与APK效果继续待独立验证。AI生成范围按原作者README及Cursor提交说明记录。

灵创的.lcc视频阶段与.cn Rust路线分别记录。Californium视频具有中文语法实证，独立项目身份及与周蟒zhpy的关系继续核实。

## 议题与资料位置

- [Issue #22：10组仓库及CPython候选](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)
- [Issue #23：4项个人内核候选](https://github.com/yuyan-lang/chinese-programming-languages/issues/23)
- [Issue #24：Californium视频与zhpy关系](https://github.com/yuyan-lang/chinese-programming-languages/issues/24)
- [Issue #3：zwpy、智语言与PYCH](https://github.com/yuyan-lang/chinese-programming-languages/issues/3)原19组中，完成分类收录累计8组，余11组继续核实。
- [Issue #1：既有条目完善](https://github.com/yuyan-lang/chinese-programming-languages/issues/1)保留其他历史字段的后续事项。
- [Issue #5：社区线索](https://github.com/yuyan-lang/chinese-programming-languages/issues/5)补充TRAE165813索引证据。

本目录的round-7-discovery.md、round-7-issue3.md、round-7-existing.md、round-7-bilibili.md及round-7-kernels.md保存检索过程和原始链接。对应pending.json保存完整候选记录与核验日期。

## 研究覆盖与遗漏风险

重点轮换GitHub低关注度2024—2026仓库、Bilibili原视频与Gitee原作者代码，辅以中文社区和技术团队网站。关键词覆盖中文关键字、中文语法、中文解释器、全中文、自制编译器、手搓编译器、AI写编译器、自制操作系统及具体作者账号。实际查询、时间范围、视频时间点与固定提交见各分项日志。

GitHub若干广查询达到100项首屏，后续优先按月份、低星及更窄词分页。B站搜索卡片仅作为发现入口；原片、动态、评论区和视频中代码仍有遗漏风险。Gitee公开代码区可读；受登录限制的提交详情留待核实。PYCH附件访问遇浏览器协议限制，静态源码正文继续待安全公开入口。TRAE原页直接访问超时，索引内容与当前正文的对应待核实。学术论文和历史资料本轮新增覆盖有限。

下一轮优先核实Issue #22中具有连续中文原例的微型项目，轮换Gitee／GitCode和历史资料；B站继续追踪同UID原理视频及发布动态。内核优先补作者明确归属、原片时间点及版本对应。

## 文档审阅

逐字核对所选中文原例，保留原例中的字符串。zwpy代码的“不能为负”为作者程序字符串，按原文保存。文档使用直接事实陈述和待核实状态。项目运行、二进制、性能及AI服务效果分别标明独立验证范围。

文语与灵语原有6条引用完整保留；其他原目录对象及豫言条目保持原值。主页中文网址与内核中文路径入口已复核。研究更新通过贡献分支及PR交付。
