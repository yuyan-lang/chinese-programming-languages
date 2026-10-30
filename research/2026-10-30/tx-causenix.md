# 2026-10-30 TX／FendOSPE产品边界与Causenix原件入口

基线`449956a66e3e8e3a791ebbe4e09376fd6c6254dd`，114语言、25内核。已读根AGENTS、2026-10-30快照中#32与#52正文及全部评论（分别2条、8条），并读取2026-10-25、2026-10-28对应研究与10月28日部署站回执。本工作树未设置`.agents/skills`。本轮新增研究2份，正式数据、内核详情及索引原样保留。候选执行、安装、构建、启动和挂载均为0。

## #32：FendOSPE的发行关系采用单独产品范围

通过正常只读HTTP取得[TX官网](https://txgzsgw.mysxl.cn/)，响应日期2026-10-30T12:07:31Z，HTTP200，131856字节，SHA256为`7907125cf63e37296476e896fcd2590da059282a8389c169f9f2c5738968facc`。网页将“VergeOS自研操作系统Beta版”作为单独产品段落，继续链接既有VergeOS公开分享页；FendOSPE另有独立下载段落和产品站链接。当前正文与直链集合中，VergeOS的内核技术原件入口继续待补。

本轮沿官网明确直链读取[FendOSPE产品页](https://fendospext.mysxl.cn/)，响应日期2026-10-30T12:07:59Z，HTTP200，119326字节，SHA256为`2419dedb05ae7a91a22c8463ff2bf0e0cd1aaa898797fe4a2a055ce3b3a86754`。页面的直接原文短引为：

> PE系统内核基于Win11PE系统

作者同时列Windows 10／11微软官方下载入口，并将FendOSPE作为PE产品介绍。该资料支持FendOSPE的作者声明层面分类：基于Win11PE的PE发行产品。发行物字节、上游组件版本、实际运行及源码范围继续待核实。

**对应议题子项边界：** FendosPE系统官方是原片发布账号，TX是其官网工作室名称，FendOSPE另有上述PE产品。主站将VergeOS Beta与FendOSPE分列。FendOSPE的Win11PE关系采用该单独产品范围；TX VergeOS的内核、固件服务、现成组件与界面层边界继续待核。VergeOS Open已完成正式收录；TX与NewEra Studio同名项目的合作／代码继承关系继续待核。

**最终建议：保持#32开放。** 本轮完成FendOSPE产品的作者自述发行关系限定。TX VergeOS的最小原件缺口为可静态解析的公开发行物，或能明确内核入口、资源管理与上游边界的原作者技术资料。完整历史、全部许可与独立运行按后续资料字段保存。

有实质增量的评论草稿：

> 本轮沿TX官网直链读取FendOSPE产品页，作者明确说明该PE产品基于Win11PE。TX主站将VergeOS Beta与FendOSPE分列，因此该Win11PE声明采用FendOSPE单独产品范围，VergeOS的自身内核与上游边界继续待核。VergeOS Open已收录；TX VergeOS仍需可解析发行物或明确核心实现的原作者技术资料，#32保持开放。来源、响应日期与SHA256见本次研究及关联PR；候选执行、安装、构建、启动和挂载均为0。

## #52：当前公开入口继续保存软件源阶段

通过GitHub connector读取[当前仓库元数据](https://api.github.com/repos/FRCREEPER/causenix)与[发行集合](https://api.github.com/repos/FRCREEPER/causenix/releases)。homepage仍明确为`https://frcreeper.github.io/causenix/`，pushed_at为2026-10-06T15:46:44Z，Releases为`[]`。

读取[作者公开部署首页](https://frcreeper.github.io/causenix/)，响应日期2026-10-30T12:07:32Z，HTTP200、4494字节，SHA256为`ab3f2a481b357d6c5cdf8fed671cc403eaf357e338b1083ffca582074e117f57`，与10月28日保存的首页字节摘要一致。网页唯一资料直链为manifest.json。

读取该[当前软件清单](https://frcreeper.github.io/causenix/manifest.json)，响应日期2026-10-30T12:08:00Z，HTTP200、839字节，SHA256为`6495fc6aeb9190c14c3054b42167e171d895af92c89de8887ccfadfaab621811`。清单列snake和conway两项应用ELF；其原件链接已见于旧研究。当前发布入口继续提供软件源资料，核心内核原件继续待取得。

**最终建议：保持#52开放。** MimicryOS已完成收录。Causenix最小缺口仍为可取得的自身内核实现／可解析发行物及系统上游边界。本轮保持正式条目原样，省略重复状态评论；17提交、作者仓库列表及已知404路径均未重复读取。

## 证据回执与动作边界

来源URL、选定响应头、长度、SHA256、直链集合、清单和仓库元数据见[tx-causenix-evidence.json](tx-causenix-evidence.json)。HTML原文、响应头与正文缓存位于`/tmp/kernel-source-check-20261030/`。回执仅保存公开响应头的必要字段。

Safari旧状态原样保留：此前`cua.getApp("com.apple.Safari")`调用未返回应用状态或审批文本，最终`aborted by user`，审批与动作结果仍属uncertain。本轮Safari、123pan及其他云盘访问、B站页面／API／CDN请求均为0。FendOSPE页出现的PE分享链接仅静态记录。本轮新增读取均已完成，无denied、pending或uncertain结果。网页提取器访问TX官网返回不可访问后，正常只读curl取得HTTP200；未遇权限拒绝。

本轮只编辑百科研究文件。PR #62取消、PR #76草稿及既有审批／B站风控边界原样保留；其他项目和整体国籍标准原样保留。本地提交供root整合，远端写入由root执行。
