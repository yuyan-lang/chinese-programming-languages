# 第九轮已有语言条目完善：基石与易码

核验日期：2026-10-10（UTC）。百科基线：d4b23b6fb82c695a34f600582a4fa6399c44fb89。范围为基石lang-023与易码lang-024，保留原ID、全部原有参考链接及已有资料中的有效信息。

## 开轮依据与核验方式

已读取百科根AGENTS.md、data/languages.json的两项完整对象、research/2026-10-10/round-8.md、Issue #1及#5评论，并读取Issue #5正文中易码2.0旧线索。公开文字采用肯定陈述，资料缺口标注待核实。此次使用GitHub公开只读资源及普通公开网页；语言程序执行、构建、编译器与安装包运行均列为待核实。各源码路径用于静态核定实际调用链。

- [根写作规范](https://github.com/yuyan-lang/chinese-programming-languages/blob/d4b23b6fb82c695a34f600582a4fa6399c44fb89/AGENTS.md)
- [第八轮汇总](https://github.com/yuyan-lang/chinese-programming-languages/blob/d4b23b6fb82c695a34f600582a4fa6399c44fb89/research/2026-10-10/round-8.md)
- [Issue #1](https://github.com/yuyan-lang/chinese-programming-languages/issues/1)
- [Issue #5](https://github.com/yuyan-lang/chinese-programming-languages/issues/5)

## 基石 lang-023

### 固定版本、作者与历史

当前master与v0.2.2标签均指向65bb012c1c5a07e21a081b4d33cc88f5ecc046cc；提交作者及提交者署名陈柏林，关联GitHub账号benxiaoniao，时间为2026-10-10T14:24:59Z。公开发布脚本的AUTHOR_NAME同为陈柏林。作者字段按公开署名记录。

仓库created_at为2026-09-05T01:30:49Z。当前CHANGELOG的0.1.0节标注2026-09-05并称首个对外发行版；条目按当前原作者回溯资料记录这一日期。原始首发公告、v0.1.0下载资产及更早公开记录继续待核实。

当前master历史仅一个无父提交。tools/publish_github.py明确采用导出快照、重新git init、创建孤儿提交并覆盖公开分支的发布方式。因此当前根提交表示本次公开快照，历史沿革由CHANGELOG、保留的Release及标签共同佐证。

- [当前提交](https://github.com/benxiaoniao/JISHI/commit/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc)
- [元数据](https://api.github.com/repos/benxiaoniao/JISHI)
- [发布脚本与署名](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/tools/publish_github.py#L1-L72)
- [首发回溯记录](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/CHANGELOG.md#L3470-L3509)

### 当前执行链与实现边界

1. frontend/src/tokenizer.rs的关键字表包含令、如果、循环、函数、返回、类、尝试等；原始完整例子取自examples/01_猜数字.jsh（20行，保留注释、空行、全角冒号及最终输出）。
2. rust/src/main.rs的普通文件入口调用run::main_cli；run.rs读取.jsh源码，parser::parse得到AST，compiler::compile_program产生字节码，serialize::dump_json序列化，再load_module载入Rust VM并vm.run。该链路完整存在于固定源码。
3. Rust树遍历参考执行器通过--walk读取AST JSON，调试器/DAP当前使用树遍历执行器。源码明确记录字节码VM/CVM调试钩子的迁移状态，因此条目分别描述普通运行与调试路径。
4. cvm/src/jsvm.c保留C栈式虚拟机，头文件的JSVM_ABI_VERSION当前为2。JsHost提供宿主语义回调；oracle/jishi/cvm_bind.py负责ctypes加载、字节码扁平数组和Python宿主回调；examples/embed/hello.c展示C宿主执行常量42的字节码。README称Rust与C为两套正式实现；资料将独立C引擎及Rust默认发行链分列。
5. tools/build_release.py默认engine为rust，_build_rust_into调用cargo并将产物复制改名为bin/jishi；.github/workflows/release.yml显式传--engine rust。Python构建脚本与参考判据属于开发期链路。
6. wasm/Cargo.toml依赖同仓jishi-ffi及jishi-frontend；wasm/src/lib.rs通过裸C ABI与手写JS胶水调用同步沙箱。WASM的循环步数预算和原生沙箱超时分别记录。

- [完整中文原例](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/examples/01_%E7%8C%9C%E6%95%B0%E5%AD%97.jsh)
- [中文关键字](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/frontend/src/tokenizer.rs#L20-L32)
- [源码主执行链](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/rust/src/run.rs#L136-L206)
- [CLI与树遍历入口](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/rust/src/main.rs#L397-L538)
- [Rust VM](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/rust/src/lib.rs#L1805-L1875)
- [当前调试器边界](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/rust/src/debugger.rs#L1-L40)
- [C VM ABI](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/cvm/include/jsvm.h)
- [C实现](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/cvm/src/jsvm.c)
- [Python参考宿主绑定](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/oracle/jishi/cvm_bind.py)
- [C宿主示例](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/examples/embed/hello.c)
- [发行构建函数](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/tools/build_release.py#L187-L308)
- [Release工作流](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/.github/workflows/release.yml)
- [WASM入口](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/wasm/src/lib.rs)

### 迁移、发行、许可与AI声明

CHANGELOG记录2026-10-08 R8.4b-2将Python／Node实现移至oracle/jishi与oracle/node，退役对外分发与安装入口；pyproject.toml的project.scripts为空表。2026-10-09版本记录标为0.2.2。GitHub Release的published_at为2026-10-10T15:55:49Z，draft=false、prerelease=false；两类日期分开保存。

v0.2.2资产：
- jishi-0.2.2-linux-x64.tar.gz：2,688,075字节
- jishi-0.2.2-macos-arm64.tar.gz：2,540,508字节
- jishi-0.2.2-windows-x64-setup.exe：4,243,891字节
- jishi-0.2.2-windows-x64.zip：2,722,697字节
- SHA256SUMS：463字节

以上为Release元数据核验，资产实际下载、安装与校验和复算待核实。frontend版本0.2.2；rust的jishi-ffi与wasm的jishi-wasm版本均为0.1.0，按组件编号与语言发行版本分列。

根LICENSE是MIT No Attribution（MIT-0），版权署名为2026 jishi contributors。CHANGELOG在0.2.0节记载由Unlicense调整为MIT-0。README声明作者使用大模型帮助实现软件；具体模型、生成比例及人工改动范围待核实。AI相关源码提供语言卡、机器可读规格、结构化结果、MCP与沙箱接口；日常运行的词法、语法和VM入口已静态核对。

- [0.2.2正式发行](https://github.com/benxiaoniao/JISHI/releases/tag/v0.2.2)
- [发行元数据](https://api.github.com/repos/benxiaoniao/JISHI/releases/tags/v0.2.2)
- [标签固定提交](https://api.github.com/repos/benxiaoniao/JISHI/git/ref/tags/v0.2.2)
- [0.2.2与退役记录](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/CHANGELOG.md#L55-L124)
- [Python参考分发配置](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/pyproject.toml)
- [当前许可](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/LICENSE)
- [AI开发声明](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/README.md#L579-L583)
- [MCP实现](https://github.com/benxiaoniao/JISHI/blob/65bb012c1c5a07e21a081b4d33cc88f5ecc046cc/rust/src/mcp.rs)

### 资料差异与剩余缺口

README开头已更新为Rust／C正式实现，后半“架构与数据流”仍保存Python默认执行器描述；rust/README.md仍保存先用Python生成字节码、14模块等早期阶段说明；examples/embed/README.md写ABI v1，当前头文件为v2。条目采用最新实际源文件、发行脚本与明确日期阶段记录。README测试数3404、速度倍数、跨引擎逐字节一致等为项目自述，独立执行与性能复现待核实。

原有2026-10-09核验所用491733465dadd79fa82cbf9fb01b60ee2ddf214c的README、rust/Cargo.toml及仓库元数据3条参考完整保留。当前description为334字，代码改为完整原始程序。

## 易码 lang-024

### 当前固定版本、署名与发行

当前main固定提交de50f04b0211daa3c4401c4610c83dbcc1060e0e，提交时间2026-02-25T08:52:18Z。VERSION为1.0.0，README标注v1.0稳定期及核心语法冻结。易码.py头部和NOTICE均署名景磊，入口文件列出Jing Lei。根LICENSE为Apache License 2.0，NOTICE另保留版权、归属及商标说明。

GitHub Releases返回一项正式发行：标题“易码编辑器”，标签“中文编程语言”，published_at为2026-02-25T09:01:29Z，draft=false、prerelease=false，标签指向当前de50f04提交。Windows资产名为-windows-v1.0.exe，64,369,455字节。资产元数据与源码版本分开记录；实际下载、安装、运行及二进制内容校验待核实。

- [当前固定提交](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/commit/de50f04b0211daa3c4401c4610c83dbcc1060e0e)
- [VERSION](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/VERSION)
- [README](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/README.md)
- [源码署名](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/%E6%98%93%E7%A0%81.py#L1-L12)
- [NOTICE](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/NOTICE)
- [LICENSE](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/LICENSE)
- [发行页](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/releases/tag/%E4%B8%AD%E6%96%87%E7%BC%96%E7%A8%8B%E8%AF%AD%E8%A8%80)
- [发行元数据](https://api.github.com/repos/jinglei88/Yima---Minimalist-Chinese-Programming-Language/releases)

### 中文原例与实际执行链

采用示例/欢迎.ym第1—28行的完整程序，覆盖输入、赋值、条件、列表遍历、函数、当循环和模板字符串。展示文本移除开头UTF-8 BOM及文件末尾空行，其余字符、注释、emoji及缩进保留。源文件末尾附加空行对程序内容无影响。

易码.py第108—119行展示：词法分析器(代码)→分析()→语法分析器(tokens)→解析()→解释器.执行(语法树)。yima/解释器.py第2128—2149行按AST节点类型查找“_做_”方法，并遍历程序节点的语句列表，属于树遍历解释执行。架构文档说明词法器以缩进／退缩Token组织块，解释器通过环境.py的作用域链解析变量并处理返回和循环控制信号。

引入语句第2367—2418行依次查内置虚拟模块、.ym源文件、Python原生库；Python分支直接调用importlib.import_module。README记录.ym模块按绝对路径及修改时间缓存。GUI工具使用Tkinter；当前语言支持图纸对象、模板字符串、列表、字典、异常和模块等。

易码打包工具.py第530—581行生成Python启动器，该启动器寻找并读取包内.ym文件，执行同一词法、语法与AST链；打包工具再调用PyInstaller封装。源码执行链与应用分发形态各自记录。

- [完整中文原例](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/%E7%A4%BA%E4%BE%8B/%E6%AC%A2%E8%BF%8E.ym#L1-L28)
- [CLI主入口](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/%E6%98%93%E7%A0%81.py#L99-L123)
- [AST执行器](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/yima/%E8%A7%A3%E9%87%8A%E5%99%A8.py#L2125-L2149)
- [导入实现](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/yima/%E8%A7%A3%E9%87%8A%E5%99%A8.py#L2367-L2418)
- [打包启动器](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/%E6%98%93%E7%A0%81%E6%89%93%E5%8C%85%E5%B7%A5%E5%85%B7.py#L530-L581)
- [语言规范](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/%E6%96%87%E6%A1%A3/%E8%AF%AD%E8%A8%80%E8%A7%84%E8%8C%83.md)
- [架构设计](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/de50f04b0211daa3c4401c4610c83dbcc1060e0e/%E6%96%87%E6%A1%A3/%E6%9E%B6%E6%9E%84%E8%AE%BE%E8%AE%A1.md)

### 易码2.0旧帖与仓库时间线

1. linux.do原帖《闲的蛋疼，就用用AI编程做了一个中文编程语言玩。》显示作者jinglei（道友），首帖页面时间2026-02-20 17:33。该时间按页面显示保存，页面时区待核实。发帖者自述以AI辅助业余开发，展示易码2.0、.ym后缀和勇者大冒险RPG，语法含“说／让／问／结束”。
2. 当前仓库Git根提交7aa68b8f3f52bed963f2f9296d4a2ec3b3a61885的作者、提交者日期为2026-02-21T04:50:59Z，署名YiMa Developer，无父提交。根提交README展示“说／让／问／结束”；根提交词法器第16行附近有“语法2.0新增极简关键字”。
3. 根提交的示例/勇者大冒险.ym注释保留易码2.0称呼。其人物初值为血量100、攻击力15、金币30、药水数2；怪物名单为哥布林、骷髅兵、黑暗法师、毒蜘蛛、石头巨人、影子刺客。人物、怪物、战斗及商店与论坛原例形成内容对应；根提交程序部分句式已经改为“显示／完事”。这些证据支持原例和语法阶段的连续性。
4. GitHub仓库created_at为2026-02-22T08:06:28Z。Git提交日期与仓库创建日期各自保留，公开首发日期待核实。
5. 2026-02-23T08:22:08Z提交e51f8a50ab6abcdf60f24ef46b5dd03a52bc72af新增VERSION=1.0.0，将README阶段文字改为v1.0稳定期并加入冻结策略。
6. 2026-02-25发布Windows编辑器包。

当前规范以缩进、符号算术比较和官方关键词定义v1.0契约。历史2.0文字及语法与当前1.0.0分别保存，版本重编号的明确解释待核实。论坛jinglei与仓库jinglei88的显式身份互链继续待核实，因此论坛日期按相关历史线索保存。

- [论坛原帖](https://linux.do/t/topic/1631327?tl=en)
- [Git根提交](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/commit/7aa68b8f3f52bed963f2f9296d4a2ec3b3a61885)
- [根提交README](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/7aa68b8f3f52bed963f2f9296d4a2ec3b3a61885/README.md)
- [根提交词法器](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/7aa68b8f3f52bed963f2f9296d4a2ec3b3a61885/yima/%E8%AF%8D%E6%B3%95%E5%88%86%E6%9E%90.py)
- [根提交RPG程序](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/blob/7aa68b8f3f52bed963f2f9296d4a2ec3b3a61885/%E7%A4%BA%E4%BE%8B/%E5%8B%87%E8%80%85%E5%A4%A7%E5%86%92%E9%99%A9.ym)
- [确立v1.0冻结与VERSION的提交](https://github.com/jinglei88/Yima---Minimalist-Chinese-Programming-Language/commit/e51f8a50ab6abcdf60f24ef46b5dd03a52bc72af)
- [仓库创建元数据](https://api.github.com/repos/jinglei88/Yima---Minimalist-Chinese-Programming-Language)

### AI声明与浏览器覆盖范围

AI开发声明的当前原始证据来自论坛发帖者自述。当前README、NOTICE、语言规范、架构设计、开发指南及开发者教程的核验范围内，仓库作者相应声明、与论坛的显式互链、具体模型与生成比例继续待核实。

先检查公开网页浏览器状态，再使用公开网页浏览器读取论坛首帖及主题统计。主题显示22帖、1个链接；搜索索引覆盖至第19楼，其中第15楼链接wenyan-lang/wenyan。后段回复和个人资料读取发生浏览器协议超时，完整账号互链核验继续保留。论坛源码所示语法与现存根提交的内容比对已完成；身份归属、首发和版本重编号列为后续缺口。

易码原有固定README、词法分析.py及仓库元数据3条参考完整保留。当前description为347字，代码改为28行连续完整原例。文档列出的131个内置功能、回归结果与性能数字按作者资料保存，独立测试待核实。

## 检索与接口边界

- GitHub读取：百科根规范、目录及第八轮汇总；Issue #1／#5评论、Issue #5正文；两个原仓元数据、分支、固定文件、递归目录树、提交、发行及标签。
- 基石来源优先级：当前CLI与VM源码、正式构建脚本、Release元数据；README历史段按相应阶段引用。
- 易码来源优先级：当前VERSION与规范、入口及解释器、Git历史补丁、原始论坛。
- 初始尝试百科round-8-summary.md返回404，随后从已读目录树定位并读取实际round-8.md。
- GitHub /tags集合通过所用读取接口返回路径不支持；改读已知v0.2.2的git/ref/tags/v0.2.2，成功取得固定提交。该情况属于读取接口范围。
- 编译、程序执行、安装包解压或运行、性能和完整跨引擎测试均留作独立复现字段。

## 交付与审阅

round9-existing.json为两个完整对象数组，ID分别为lang-023与lang-024。两对象合计原有6条参考链接的标题和URL完整保留。新增引用以固定提交、原始发行或原帖为主。基石原例20行、易码原例28行均来自相应固定文件；易码仅做BOM及末尾空行展示处理。

两项已有条目完善计数为2；新增语言计数为0。Issue #1可记录本轮两项完善；Issue #5可记录易码的旧RPG／语法衔接、2.0至v1.0文档时间线，以及继续待核的账号互链、首发和重编号说明。原议题其余线索保持原研究范围。

