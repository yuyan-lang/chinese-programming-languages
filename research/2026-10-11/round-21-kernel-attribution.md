# 第二十一轮：Issue #52 归属与 B 站原片有限复核

核验时间：2026-10-11 19:00:29—19:01:22 UTC。

## 结果

MimicryOS（Annihilation006）和 Causenix OS（FRCREEPER）继续保留待核候选。此次八条定向检索获得的有效归属声明及作者原片为0项；中国作者／中国社区的明确公开归属、原作者 B 站账号与原片继续待核实。该结果说明本批检索的证据缺口，作者国籍及全部公开网络覆盖仍待核实。

## 已读基线

- [根 AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/AGENTS.md)，返回 blob ab8038fa86c6ff04320372eea00cee9c5fd54cca。
- [Issue #52](https://github.com/yuyan-lang/chinese-programming-languages/issues/52) 正文及全部1条评论；状态 open。
- [唯一评论](https://github.com/yuyan-lang/chinese-programming-languages/issues/52#issuecomment-6111139811) 确认 PR #53 合并并链接固定资料。
- [第十八轮固定日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/e4044d517c1fc67d54c935d3bae05891886b9bae/research/2026-10-11/round-18-kernels.md)，返回 blob 923615ecaed9e6fb1430071285ce9f251f8cd160。
- 第十八轮35项原始来源（MimicryOS mi1—mi22；Causenix ca1—ca13）及搜索补充记录。技术证据沿用此前固定提交与静态研究；本批聚焦归属和作者原片。

## 实际查询及回执

19:00:48—19:00:57 UTC，普通公开网页检索第一批：

1. `"MimicryOS" "bilibili"`
2. `"Annihilation006" 中国`
3. `"causenix" "bilibili"`
4. `"FRCREEPER" 中国`

批量返回两个无关匹配：SilkSpawners 配置中的 FriendlyCreeper 别名 frcreeper，以及游戏卡牌页面拼接字符串 Annihilation006。两者与本次仓库作者之间的身份对应待核实，归属证据计入0项。

19:00:57—19:01:07 UTC，第二批：

5. `site.bilibili.com "MimicryOS"`
6. `site.bilibili.com "Causenix"`
7. `site.bilibili.com "Annihilation006"`
8. `site.bilibili.com "FRCREEPER"`

搜索服务返回若干站点限定范围之外的结果：已知什么值得买 AI 聚合页、causenix.com 企业 AI 服务页、上述同名误匹配及无关论文。有效 B 站账号或视频 URL 为0项。此次是公开搜索引擎检索，B 站全站内部搜索覆盖待核实。

相关回执来源：

- https://post.smzdm.com/p/a5rxv94x/ ：已知发现入口，页面标注 AI 生成；沿用第十八轮来源定位。
- https://github.com/mushroomhostage/SilkSpawners/blob/master/config.yml ：Minecraft 别名同名匹配。
- https://tcgbible-web-production.up.railway.app/yugioh/sets/battles-of-legend-chapter-1 ：卡牌文本拼接同名匹配。
- https://causenix.com/ ：企业 AI 平台服务名称同名匹配；与 FRCREEPER 的对应待核实。

19:01:07—19:01:15 UTC，直接尝试打开两个既有作者主页：

- https://github.com/Annihilation006
- https://github.com/FRCREEPER

两次均返回 Cache miss。本批当前主页内容待核实；第十八轮成功读取的简介／所在地字段为空观察保留原核验时间。

## 剩余缺口与范围

需要作者或所属社区的明确公开自述，以及能把仓库维护账号与 B 站作者账号对应起来的原始链接和原片。中文 README、QQ群入口、项目名称及其他网站同名各作为相应线索记录。

本批完成八条定向查询及既有主页核查。资料范围为公开页面与固定源码静态阅读；独立运行验证待核。后续优先依据作者或社区的原始发布与跨平台链接补齐归属。
