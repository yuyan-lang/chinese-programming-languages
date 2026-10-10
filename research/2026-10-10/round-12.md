# 第十二轮研究汇总

核验日期：2026-10-10（UTC）。基线：[9776f45bed00a6f1c9a594eb8142dd5b4428095d](https://github.com/yuyan-lang/chinese-programming-languages/tree/9776f45bed00a6f1c9a594eb8142dd5b4428095d)。

## 开轮检查

已读取根AGENTS.md、当前目录、73项语言与8项内核、第十一轮日志、全部20个开放Issue正文和53条评论。开放PR为0。按原仓、作者、别名、BV及项目关系排重，沿用已有背景和待核记录。

## 数量与结果

- 真正新发现并深入2组：hscript-c、CoreZ-OS。hscript-c完成分类收录；CoreZ-OS保留待核。
- 旧背景首次深入并转正式2项：PyCN（Vincent-the-gamer）、可执行考鼎码（EC2）。
- 正式新增语言共3项，目录增至76项语言、8项内核。
- 已有条目完善2项：NyaPlus lang-029、Nuzo lang-030。原6条参考及原代码保留，新增18条参考。
- 旧Issue #22中文Rust设计补证1组，核明设计与部分基础模块阶段。
- 本轮待核候选合计2组：新CoreZ-OS、旧中文Rust设计。正式条目的待补字段另行记录。

## 新条目与已有资料

1. lang-074 PyCN（Vincent-the-gamer）：Python中文方言／Rust AST源码转译工具链。固定7行质数函数、logos词法、自有AST、Python生成及PyO3执行已核。WASM和HTTP职责为转译接口。主干1.0.5与公开发行标签的7条提交差异单独记录，MIT许可、6条发行及日期已核。
2. lang-075 hscript-c：Haxe风格嵌入式脚本语言／中英双语前端。低关注B站原片直接链接原仓，22行中文类原例与C++扫描、解析和解释链可读。AI协作范围依据2026-07-08作者提交声明记录。注解及修饰词消费行为与运行语义分别描述。
3. lang-076 可执行考鼎码（EC2）：算法教学DSL／洛书派生解释实现。独立规范、8行算法入口及函数原例、C指令生成和VM执行、WASM接口已核。练习场AGPL与洛书核心MIT分层记录，旧demo与规范的用词差异保存待核。

NyaPlus完善输入正则驱动、逐行解释、宿主Java扩展、LGPL 2.1及日期；旧循环原例空白与赋值解析的衔接列待核。Nuzo重读原作者文章，补Apache 2.0声明及AI开发／人工架构说明，源码、发行与测试报告继续待核。

## 内核线索

[Issue #38](https://github.com/yuyan-lang/chinese-programming-languages/issues/38)记录新候选CoreZ-OS。原片简介直接关联lightfl0w/CoreZ-OS；固定源码具有x86-64独立内核链接目标、BIOS／UEFI入口、任务及用户态路径。01:01原片可见终端和几何绘图窗口，按作者演示记录。中国开发者或中国社区的明确公开归属、视频日期规范值及录像对应版本继续待核实。

## 既有议题

- [Issue #1](https://github.com/yuyan-lang/chinese-programming-languages/issues/1)：NyaPlus与Nuzo资料完善，后续薄条目继续推进。
- [Issue #22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22)：中文Rust设计的固定树81项、51文件。cn_types／cn_config有基础实现，12个其余crate声明的51个外部模块对应文件为缺失状态；CLI打印版本。连续中文用户程序原例继续待核。初始10组累计分类7组的状态保持。
- [Issue #38](https://github.com/yuyan-lang/chinese-programming-languages/issues/38)：CoreZ-OS待核证据与后续清单。

以上议题有明确剩余事项，继续开放。已有成果与原有参考保留。

## 分项记录

- [PyCN（Vincent-the-gamer）](round-12-vincent.md) · [条目待补字段](round-12-vincent-pending.json)
- [hscript-c与考鼎码](round-12-discovery.md) · [条目待补字段](round-12-discovery-pending.json)
- [NyaPlus与Nuzo](round-12-existing.md)
- [中文Rust设计](round-12-chineserust.md) · [旧候选补证](round-12-chineserust-pending.json)
- [CoreZ-OS](round-12-kernels.md) · [完整待核资料](round-12-kernel-pending.json)

## 检索覆盖与遗漏风险

本轮重点轮换B站公开搜索、原片简介与频道，再沿原仓读取GitHub、Gitee入口和TRAE社区。关键词覆盖“手搓编译器”“AI写编译器”“自制脚本”“中文解释器”“中文关键字 继承”“手搓内核”“AI操作系统”及作者／项目精确词。发现目标为2024—2026；历史和同名项目按原始时间追溯。各项日志保存实际检索词、覆盖范围和固定提交。

低关注视频索引、B站360P画面、评论可读范围、客户端日期差异、网站可达性及旧缓存构成遗漏风险。PyCN发行时间采用当前GitHub API，旧缓存日期另存待核。EC2规范与源码、CoreZ README与较新调度实现分别按固定快照记录。词元表、实际解析、作者演示和独立运行保持各自证据层级。

## 审阅与下一轮

已核对固定来源、连续原例、已有参考保留、分类关系、JSON／ID、详情页及链接。独立构建、安装、测试和运行结果继续待核；适用仓库检查与部署状态随关联PR记录。

下一轮优先核CoreZ作者关联中出现的微内核与编程语言背景入口，并轮换Gitee／GitCode和中文技术社区寻找低关注原例。已有条目从lang-031之后继续补全。中文Rust设计等待新的连续原例或转译模块来源，后续核验优先处理新增证据。
