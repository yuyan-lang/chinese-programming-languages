# 第五轮 Bilibili 核验：子语与有限新线索

核验日期：2026-10-10（UTC）。研究时段约16:30—16:39 UTC。采用 GitHub 只读接口、公开网页搜索和 云端浏览器；原视频以关键段暂停检查。外部服务保持只读。本轮整理一项语言条目与两项待核实候选。

## 结果

- 建议新增子语1项。原视频、作者公开置顶、关联仓库中文原例和构建脚本形成来源链。
- Issue #11 的 BV1DwYc6iEKG 已识别为现有豫言。原片00:09显示“豫言”，简介链接 yuyan-lang.org。该子项按重复线索解决；豫言条目维持原样。
- 本轮有限新增候选2项：华夏编程、VCN／VcnStudio轻语言。二者已有原视频和发布账号，精确原例及实现关系仍待核实。
- BV1rFHn6JEBs 的原简介明确介绍玄铁并链接既有 XuanTie-Lang 主仓库，按既有项目传播资料处理。
- 另受托核看 OpenXJ380 原作者视频的一处 QEMU 演示，证据单独列在文末。

## 基线和防重

读取：
- [AGENTS.md](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/AGENTS.md)，SHA ab8038fa86c6ff04320372eea00cee9c5fd54cca。
- [data/languages.json](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/data/languages.json)，SHA 7327fbbfadf03c71b8ccb55b878766a6c33da0bf，46项。名称、别名和相关来源参与核对。
- [Issue #11](https://github.com/yuyan-lang/chinese-programming-languages/issues/11)及[Issue #16](https://github.com/yuyan-lang/chinese-programming-languages/issues/16)正文。
- [第四轮B站日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/round-4-bilibili.md)、[第四轮发现日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/round-4-discovery.md)。
- [第三轮B站日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/round-3-bilibili.md)、[第二轮B站日志](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/bilibili.md)。

子语在当前46项名称与别名中属于新对象。山雀按硬件／运行包关系写入同一条目。豫言及玄铁线索按已有项目处理。

## 子语：来源链

- 原片：[中文编程？不一样的体验！](https://www.bilibili.com/video/BV125up6eEdA/)。
- 发布账号：[抽空抽象抽象层，UID489636691](https://space.bilibili.com/489636691/)。
- 原简介写“显示屏打印功能演示”，带 ESP32、自然语言编程和中文编程标签。
- 同 UID 公开置顶评论给出 GitHub 仓库检索名 shanque_esp32s3，并称项目处于首批体验阶段。
- 精确仓库搜索取得 [liuzhiyixx/shanque_esp32s3](https://github.com/liuzhiyixx/shanque_esp32s3)，仓库描述为“山雀-中文编程代码库”。
- 固定 [README](https://github.com/liuzhiyixx/shanque_esp32s3/blob/15559af77adfc64e6ede4c907dd219fa5603163f/README.md)称其为“山雀 ESP32-S3 开发板的子语运行包”，用于编译和下载 .zhw 中文示例。核心教程也明确使用“子语”名称。

### 日期与版本

- 仓库 created_at：2026-07-08T09:46:10Z。此字段为仓库创建时间。
- 默认分支提交列表返回8项，最早提交 ef5ce5b94d5a362c7578e8c91535525ecc96224b 的作者时间为2026-07-08T10:32:56Z、消息为 first commit。
- 已读取该最早提交的[中文循环示例](https://github.com/liuzhiyixx/shanque_esp32s3/blob/ef5ce5b94d5a362c7578e8c91535525ecc96224b/中文示例/08_加入循环让按键1控制蓝灯.zhw)，包含“从…中引入”“循环以下内容”“如果”“直到”等语法。该证据说明当前历史最早提交已保存中文源程序。
- 原片 video:release_date=2026-08-06T12:49:28.000Z；北京时间2026-08-06 20:49:28。浏览器客户端显示05:49:28，记录采用带Z元数据。
- 核验 main 提交15559af77adfc64e6ede4c907dd219fa5603163f，时间2026-08-15T08:33:29Z。
- 运行包的插件文件为 zi-yu-0.0.7.vsix。0.0.7 按插件版本记录；语言版本待核实。
- Releases接口返回空数组。语言的首次公开日期仍待原作者更早发布材料确认。

### 原片关键时间点

总长02:15，均在精确原BV内定位并检查播放器时间：

- 00:11：编辑器打印语句画面。
- 00:41：编辑器出现中文“打印”和文本内容。
- 01:33：可辨“组合名字、年龄成小明”、带实词槽的“长大…岁”句式和成员赋值；同画面硬件屏幕显示“小明现在18岁”。
- 02:05：可辨“复制小明成张三”“张三长大3岁”以及打印语句。

原片文字较小，条目完整代码采用仓库固定文件原文。视频用于核定演示内容与时间点，硬件运行与构建可复现性待独立验证。

### 精确中文短例

固定[08_加入循环让按键1控制蓝灯.zhw第1—5行](https://github.com/liuzhiyixx/shanque_esp32s3/blob/15559af77adfc64e6ede4c907dd219fa5603163f/中文示例/08_加入循环让按键1控制蓝灯.zhw#L1-L5)：

```text
引入山雀开发板.zhw。

循环以下内容：
如果按键1按着：蓝灯点亮。
直到0。
```

文件 blob SHA：195ac7ae09a3d86e0ae6b2061d3aaf071c394ea2。保留中文标点及空行，末尾教程评论省略。

另读取：
- [18_子语核心.zhw](https://github.com/liuzhiyixx/shanque_esp32s3/blob/15559af77adfc64e6ede4c907dd219fa5603163f/中文示例/18_子语核心.zhw)：整数／小数／文本实词，复制、组合、成员访问、句式与语句、如果和退出。
- [19_子语核心_引入实词和使用语句.zhw](https://github.com/liuzhiyixx/shanque_esp32s3/blob/15559af77adfc64e6ede4c907dd219fa5603163f/中文示例/19_子语核心_引入实词和使用语句.zhw)：引入实词和按实词类型匹配句式。
- [17_按键1控制成流水灯_人话版.zhw](https://github.com/liuzhiyixx/shanque_esp32s3/blob/15559af77adfc64e6ede4c907dd219fa5603163f/中文示例/17_按键1控制成流水灯_人话版.zhw)：中文条件、否则、退出及循环。

### 实现核验

固定递归树返回186项，truncated=false。

[tools/build.ps1](https://github.com/liuzhiyixx/shanque_esp32s3/blob/15559af77adfc64e6ede4c907dd219fa5603163f/tools/build.ps1)：
- 第62行说明命令行解析器名 ziyu_cli.exe 及 ziyu_parser 来源名称。
- 第580—589行组织入口和 --build-dir 参数并调用解析器。
- 第591—604行同步生成的 .c/.h，建立 ziyu_generated_main 入口。
- 第633—659行以 ESP-IDF esp32s3 目标构建 app。
- [app_main.c](https://github.com/liuzhiyixx/shanque_esp32s3/blob/15559af77adfc64e6ede4c907dd219fa5603163f/idf_project/main/app_main.c)调用 zy_esp32_runtime_start(ziyu_generated_main)。
- [运行时头文件](https://github.com/liuzhiyixx/shanque_esp32s3/blob/15559af77adfc64e6ede4c907dd219fa5603163f/runtime/board_esp32s3/include/zy_esp32_runtime.h)提供硬件及运行时接口，仓库树另列预编译静态库。

GitHub 仓库精确搜索 ziyu_parser 返回空数组。解析器完整来源、运行时内部实现、插件与源程序对应性、许可和 AI 参与均待核实。README 的构建时长和硬件能力按作者资料理解，独立执行与性能结论待核实。

## 两项新候选

### 华夏编程

- 原片：[我用中文写了代码，还做了个游戏](https://www.bilibili.com/video/BV1NKH466EFB/)。
- 账号：[华夏编程-官方，UID3493272276175446](https://space.bilibili.com/3493272276175446/)。
- video:release_date=2026-10-05T13:07:27.000Z，北京时间21:07:27。
- 原简介正式命名华夏编程，称做了一个月，并列出设、输出、如果、循环、函数，及游戏、网络、文件读写等能力。
- 00:04可见游戏窗口及绿色竖条；00:13、00:33、00:42为编辑器、说明字幕和中文快捷输入按钮。完整用户程序的精确字符与时间点待核实。
- 原简介的下载字段为“你的链接”占位；同 UID 公开置顶另提供新版网盘地址，另一条作者评论称旧版因严重缺陷下架。网盘内容与有效版本待核实。本轮保留入口于pending JSON，保持原链接原样，未下载或执行。
- 同作者[安装使用教程BV1Gtpg65EfU](https://www.bilibili.com/video/BV1Gtpg65EfU/)来自推荐位，是下一步可直接核看的来源。
- GitHub精确检索“华夏编程”返回空数组。
- 原简介自述含编译器、断网可用；实现架构、源码、许可、AI参与及同源关系待核实。

### VCN／VcnStudio轻语言

- 原片：[AI/中文编程/VcnStudio 4.8.0/新版特性摘要](https://www.bilibili.com/video/BV1SnY16wECF/)。
- 账号：[VCN中文编程，UID330302804](https://space.bilibili.com/330302804/)。
- video:release_date=2026-09-14T09:40:44.000Z，北京时间17:40:44。
- 00:34展示移动端可视化布局；00:53、00:59展示主窗口.spl中文事件代码和AI助手，可辨“事件”“结束 事件”等词。
- 原简介自述增加面向对象语法、增强变量及匿名参数类型推断，并把AI助手输出称为“自研轻语言代码”。核心实现、上游关系及精确原例待核实。
- [E4A官网友情链接](https://e4asoft.com/lists/16.html)指向[www.vcnstudio.com](https://www.vcnstudio.com/)。公开网页抓取超时，云端浏览器返回502 Bad Gateway及Connection refused，官网文档在本轮未取得。
- 原片显示13条评论，未登录可见部分围绕图标和免费使用。完整讨论待核实。
- GitHub精确搜索“VcnStudio”返回空数组。
- VcnStudio按IDE／平台名称记录，当前原作者语言名为轻语言。平台早期语言扩展与当前轻语言的沿革、正式命名、发行、许可及首发日期继续核验。

两项均保持待核实候选。首次发现本轮资料的日期与项目首次公开日期分别记录。

## 实际检索平台、关键词和窗口

### GitHub

读取百科基线、研究日志和两项Issue正文；读取山雀仓库README、完整递归树、默认分支提交列表、最早与当前固定原例、构建脚本、C入口和运行时头文件。

仓库检索词：
- shanque_esp32s3
- ziyu_parser
- 子语
- "华夏编程"
- "VcnStudio"

“子语”模糊检索主要返回句子语义、自然语言处理和教材等同名噪声；精确仓库名来自作者置顶，作为主要来源链。

### 公开网页搜索

执行的查询包括：
- site:bilibili.com/video "手搓" "中文" "编译器" 2025
- site:bilibili.com/video "AI" "中文编程语言" 2026
- site:bilibili.com/video "全中文代码" "自制"
- "子语" "山雀" 编程
- site:bilibili.com/video/ "手搓编译器"
- site:bilibili.com/video/ "AI写编译器"
- site:bilibili.com/video/ "全中文代码"
- "华夏编程" "语言"
- "VCN中文编程" "语法"
- "自制中文语言" bilibili 2024 2025 2026
- "VcnStudio" 官网
- "华夏编程" "github"
- VcnStudio 官方 网站 vcnopen
- "VcnStudio" "轻语言" 官网

### Bilibili站内

首屏查询：手搓编译器、AI写编译器、全中文代码、自制中文语言。直接核看指定两条BV，并从“全中文代码”首屏与玄铁视频推荐位选定VCN及华夏两项新候选。

研究目标窗口为2024—2026；本轮站内查询采用默认综合排序，网页查询部分显式带2024、2025、2026，没有统一开启严格时间过滤。候选日期按原页面带Z元数据核定。返回的教程、游戏物品代码、AI模型编译器、编辑器、英文语言和现有项目传播片分别筛查。搜索短日期只用于选择入口。

## 覆盖限制

- 公开搜索对新BV和项目名收录有限。“全中文代码”可命中游戏物品编号；“AI写编译器”可命中AI算子编译与写作内容；“自制中文语言”分词后有大量无关视频。
- B站采用各查询首屏及有限相关推荐。完整分页、所有作者投稿及全部长视频仍属于后续覆盖范围。
- 未登录评论仅覆盖公开置顶与热评：山雀页面显示138条、华夏8条、VCN13条。完整评论、群文件和私域资料待核实。
- 播放器关键段抽查采用360p可用画面；低清、长行和字幕影响逐字转录。子语以固定源码作为精确例文，两个新候选保留原例待核实状态。
- 视频发布时间存在服务器首屏、客户端和带Z元数据的时区展示差异；本记录采用带Z值并换算北京时间。
- VCN官网502属于本轮连接失败；其当前可访问性和文档内容待核实。
- 下载包和预编译库内部内容、实际构建、硬件烧录、性能、兼容性及运行结果保持待核实。
- 研究过程中保存的是来源和关键帧观察记录；截图在浏览器工具结果中可见，本次未交付独立截图文件。

## 附：OpenXJ380原视频辅助证据

受托补看[原片BV1ku376JE2h](https://www.bilibili.com/video/BV1ku376JE2h/)，账号人朝的小郭同学（UID1591866703），video:release_date=2026-07-26T05:48:44.000Z。

01:10暂停画面显示“QEMU - Press Ctrl+Alt+G to release grab”窗口，内部为中文控制中心、系统信息、设备规格和右下角日志；产品行可读“XJ380 操作系统”，版本数字可读2.1.0。版本前三个字母在低清画面中待核实。

原简介直接链接 https://github.com/xingji-studio/OpenXJ380，并说明4月前手写及原视频已换源。此处按原作者QEMU演示记录。当前源码对应性与独立运行由内核研究单独核验。

