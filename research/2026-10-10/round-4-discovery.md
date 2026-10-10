# 第四轮新仓库与辅助入口检索

核验日期：2026-10-10（UTC）。新线索汇总见 [Issue #16](https://github.com/yuyan-lang/chinese-programming-languages/issues/16)。

## 2026-10-10 第四轮发现

首批记录3项新增候选，后续按中文语法、实现及同源关系逐项分类。

### SPCNYY
- 原仓库：https://github.com/xs-smz/spcnyy-
- 创建时间：2026-08-15T16:42:42Z；核验提交：2d9087cade68fff2c966a7bf057141935b439ec0。
- 固定来源：https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh#L288-L310
- 安装脚本内嵌Python文件，language.py的映射包括“如果/否则/循环/定义/返回”等；translate按词长排序替换，再以正则处理计次循环。编辑器的运行入口把转换结果交给exec，界面称“中文编程翻译层”。
- 脚本另含Tkinter编辑器及DeepSeek助手接入；AI接口属于配套编辑功能，实际翻译流程需要分别核对。
- 待核实：作者认可的实际用户程序、名称沿革、版本、许可证、字符串与注释处理语义、Windows/Linux脚本对应性。
- 安装脚本包含桌面项目目录重建与依赖安装操作，本轮采用静态源码阅读。

### ChineseCpp（JinSuperOfficial）
- 原仓库：https://github.com/JinSuperOfficial/ChineseCpp
- 创建时间：2026-08-30T03:09:52Z；固定提交：739f835d2bb38202ec08c2cbf30793df152abb6a。
- README：https://github.com/JinSuperOfficial/ChineseCpp/blob/739f835d2bb38202ec08c2cbf30793df152abb6a/README.md
- 本次完整文件树含README.md与LICENSE两项。README将目标描述为中文编译器/头文件。
- 待核实：中文关键字、原始程序、实现发布位置、与其他ChineseCpp/Chinese++项目的关系。

### ChinesePython（YoloLogic，2026年项目）
- 原仓库：https://github.com/YoloLogic/ChinesePython
- 创建时间：2026-09-28T20:13:00Z；固定提交：ad29d1cddae32e8d7a550ba022471dfead835d9c。
- README：https://github.com/YoloLogic/ChinesePython/blob/ad29d1cddae32e8d7a550ba022471dfead835d9c/README.md
- README提供“导入/来自/定义/返回/使用/对于/属于”等中文短例，自述基于CPython 3.14.7；目录含bin、Lib、include、中文手册和发行材料。
- 关联候选：https://github.com/YoloLogic/LinuxChinesePython 。两个平台的同源和版本关系待核实，后续按同一项目关系整理。
- README同时列出项目许可、再分发条款与MIT说明，适用范围待核实。
- 待核实：作者与原视频身份链、解析器修改来源、语法映射及运行方式、发行版本、平台间关系、与2002年中蟒的项目沿革。现有中蟒lang-013资料单独保留。

## 检索记录

GitHub仓库搜索，2026-10-10执行：
- `"中文解释器" created:2024-01-01..2026-10-10`
- `"中文" "编译器" created:2026-01-01..2026-10-10 stars:0..3`
- `"中文关键字" created:2024-01-01..2026-10-10`

已读当前43项语言目录、现有研究日志和开放议题防重。范围聚焦低关注度2024—2026项目；检索返回的首屏、名称和README索引会影响覆盖。日期字段表示仓库创建，首次公开日期仍需原始发布材料。

## 同轮补充的3组入口线索

### ChineseTypeScript
- 原作者官网：https://logicyolo.com/chinese-typescript/
- 官网显示0.1及“如果、常量、字符串”中文例子，并声明以microsoft/typescript-go为底本。
- 作者关联页：https://logicyolo.com/about#%E4%BD%9C%E8%80%85 。官网明确署名YoloLogic，并链接同名GitHub账号。
- 待核实：完整语法、原始实现、版本与发行物、上游修改范围、平台关系。

### ChineseJava
- 原作者官网：https://logicyolo.com/chinese-java/
- 官网将项目记为计划中的OpenJDK方向，当前页面为占位与准备状态。
- 待核实：中文语法规范、原始实现、仓库、版本与发行物；按设计阶段线索记录。

### 未命名B站中文编程线索
- 原视频入口：https://www.bilibili.com/video/BV125up6eEdA/
- 搜索标题“中文编程？不一样的体验！”，账号抽空抽象抽象层（UID489636691）。
- 来自SZ语言原视频推荐位，本轮保留标题级证据。
- 待核实：原片、正式语言名、作者关系、中文语法及与现有项目的关系。

上述六组候选继续核验。ChinesePython作者与官网关系已由Chinese++原片、官网作者页及GitHub账号形成关联链；解析器来源、发行版本及许可范围继续核验。

## 同名历史语言：Sheng／结绳

- 作者发布页：https://pypi.org/project/sheng/0.1.18/
- 页面指向原仓库：https://github.com/luojiahai/sheng ，当前仓库及README请求返回404。
- PyPI署名luojiahai、维护者ljiahai，0.1.18发表于2021-11-15T13:43:30Z；说明采用Python与PLY，示例包含“甲 赋值 \"你好，世界！\"”及“打印(甲)”。
- 本轮将其作为独立身份链的历史语言候选保存；现有lang-012结绳中文对应tiecode.cn、Scave与MobileIPE。
- 待核实：原始源码或发行包、最早公开日、完整语法及版本沿革、与其他同名项目的关系。

本议题现记录7组候选，后续逐项补齐后通过PR收录或记录明确分类结论。
## 已取得完整条目的两项新发现

同一低关注度仓库查询发现[玄语](https://github.com/chy818/xuanyu)和[han-riscv](https://github.com/1913964829/han-riscv)。本轮分别完成固定源码、原例、作者、日期与版本核验，条目为lang-044、lang-045。详见[仓库核验](round-4-repositories.md)。

## 语程同名资料链

[yucheng-lang/yucheng](https://github.com/yucheng-lang/yucheng)创建于2026-05-18，固定提交a5de19574471ea41d0c399b06f6958ae8a746d64。[README](https://github.com/yucheng-lang/yucheng/blob/a5de19574471ea41d0c399b06f6958ae8a746d64/README.md)使用语程/YuCheng/YuProg/YCC名称，标注v0.4.1，示例含设、函程、如果、循环、返回。树中可见.程样例与库、平台二进制和VS Code插件。Rust实现与跨平台行为按README作者声明记录。

与[旭猜囱原片](https://www.bilibili.com/video/BV1EgKZ6VED9/)的关系待核实，已补入[Issue #4](https://github.com/yuyan-lang/chinese-programming-languages/issues/4#issuecomment-6099450503)。本轮按已有语程线索的同名来源补充记录。

## 查询覆盖

前三个GitHub查询分别返回0、30、7条结果；第二个查询达到请求的30条页容量。已筛查候选名称、README、固定树及现有目录关系。课程翻译、教程目录、学习游戏与同名无关仓库属于搜索噪声；后续可分页并轮换关键词继续扩大覆盖。当前检索集中2024—2026创建的仓库，早期项目和后期迁移仓库仍需其他时间窗口补充。
