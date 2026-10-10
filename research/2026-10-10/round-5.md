# 第五轮：中文工具链、历史语言与小型内核

核验日期：2026-10-10（UTC）。起始提交：ac3ac325174116c0dc44f8e836ab4a52ab31e4ad。

## 结果与计数

- 语言新发现3组：自然派、华夏编程、VCN／VcnStudio轻语言。自然派达到收录资料条件；另2组进入[Issue #19](https://github.com/yuyan-lang/chinese-programming-languages/issues/19)。
- 已有[Issue #16](https://github.com/yuyan-lang/chinese-programming-languages/issues/16)中4组完成分类收录：ChinesePython（YoloLogic，合并Linux平台线）、ChineseTypeScript、Sheng（结绳）、子语（对应BV125up6eEdA）。SPCNYY补充Windows/Linux内嵌模块一致性和替换语义，作者原始用户程序继续待补。
- 语言目录新增5项，编号lang-047至lang-051，总数46→51。
- 完善现有2项：奇语言lang-011、CNPL lang-018。
- 内核新发现2组：OpenXJ380与NeoAetherOS。OpenXJ380达到收录资料条件，目录5→6；NeoAetherOS进入[Issue #18](https://github.com/yuyan-lang/chinese-programming-languages/issues/18)。
- 合计新发现5组，新增正式条目6项（语言5、内核1），新待核实3组。正式条目包括本轮新发现2项及既有线索4项。
- [Issue #11](https://github.com/yuyan-lang/chinese-programming-languages/issues/11)中的BV1DwYc6iEKG完成去重，对应现有豫言lang-001；条目维持原样。

“核实”表示达到对应分类的资料条件。作者声明、固定源码、发行元数据、作者演示和独立运行分别记录，具体缺口见条目。

## 研究材料

- [ChinesePython与ChineseTypeScript](round-5-yolologic.md)
- [Sheng与SPCNYY](round-5-historical-and-layer.md)
- [子语与B站候选](round-5-bilibili.md)
- [自然派与社区检索](round-5-community.md)
- [奇语言与CNPL](round-5-existing.md)
- [OpenXJ380与NeoAetherOS](round-5-kernels.md)

## 协作与资料审阅

先读根AGENTS.md、目录、第四轮日志及全部开放Issues和评论；起始开放Issues为#1、#3、#4、#5、#11、#13、#16，开放PR为0。已有资料沿用固定来源，各项目按有限子项核验。研究通过贡献分支与PR提交。

ChinesePython与ChineseTypeScript经独立审阅，核对连续原例、实现路径、上游关系及标签与主分支差异。自然派经独立审阅，保留混淆实现与发行许可边界。Sheng原例对照PyPI作者页；奇语言、CNPL及子语原例逐字核对固定源码。OpenXJ380复核公开中国归属、启动与内核路径、第三方来源及版本字符串。视频稿件发布时间、当前换源画面与源码阶段分别记录，拍摄时间保持待核实。

## 平台与范围

本轮覆盖Bilibili、GitHub、PyPI、LINUX DO及Gitee/GitCode、V2EX、开源中国、CSDN的网页检索入口。新项目检索重点为2024—2026；历史回溯包括CNPL 2020年、Sheng 2021年和自然派2023年资料。关键词、原始URL、固定提交、视频时间点、实际访问限制和遗漏风险保存在分项日志。

## 下一轮策略

优先读华夏编程的原作者安装教程，取得清晰连续程序；VCN沿.spl事件代码和轻语言声明追查实现及平台沿革。继续处理SPCNYY作者原例和其他旧线索，轮换Gitee／GitCode原始仓库。已有薄弱语言优先光明、天工语、习语言及入墨答。内核继续核查NeoAetherOS公开归属、原片互链与na-kernel沿革，并沿既有Issue #13保存的KunOS、NeoRunST缺口有据推进。

主目录保存当前资料，研究日志保存本轮证据边界。后续源码与发行变化继续按日期及固定版本更新。
