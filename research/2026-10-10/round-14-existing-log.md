# 第十四轮：Calculator.rs中文试验分支与玄铁资料完善

核验日期：2026-10-10。基线：[46734fc65a9a5da4cdc230c78c9f835134973e9a](https://github.com/yuyan-lang/chinese-programming-languages/tree/46734fc65a9a5da4cdc230c78c9f835134973e9a)。本项工作完善lang-033与lang-034，保持77项语言、8项内核的目录范围。

开轮已读取根AGENTS.md、data/languages.json中两条完整对象、research/2026-10-10/round-13.md、Issue #1及全部13条评论。Issue #1的逐条资料完善要求与后续评论的并行维护安排分别记录。本次只对两项研究交付作增补，原ID、原字段键和原引用前三项的标题、URL及顺序保留。


## 本项汇总

- 完善2项已有语言，新增语言0项、内核0项。
- 原有6条引用保持标题、URL与顺序；新增35条，合计41条。Calculator.rs由3增至21，玄铁由3增至20。
- 两段原代码及原code_source完整保存在下文；新例均来自固定源码，分别为8行和10行的完整连续原例。
- 两对象全部原字段键保留，code_context、许可与AI说明已补。简介正文分别含238和226个汉字。
- 公开材料的AI比例、自举一致性和性能归属作者声明；独立运行证据继续待核实。

## Calculator.rs（lang-033）

### 已核事实

- 作者署名为BHznJNs。Bilibili原演示页面索引显示同名发布账号、2023-07-19 11:35:20及指向Chinese-test的源码链接。
- 中文词表共有18项，组成九对中英文词元：“输出/out、循环/for、若/if、跳过/ctn、中断/brk、导入/import、函数/fn、类/cl、实例/new”。中文化提交da35c77b的差异记录及父版本词表共同确认这次扩展。
- 固定分支版本为1.9.3，Cargo.toml声明GPL-3.0；LICENSE保存GNU GPL第三版全文。
- 执行链由Rust实现：词法tokenize → 语法analyze → RootNode → computer::compute。脚本与REPL通过attempt连接解析和求值。脚本入口逐行读取并缓存多行花括号块；自定义函数建立局部作用域，读取中断携带的结果，再恢复调用方作用域。
- 固定Chinese-test头为189e8e23d95c215b1fbb7ff9d31ea2f740b43c89，时间2023-07-19T03:46:48Z。2026-10-10再次读取分支集合，头保持此提交。
- 固定主线头a4759246的词表含10项英文词元。两头比较的共同祖先为2c3539a5，结果为diverged、主线领先63提交、中文分支独有3提交；分支关系按Git历史记录。
- 主项目latest正式Release为1.10.5，发布于2023-08-29T09:35:33Z。按发布日期排序的最新预发行是editor-test分支的1.13.0a，发布于2024-05-24T12:56:09Z。中文专属发行物与这些Release的对应关系待核实。

### 时间层

1. 母项目GitHub仓库创建：2023-03-04T06:39:08Z。
2. deprecated1保存的母项目根提交7499ed2d：2023-03-04T06:40:04Z，parents=[]。
3. 现存最早GitHub Release 1.0.1：2023-03-06T12:39:57Z。
4. 当前中文分支祖先中的重构根提交d2f23f11：2023-05-15T10:14:16Z，parents=[]。
5. 中文词元及例程加入提交da35c77b：2023-07-18T13:49:09Z。
6. 中文公开演示页面时间：2023-07-19 11:35:20，按Bilibili原文保存。
7. 中文分支当前头：2023-07-19T03:46:48Z。
8. master当前头：2023-10-08T05:07:57Z；editor-test当前头：2024-06-17T14:17:43Z；仓库pushed_at：2024-07-25T09:49:42Z。

仓库创建、Git提交、发行记录、网页演示和pushed_at各自代表对应事件。中文分支实际首次对外开放时刻及其后续维护计划待核实。Bilibili页面时区待核实；代码示例以明确的固定源码版本为准。

### 完整连续中文原例

当前条目使用[固定examples/斐波那契.calcrs](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/examples/%E6%96%90%E6%B3%A2%E9%82%A3%E5%A5%91.calcrs)，共8行，含2个空行；文件blob为f5d5daa72f04e8daf4a909dcf81317adc08dad5b。这是完整作者原文件，代码保持原字符、分号、类型标记、顺序与缩进，展示仅省去文件末尾换行。

```text
斐波那契函数 = 函数(任意数 $数字) {
    若 任意数 == 1 { 中断 1 };
    若 任意数 == 2 { 中断 1 };

    中断 斐波那契函数(任意数 - 1) + 斐波那契函数(任意数 - 2)
}

输出 斐波那契函数(10)
```

原两行“加一”例保留如下，其原code_source为https://github.com/BHznJNs/Calculator.rs/blob/Chinese-test/README.md；对应[固定README](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/README.md)“支持函数定义”围栏。新原例展示条件、带类型参数与递归调用，原例继续作为已核短例保存。

```text
加一 = 函数(任意数) {中断 任意数 + 1}
输出 加一(1) # 2
```

### 主要固定来源

- [中文化初始提交：关键词、类型与示例](https://github.com/BHznJNs/Calculator.rs/commit/da35c77b4bd9f955eb2c3aa0490be6c8f74cd219)
- [完整中文斐波那契程序（固定提交）](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/examples/%E6%96%90%E6%B3%A2%E9%82%A3%E5%A5%91.calcrs)
- [九对中英文关键词映射（固定提交）](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/src/public/compile_time/keywords.rs)
- [词法与AST构建入口（固定提交）](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/src/compiler/mod.rs)
- [AST编译与求值连接（固定提交）](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/src/exec/attempt.rs)
- [AST求值入口（固定提交）](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/src/computer/computer.rs)
- [函数局部作用域与中断值返回（固定提交）](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/src/computer/resolvers/invocation/user_defined_function.rs)
- [脚本逐行读取及多行块处理（固定提交）](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/src/exec/script/mod.rs)
- [中文分支版本与GPL-3.0声明](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/Cargo.toml)
- [中文分支GNU GPL第三版全文](https://github.com/BHznJNs/Calculator.rs/blob/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89/LICENSE)
- [中文分支与主分支的固定提交比较](https://github.com/BHznJNs/Calculator.rs/compare/189e8e23d95c215b1fbb7ff9d31ea2f740b43c89...a475924608cc94c9699469dd5cf2adb5c758ab6e)
- [主分支英文关键词表（固定提交）](https://github.com/BHznJNs/Calculator.rs/blob/a475924608cc94c9699469dd5cf2adb5c758ab6e/src/public/compile_time/keywords.rs)
- [主项目正式发行1.10.5](https://github.com/BHznJNs/Calculator.rs/releases/tag/1.10.5)
- [editor-test预发行1.13.0a](https://github.com/BHznJNs/Calculator.rs/releases/tag/1.13.0a)
- [母项目deprecated1根提交（2023-03-04）](https://github.com/BHznJNs/Calculator.rs/commit/7499ed2dd4f7eb4a3a9071e956e617a6917b9468)
- [GitHub仓库元数据与归档状态](https://api.github.com/repos/BHznJNs/Calculator.rs)
- [GitHub分支当前指向](https://api.github.com/repos/BHznJNs/Calculator.rs/branches?per_page=100)
- [母项目现存最早发行1.0.1](https://github.com/BHznJNs/Calculator.rs/releases/tag/1.0.1)

### 待核范围

中文专属Release、真实首次对外开放时刻、后续维护计划、AI参与方式与比例、视频逐帧内容、跨平台二进制对应及独立运行结果继续待核实。README的平台列表属于作者使用说明；实机执行与性能属于后续核验范围。

### 平台、关键词、时窗与风险

- GitHub：原仓、Chinese-test、master、editor-test、deprecated1；读取README、完整树、Cargo.toml、LICENSE、词元与执行链、commits、branches、releases和固定compare。历史窗口追溯2023-03—2024-07，状态复核日为2026-10-10。
- Bilibili／网页索引：查询“Calculator.rs Chinese-test”“BV1Vh4y1L7Ay”“Calculator.rs BHznJNs AI”“Calculator.rs Chinese 2023 中文”“site.bilibili.com/video Calculator.rs 中文编程”“site.github.com/BHznJNs/Calculator.rs Chinese-test AI”。查询采用全时域，并以2023年原演示与源码时间交叉定位。
- 原视频普通网页读取返回412；网页索引保留作者、日期、标题与原分支链接。api.bilibili.com普通网页读取返回内部错误。原片帧内容与评论纳入待核范围。
- GitHub tags集合读取返回工具端点支持错误；版本信息依据可读Release集合、latest及固定Cargo.toml。Release集合本轮读取36项；动态集合未来变化以再次读取为准。
- 广义“Calculator.rs”及“Chinese-test AI”检索混入其他Rust文件和中文测试集；本条以作者账号、完整仓库名、分支、BV和固定提交排重。源码路径本身含compiler字样，实际执行方式由调用链确定。
- 本轮使用公开网页与GitHub只读接口。独立运行结果待核实。


## 玄铁（lang-034）补充核验

核验日期：2026-10-10（UTC）。本轮采用普通网页与 GitHub 只读查询，核验范围为公开文档、Git 元数据和源码结构。独立构建、运行、自举一致性、性能及跨平台执行结果待核实。

### 结论

- 维护账号为 MARKJY-China。固定 LICENSE 的版权署名为“问号盒”；GitHub README 指定 GitHub 为主仓库并指向 Gitee，Gitee 仓库显示“问号盒-MarkJY”。
- 最新 master 仍为 17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83，提交时间 2026-10-06T23:42:05Z。
- 最新 Release 为 v1.0-rc.3，发布时间 2026-10-04T13:08:29Z，正文称“第三个候选正式版”。API 字段 prerelease=false、draft=false。Release 元数据的非预发布标记与版本名称中的 rc 分别记录。
- README 代码已换为第37—46行同一围栏中的完整、连续 Result 示例，逐字保留。
- 原引用3条标题、URL、顺序全部保留，追加17条，合计20条。

### 日期分层

1. 项目自述起步：固定 [README_EN.md](https://github.com/MARKJY-China/XuanTie-Lang/blob/17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83/README_EN.md) 写 v0.2 起于 2026-04-03。该英文文件仍带 v0.15.4 的历史状态，当前版本以中文 README 和最新 Release 为准。
2. 现存 Git 历史根提交：[41b1dcd26aa37ede6bface5dbdc6bb0b814bb1c9](https://github.com/MARKJY-China/XuanTie-Lang/commit/41b1dcd26aa37ede6bface5dbdc6bb0b814bb1c9)，author.date 与 committer.date 均为 2026-04-04T05:33:33Z，parents=[]，提交标题记 v0.3.2.0 milestone。
3. [GitHub 仓库元数据](https://api.github.com/repos/MARKJY-China/XuanTie-Lang)：created_at=2026-04-05T18:57:29Z，default_branch=master，archived=false。
4. [GitHub 现存 Release 列表](https://api.github.com/repos/MARKJY-China/XuanTie-Lang/releases?per_page=100) 共4条：v0.17.2 于 2026-04-28T11:37:48Z；v1.0-rc 于 2026-08-14T21:25:20Z；v1.0-rc.2 于 2026-09-27T07:26:39Z；v1.0-rc.3 于 2026-10-04T13:08:29Z。
5. 首次向公众公开日期：待核实。起步自述、Git 提交时间、GitHub 创建时间及 Release 发布时间是不同事件，分别保留。Gitee 页面列3个历史发行；逐条日期待核实。

### 作者与同源关系

固定 [LICENSE](https://github.com/MARKJY-China/XuanTie-Lang/blob/17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83/LICENSE) 写 Copyright (c) 2026 问号盒；[Gitee 同项目仓库](https://gitee.com/mark-jy_admin/xuantie) 显示“问号盒-MarkJY”。旧 Gitee 链接 https://gitee.com/mark-jy/xuantie 重定向至该路径。当前 GitHub README 明确指定 GitHub 为主仓库、Gitee 为镜像，官方文档域名为 xt.markjy.com。

B站搜索索引显示“问号盒”的“中文编程能自举吗？我离答案只差最后一步”（04-21）和“玄铁中文编程语言 v1.0-rc 纯净虚拟机从安装到实现并运行桌面程序demo”（08-15）。直接视频 BV、完整发布日期及账号主页至项目仓库的身份链待核实，因此作者字段保留该缺口。参考索引：
- https://search.bilibili.com/all?keyword=%E7%BC%96%E7%A8%8B%EF%BC%9F
- https://search.bilibili.com/all?keyword=go%E8%AF%AD%E8%A8%80%E5%BC%80%E5%8F%91

### 连续中文示例及旧代码保存

新 code_source：[固定 README 第37—46行](https://github.com/MARKJY-China/XuanTie-Lang/blob/17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83/readme.md#L37-L46)。整个第二个 xuantie 围栏包含如下连续原例：

```text
函 获取数据(id) {
    若 id == 0 { 返 失败("无效 ID") }
    返 成功({"名": "玄铁", "值": 100})
}

获取数据(1).接着(函(对象) {
    示("获取到: " & 对象["名"])
}).否则(函(错) {
    示("错误: " & 错)
})
```

原 code_source（原值完整保存）：https://github.com/MARKJY-China/XuanTie-Lang

原6行 code（原值完整保存）：

```text
设 名字 = "玄铁"
示("你好，#{名字}！1+1=#{1+1}")
函 获取数据(id) {
    若 id == 0 { 返 失败("无效 ID") }
    返 成功({"名": "玄铁", "值": 100})
}
```

原代码的前2行来自 README 第33—34行的第一个围栏，后4行来自第37—40行的第二个围栏。两个围栏之间存在围栏结束与开始标记，旧摘录是两处片段拼接。新代码改为一个围栏的完整内容，函数定义后保留调用和成功／失败分支。

### 实现源码证据

- [lexer/lexer.go 第287—315行](https://github.com/MARKJY-China/XuanTie-Lang/blob/17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83/lexer/lexer.go#L287-L315)：把“设／变量”“函／函数”“返／返回”“若”等词映射为专门 Token；中文语法由词法实现直接支持。
- [main.go 第178—355行](https://github.com/MARKJY-China/XuanTie-Lang/blob/17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83/main.go#L178-L355)：tie 路径调用 compiler.NewLLVMCompiler(program)，再调用 Compile()；第204—205行将结果写为 .ll；第284—287行优先选 clang 并使用 -c 生成 .o；第328—355行把目标文件与 xt_runtime.c、xt_threadpool.c、xt_net.c、xt_tls.c 交给 gcc 驱动链接。findCCompiler 还列 gcc/cc 回退候选，回退可用性待执行核验。Go 入口另保存解释执行与 Go 转译构建路径。
- [compiler/llvm.go](https://github.com/MARKJY-China/XuanTie-Lang/blob/17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83/compiler/llvm.go#L205-L383)：Compile() 生成 LLVM 文本 IR，包含 main 定义及运行时函数调用。
- [xuantie_compiler/玄铁.xt 第488—603行](https://github.com/MARKJY-China/XuanTie-Lang/blob/17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83/xuantie_compiler/%E7%8E%84%E9%93%81.xt#L488-L603)：入口加载“词法.xt”“抽象语法树.xt”“语法分析.xt”“编译.xt”；依次创建词法分析器、语法分析器和编译器，调用解析程序()、编译程序()，第543行写入 .ll，第595行执行 clang 指令；后续用 gcc 驱动链接运行时。
- [xuantie_compiler/编译.xt](https://github.com/MARKJY-China/XuanTie-Lang/blob/17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83/xuantie_compiler/%E7%BC%96%E8%AF%91.xt#L1052-L1135)：编译程序方法生成 LLVM 的 target datalayout、target triple 与对象类型；第1371行附近生成 main。
- [runtime/xt_runtime.h](https://github.com/MARKJY-China/XuanTie-Lang/blob/17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83/runtime/xt_runtime.h#L1-L86)：包含 stdatomic.h、_Atomic ref_count 和 Tagged Value 宏。
- [runtime/xt_runtime.c 第1660—1683行](https://github.com/MARKJY-China/XuanTie-Lang/blob/17ef9d35a683fb8951050dd7ea5f0c7c6d9dbd83/runtime/xt_runtime.c#L1660-L1683)：xt_retain 使用 atomic_fetch_add_explicit，xt_release 使用 atomic_fetch_sub，并在引用数归零时释放对象。

上述材料证实源码中的实现结构与调用路径。自举产物逐字节一致、运行性能、完整语义正确性和跨平台结果属于另一层执行证据，待核实。

### MIT全文与范围

固定 LICENSE 完整读取，全文为：

```text
MIT License

Copyright (c) 2026 问号盒

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

记录范围为项目根目录许可证覆盖的内容；第三方依赖按各自许可处理。

### AI声明范围

固定中文 README 的作者声明约90%代码由大模型生成，并称每次更新经过全量回归。该比例为作者声明。README 另以“直至2026-09-27”为时点列出 ClaudeFable5 3%、KimiK3 27%、DeepSeekV4Pro 49%、DeepSeekV4.1Flash 9%、GLM5.3 12%，合计100%。模型份额与总代码90%之间的统计分母及统计方法待核实。模型名称、生成比例、人工审核及回归结论的独立核验待核实。

compiler/llvm.go 文件头另称大部分代码由 TraeAI 编写并经作者审核及 ClaudeOpus4.7 扫描。当前 master 提交信息称该次提交由 Kimi 负责并经人工核验。这些说明各自限于相应文件或提交，分别归属作者声明。正文使用“作者在README中声明”，保留披露来源。

### 变更摘要

description 扩展为中文长介绍，覆盖定位、中文语法、源码架构、工具链、MIT及候选发行阶段。author 补许可证署名与 Gitee 账号，保留 B站直接身份链待核实。first_publication 拆分起步、提交、创建及发行事件。implementation 补实际源码调用链。version、status 使用当前 API 与固定提交。全部原引用顺序保留。条目与本日志分别保存结构化结论及证据范围。

### 搜索平台、关键词与时窗

本轮查询窗口：2026-10-10 21:01—21:06 UTC；检索采用网页搜索／打开和 GitHub 只读 connector。网络搜索采用全时段检索，结果时效由原页面、固定提交与API时间戳分别确定。

网页搜索的实际查询包括：
- “问号盒” “玄铁”
- “MARKJY-China” “bilibili”
- “问号盒” “玄铁中文”
- site:bilibili.com/video “玄铁” “语言”
- site:github.com/MARKJY-China “问号盒”
- “markjy.com” “bilibili”
- “玄铁中文编程语言 v1.0-rc”
- “玄铁” “自举” “哔哩哔哩”
- “问号盒” 编程
- “XuanTie-Lang” “bilibili.com”
- 玄铁 编程 语言 问号盒 B站
- “中文编程能自举吗” “问号盒”
- “玄铁中文编程语言” “BV”
- “问号盒” “space.bilibili.com”
- MARKJY B站
- 问号盒 MarkJY
- “问号盒” bilibili 玄铁
- “玄铁” “04-21” 编程
- “XuanTie-Lang”
- “中文编程能自举吗？我离答案只差最后一步”
- “玄铁中文编程语言 v1.0-rc 纯净虚拟机”
- “问号盒” site:bilibili.com/video

GitHub代码检索：
- query=bilibili，org=MARKJY-China：返回空列表。
- query=2026-04-03，repository=MARKJY-China/XuanTie-Lang：返回空列表；改为直接读取固定README_EN取得英文日期。
- query=问号盒，repository=MARKJY-China/XuanTie-Lang：取得LICENSE及多个官方库tiepm.toml署名。

失败与替代读取记录：
- GitHub公开仓库主页网页可读；网页 /releases 返回 Cache miss，改用GitHub connector读取 /releases?per_page=100 与 /releases/latest 成功。
- GitHub账号主页及 ?tab=overview 返回 Cache miss／Internal Error；同名个人README仓库返回404。作者核验转向项目LICENSE、维护账号元数据及Gitee仓库署名。
- xt.markjy.com 与 /ai/index.html 网页返回 Internal Error／not accessible。保留旧官方文档引用，并通过固定README核实该域名与项目的链接关系。
- B站搜索索引提供“问号盒”与两个演示标题。直接打开搜索页返回验证码页面或访问错误；此处止于已有索引证据，原视频BV、日期年份与个人主页直链待核实。
- Gitee旧仓库地址可读并重定向至 mark-jy_admin/xuantie；账号页、发行列表、提交列表及0.3.3／0.4.1发行页面返回 Cache miss／not accessible。现存GitHub Release的最早日期与Gitee历史发行分别记录。
- 全文源码读取均通过GitHub connector完成，只作阅读分析；调用链依据固定源代码的文本与行号。

必要独立字段 code_context、license、ai_involvement 已加入建议对象；code_context保留完整连续例子、原6行边界及独立执行待核实。



## 静态核验

资料结构、原始引用与连续示例已核对。独立运行结果待核实。
