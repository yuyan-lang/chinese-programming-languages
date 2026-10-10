# 第十五轮研究记录

核验日期：2026-10-10。研究窗口：21:30—21:46 UTC。起点提交：[757ddd0d875cb114b7261e389aa9a8a002f86c80](https://github.com/yuyan-lang/chinese-programming-languages/tree/757ddd0d875cb114b7261e389aa9a8a002f86c80)。

## 结果
- 真正新发现并深入记录6项：csg、Zechariah、calvinwilliams/zlang、知语言、zyw98020的Z语言、HanOS。
- 正式语言条目新增6项：前述4项新发现，加旧候选LightLang（NomiLight2026）与壬通。
- 新待核候选2项：[Z语言 #45](https://github.com/yuyan-lang/chinese-programming-languages/issues/45)、[HanOS #46](https://github.com/yuyan-lang/chinese-programming-languages/issues/46)。
- 完善既有正式条目2项：文言lang-003、言序lang-007；保留原JSON和详情页全部5条旧引用，补入36条新引用，最终共41条。
- 旧待核飞鱼补齐UTC发布时间与Vue运行演示观察，继续沿[Issue #33](https://github.com/yuyan-lang/chinese-programming-languages/issues/33)。
- 语言目录80→86项；内核目录9项。汉源码及其余搜索级名称保存在初筛日志，另行计数。
- 壬通保存两张原片截图及SHA-256，单行“返回 0;”按局部语法原文展示。

## 启动检查与协作
已读根AGENTS.md、根目录、当前语言与内核资料、前轮研究日志，核对全部24项开放Issues及63条评论；当时开放PR为0项。沿既有议题核对作者、仓库、BV与别名；LightLang的GitHub和GitCode合流历史按同一项目保存。原例、当前源码、作者演示与独立运行结果各自注明证据范围。

## 正式条目
| ID | 项目 | 中文语法与主要实现证据 |
|---|---|---|
| lang-081 | csg | 六项关键字字符串映射；Roslyn增量生成器；固定11行原例 |
| lang-082 | Zechariah | 21关键词、AST至JavaScript编译及逐行解释路径；固定8行原例 |
| lang-083 | LightLang（NomiLight2026） | Rust前端、LLVM IR、Clang与运行时；固定11行原例 |
| lang-084 | 壬通中文编程 | 作者视频558.450237秒第11行中文返回语句；C++诊断截图 |
| lang-085 | zlang（calvinwilliams） | C词法及解释执行、中英文词元映射；固定19行阶乘 |
| lang-086 | 知语言（知心编译器） | TCC衍生中文C方言、双编码词元；编译器源码连续20行 |

## 资料与搜索
- [既有条目补全](round-15-existing.md)
- [csg](round-15-csg.md)
- [Zechariah](round-15-qbr.md)
- [LightLang](round-15-lightlang.md)与[剩余字段](round-15-lightlang-pending.json)
- [Bilibili原片与截图](round-15-video.md)及[后续字段](round-15-video-pending.json)
- [Gitee与中文社区](round-15-discovery.md)
- [GitHub补充搜索](round-15-root-search.md)及[Z语言资料](round-15-root-pending.json)
- [HanOS内核调查](round-15-kernel.md)及[45项来源](round-15-kernel-pending.json)
- [独立审阅](round-15-review.md)

搜索轮换GitHub、Gitee、GitCode／AtomGit、Bilibili、CSDN、51CTO、V2EX、linux.do、TRAE社区和OSDev。主要窗口2024—2026；csg、文言和早期内核按原始历史追溯。各专项保存实际关键词、固定提交、日期、原例、来源及访问限制。

## 核验与保留
文言、言序、csg、Zechariah及LightLang的连续原例逐字核验；壬通截图逐字目视核验；Gitee两项固定源码和关键字逐项阅读。静态目录及资料一致性检查覆盖ID、字段、引用、代码范围、旧对象保留和中文URL。目标项目安装、编译、执行、性能、自举及硬件运行均列待核。

文言源码0.4.0与正式发行0.3.4分列；言序1.1.20及公共格式版本分列；LightLang GitCode历史与GitHub源码版本分列。许可采用原文件范围，AI工具标记与开发参与事实分层记录。HanOS的明确中国作者／社区归属为继续补证事项。

## 遗漏风险与下一轮
搜索引擎索引、低关注仓库、未索引动态和评论仍有覆盖缺口。360P视频小字限制可靠转录；登录限制处保留待核。仓库创建、Git提交、版权年份、作者文稿时间与首次公开日期分别记录。重名项目按作者与原仓消歧。

下一轮优先核对Z语言固定实现、汉源码原仓及GitHub搜索级微型项目；继续B站飞鱼、Californium-252等旧视频原例；完善已有介绍稀疏条目。内核沿HanOS及既有中国归属缺口推进，以明确原作者证据作为正式收录依据。
