# YiYiYa / Issue #52 补查
核验时间：2026-10-12 04:25—04:31 UTC。本轮采用公开网页、GitHub固定源码与元数据静态核验，独立运行待核实。

## 筛选历史
- 研究起点为574d50b435fe327f9111abf02c696344f62ea3ae，发布基线为29b829eaafcd02ace3af7e6388ec0d9063efdf66，95语言／9内核。
- 根AGENTS要求肯定陈述、如实记录待核项，已读。
- 第16轮日志明确写：“JanSky520/MikuOS、OmegeUOS、YiYiYa和HelixOS按筛选线索记录。”
- 该日志深入对象为hudos；YiYiYa对应阶段为“已发现的筛选线索，独立整理尚未完成”。
- 历史固定链接：https://github.com/yuyan-lang/chinese-programming-languages/blob/574d50b435fe327f9111abf02c696344f62ea3ae/research/2026-10-10/round-16-kernel.md
- 新作者评论：https://github.com/yuyan-lang/chinese-programming-languages/issues/52#issuecomment-6117437906
- 评论作者evilbinary，原文：“YiYiYa 怎么没搜到，https://github.com/evilbinary/YiYiYa”
- 基线data/kernels.json中YiYiYa匹配数为0。

## 结果
按静态资料核验收录YiYiYa，22项一手来源保存在正式结构化条目，新增发现0项、既有线索核实1项。
- 主仓：265c8456d8699359ad626651515185fc3b82d176，提交2026-10-05T08:59:00Z。
- 主仓固定子模块：duck 84684a525fdc6b341d0ceb5e50a64eb7444caaad；app 3ea963906ce19f0aada1875249e8ed38f0593717；eggs 2f05996f61cb81666d6755f1b8a05e4222569233；foot 0a072408944e8d7a8a7e31a7565f77c0bb6ceb68。
- 作者原GitHub公开主页所在地为China，且置顶YiYiYa；仅按所在地自述记录中国关联，国籍待核。
- duck README明确“YiYiYa kernel”。kernel_init实际串联异常、页管理、系统调用、调度、模块、内存、VFS与线程；调度、内存、VFS、ELF32、FAT和AHCI实际代码已读。
- 简介与architecture.md的宏/微/混合定位及平台状态有差异。分别作为作者文档声明记录；独立运行待核实。
- 主仓LICENSE LGPL-2.1；duck LICENSE GPL-2.0。简介“GPL2.1”单独保留为文档差异。
- Releases集合4条均非draft、非prerelease；当前最新v1.4于2023-11-11T05:41:27Z，最早现存v1.1于2022-02-13T15:23:13Z。仓库created_at为2017-04-03T17:14:28Z；首次公开日期待核。
- kernel/loader.c本身是注册接口/默认占位；具体ELF实现核对modules/loader/elf.c，避免以占位文件误判整个加载器。
- schedule.c源码有共享内核栈限制、用户态边界切换及预抢占判断；完整服务隔离边界继续待核。

## B站与检索限制
普通网页实际query包括："YiYiYa" "bilibili"；"evilbinary" "中国"；"YiYiYa" site:bilibili.com/video；"evilbinary" "China"；"YiYiYa" "国产"；YiYiYa 哔哩哔哩 鸭；site:bilibili.com "YiYiYa"；site:evilbinary.org YiYiYa。
搜索结果噪声较多。全志在线社区用户文章给出FunKey介绍视频BV1at421A7mT，该文为第三方转载。链接：https://bbs.aw-ol.com/user/q1215200171/posts 。该转载作为进一步发现线索；作者归属与运行结果另按原始证据核验。视频 https://www.bilibili.com/video/BV1at421A7mT/ 与作者主页链接 http://evilbinary.org 本次web工具均无法访问。B站作者账号与固定版本在JSON中保持待核。
GitHub普通网页缓存显示旧子模块SHA，实际固定采用GitHub API返回的当前main提交及gitlink值。

## 独立复核与发布范围

独立重读作者主页、固定子模块gitlink、调度／内存／VFS／ELF32／驱动、许可及发布集合后，核对核心事实一致。发布稿采用以下精度完善：

- 加入作者在Issue #52推荐项目的原始评论；归属采用公开所在地China自述，国籍待核。
- 两份架构文档按文件名对应，文档年代比较待核。
- memory.c表述为分配接口及底层mm_alloc委托。
- ELF32路径处理ET_EXEC，PT_INTERP分支返回失败；动态解释器加载待核。
- 主仓与duck许可分别限定到各自LICENSE文件。
- README展示资源、源码可见与独立运行分层记录。

本批发布后内核目录10项，语言95项；Issue #52中的YiYiYa补充线索完成基本收录，MimicryOS与Causenix继续保留待核。研究与原始来源按上述范围归档。
