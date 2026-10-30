# 已调查议题的公开证据归档

整理日期：2026-10-30。基线为`199fcbe395f2c89a1d6f4670da171292d452d44c`，114项语言、26项内核、13个开放Issues及两个既有开放PR。已重新读取根AGENTS、目录、本日与前轮研究日志、全部开放议题正文和82条评论，并核对main与两个既有PR。工作区及仓库未提供`.agents/skills`。

本轮依据2026-10-30新的处置要求，将已调查的可靠证据及待核实部分写入百科公开资料页。议题按已记录的调查结论处理，后续新证据可以补充页面并重开。材料状态、语言分类与核实程度按各字段明确记录。

## 公开范围

[资料目录](../../资料/index.html)提供13个议题资料页；结构化内容保存于[data/evidence.json](../../data/evidence.json)。语言首页、内核目录与仓库说明提供资料入口。复合议题的既有正式条目、范围分类及剩余候选分别列出，来源保存固定提交、原始URL、日期、短例及已有视频时间点。

| 议题 | 资料页 | 关键待核实部分 |
| --- | --- | --- |
| [#3](https://github.com/yuyan-lang/chinese-programming-languages/issues/3) | [首轮仓库项目](../../资料/issue-3.html) | PYCH作者中文程序；衍真直接原件与身份 |
| [#5](https://github.com/yuyan-lang/chinese-programming-languages/issues/5) | [Hanyu、无极与言叶等](../../资料/issue-5.html) | 无极、Wxe中文语法和程序；部分设计／历史关系 |
| [#16](https://github.com/yuyan-lang/chinese-programming-languages/issues/16) | [SPCNYY等七组](../../资料/issue-16.html) | SPCNYY连续中文程序及实现覆盖 |
| [#22](https://github.com/yuyan-lang/chinese-programming-languages/issues/22) | [太和、中文Rust等](../../资料/issue-22.html) | 中文Rust用户程序；52zwbc关联组保持原有待核与取消边界 |
| [#24](https://github.com/yuyan-lang/chinese-programming-languages/issues/24) | [视频编译器、天河与周蟒](../../资料/issue-24.html) | 视频compiler源码与具体继承关系 |
| [#29](https://github.com/yuyan-lang/chinese-programming-languages/issues/29) | [Halo两条发布身份](../../资料/issue-29.html) | B站与仓库的直接身份和版本对应 |
| [#31](https://github.com/yuyan-lang/chinese-programming-languages/issues/31) | [说了算与LightLang](../../资料/issue-31.html) | Saysuan Web原件及双端结果对应 |
| [#32](https://github.com/yuyan-lang/chinese-programming-languages/issues/32) | [TX VergeOS、FendOSPE及NewEra](../../资料/issue-32.html) | TX VergeOS自身内核、发行物与上游边界 |
| [#40](https://github.com/yuyan-lang/chinese-programming-languages/issues/40) | [玄与Lua中文版](../../资料/issue-40.html) | Lua中文版原始程序与语言改动 |
| [#48](https://github.com/yuyan-lang/chinese-programming-languages/issues/48) | [E#与CH-VM阶段](../../资料/issue-48.html) | 完整中文程序、实际语言前端与阶段关系 |
| [#52](https://github.com/yuyan-lang/chinese-programming-languages/issues/52) | [MimicryOS与Causenix](../../资料/issue-52.html) | Causenix自身内核原件与来源边界 |
| [#59](https://github.com/yuyan-lang/chinese-programming-languages/issues/59) | [博流与教材平台](../../资料/issue-59.html) | 品牌正式命名、教材语言与服务端实现对应 |
| [#63](https://github.com/yuyan-lang/chinese-programming-languages/issues/63) | [客舍论坛与仓库](../../资料/issue-63.html) | 账号身份互链及版本对应 |

本次新增公开资料组13项，新增资料目录页1项，覆盖83个证据对象与关联组件；新发现0项，新增待核候选0项，新增正式核实项目0项，正式条目内容完善0项。正式语言数据及114个详情页、内核数据及26个详情页保持基线字节；目录数量保持114语言、26内核。证据对象按资料关系拆分，存在同名、同作者多仓与版本分组，资料页数量与项目数量分别记录。

## 审阅与边界

四个sol子代理分别整理互不重叠的议题组，主任务集成并复核全部资料。贡献PR采用草稿开始，经来源、完整差异、结构、本地链接、适用CI及冲突检查，并由独立sol完整审阅。既有原始来源不可读时，保留历史读取日期与已发布研究；搜索缓存、作者声明和静态原件的证据层级分别标注。候选的运行能力与作者演示分别记录。

本轮不新增候选来源抓取。此前未取得的Lua手册正文、Saysuan Web原件和身份互链维持待核实。旧台账中的“保持开放”是各历史轮次的处置记录，本轮的资料归档和议题处置采用本页规则。

PR #62的取消合并、PR #76的缺源草稿、Safari审批结果不明及Bilibili访问拒绝边界继续保留。资料整理使用main上已有成果；取消或未核草稿的内容保持原状态。GitHub APPROVE提交次数为0；候选软件的安装、构建、启动、挂载及执行次数均为0。豫言条目、其他仓库及官网保持原样。

合并后的部署核验限定现有GitHub Pages自动构建与公开页面的只读检查。议题在公开资料上线后附上页面与关联PR，再按已归档的调查结论关闭。
