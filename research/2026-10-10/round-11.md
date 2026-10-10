# 第十一轮研究汇总

核验日期：2026-10-10（UTC）。基线：[b8bced915e093ccdfde6b32804f7bd2b4c6a0786](https://github.com/yuyan-lang/chinese-programming-languages/tree/b8bced915e093ccdfde6b32804f7bd2b4c6a0786)。

## 开轮检查

已读取根AGENTS.md、当前目录、71项语言与8项内核、第十轮日志、全部18个开放Issue正文和48条评论。开放PR为0。原有研究成果、别名、原仓、作者及视频入口用于排重。

## 数量与结果

- 新发现并深入2组：折言中文词元扩展、Rule DSL Core。前者1组完成分类收录，后者1组待核实。
- 旧候选转正式1项：PyCn（sunzi334481），来自Issue #22。
- 正式新增共2项，目录增至73项语言、8项内核。
- 已有语言完善2项：PythonCN lang-027、将军令lang-028。原有8条参考完整保留，新增17条。
- 旧标题入口补证2组：壬通中文C++保留待核；白易VC++完成中文API／类型别名库与Visual Studio插件的工具分类。
- 旧内核候选补证1组：Issue #29取得Halo OS画面名称及相关仓库候选。
- 本轮待核候选合计3组：新Rule DSL Core、旧壬通、旧Halo OS。正式条目和已核工具的待补字段分别保存。

## 正式分类与已有资料

1. lang-072 PyCn（sunzi334481）：Python中文方言／词元级转译层。固定6行阶乘原例、扫描和分层词表、CLI及导入器的compile／exec链、0.1.0与MIT已核。86个测试方法按静态测试源码记录，独立通过状态继续待核。
2. lang-073 折言（Origami中文关键字扩展）：历史默认启用的中文词元扩展，采用Go词法、AST与解释执行。2025-08-01固定源码在创建解析器前注册“函数／输出”，2025-08-15提交移除该主入口注册块；当前接口、当前文档和历史阶段分别记录。

PythonCN补全文本替换顺序、全角原例、创建与根提交日期及README许可声明；将军令补自有AST、调用环境、中文条件原例、MIT署名及返回传播／解析衔接边界。两项引用与原ID保留。

## 内核资料

[Issue #29](https://github.com/yuyan-lang/chinese-programming-languages/issues/29)的首发原片00:02清晰显示“Halo OS”。相关仓库bigbenben77/Halo-OS的README内容与视频接近，维护者身份互链继续待核。固定仓库含README及两项虚拟盘分发物；自身内核实现、源码、架构、许可与录像版本对应待核实。作者关于USB、网络、打包格式及三平台测试的说明单列为作者声明。后两条视频保留不同页面日期显示值，规范时区日期继续核实。

## 议题衔接

- [Issue #1](https://github.com/yuyan-lang/chinese-programming-languages/issues/1)：PythonCN与将军令完善。
- [Issue #22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)：PyCn完成分类，初始10组累计分类7组，余下XuYu、中文Rust设计、52zwbc中文CPython关联组继续核实。
- [Issue #29](https://github.com/yuyan-lang/chinese-programming-languages/issues/29)：Halo OS画面名、相关仓库及日期差异。
- [Issue #35](https://github.com/yuyan-lang/chinese-programming-languages/issues/35)：Rule DSL Core中文规则、原仓与Go包文档候选。
- [Issue #36](https://github.com/yuyan-lang/chinese-programming-languages/issues/36)：壬通语法待核与白易工具分类。

上述议题仍有明确待核事项，继续开放。

## 来源与研究记录

- [PyCn旧候选](round-11-pycn.md) · [字段待补](round-11-pycn-pending.json)
- [折言及Rule DSL Core](round-11-community.md) · [待补字段与新候选](round-11-community-pending.json)
- [PythonCN与将军令](round-11-existing.md)
- [白易与壬通](round-11-bilibili.md) · [壬通候选](round-11-bilibili-pending.json)
- [Halo OS补证](round-11-kernels.md) · [完整待核证据](round-11-kernel-pending.json)

## 覆盖与遗漏风险

本轮轮换V2EX、linux.do、知乎、CSDN、开源中国、学术关键词与历史目录，并沿原作者线索读取GitHub、Gitee及Go包目录。B站使用原片、作者频道、公开评论和官网链接。新发现目标2024—2026，历史项目和同名包按各自来源日期追溯。完整关键词、读取范围与时间窗保存在分项日志。

折言的默认中文注册有明确移除提交，历史能力与当前发行范围分别核验。Gitee部分固定文件读取失败，Go包索引与原仓版本对应继续待核。B站360P画质与登录层影响连续源码转录，日期元数据优先于页面本地时区显示。Halo同名仓库的内容相近只作关联线索，作者身份与源码来源保留缺口。中文类型名、库API和IDE功能分别分类。

## 审阅与后续方向

完整差异、固定来源、连续中文原例、JSON和条目ID、旧参考保留、详情页与来源链接共同核对。用户代码、编译器、安装器、镜像及测试均维持静态研究范围；运行正确性与兼容性单列待核。主页中文URL及内核路径沿用现有文字与href。

下一轮继续寻找2024—2026原作者静态资料，优先同名排重中出现的Vincent-the-gamer/pycn，以及社区标题中的实验语言入口。已有资料推进lang-029之后的薄条目；Issue #22剩余三组按可读证据选择。B站先查静态原例和公开清晰图，内核优先补原作者身份关联、架构与自身实现边界。
