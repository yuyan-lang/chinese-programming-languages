# 第十五轮：Zechariah中文脚本语言

核验日期：2026-10-10。本轮真正新发现并建议正式收录1项。原仓为[qbr12/hbr-c.zc](https://github.com/qbr12/hbr-c.zc)，固定提交15b107ae9f7ce112e678b385b65599d749b6cbdc。

## 排重
80项语言、24项开放Issues及63条相关评论按Zechariah、qbr12与完整仓库路径查询，匹配0项；历轮研究日志及候选记录全文匹配0项。按一个项目收录，仓库名作为入口别名。

## 原始例程
[demo2.zc第5—12行](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/demo2.zc#L5-L12)，blob 57b294aa3a8debe2c012d0a034f919c34ce4fca3，连续8行，原缩进及字形保留。
```text
定义 阶乘(n) {
  若 n <= 1 则
    返回 1
  否则
    返回 n * 阶乘(n - 1)
  结束
}
显示 阶乘(5)
```
原文件前四行为项目注释、用插件语句、空行及章节注释；本片段完整保留函数与调用。运行结果待核实。

## 实现边界
JavaScript与Node.js实现。compiler/lexer.js定义21个中文关键词；parser.js构造If、Loop、While、Func、Return、ForIn等AST。compiler/compiler.js第16—23行调用Parser.parse和Codegen.generate生成JS。codegen.js把控制节点转为JS语句，把函数参数写入共享__v变量表，再生成函数体；函数局部作用域、递归重入与变量恢复结果待核实。run.js另调用interpreter.js的逐行正则匹配路径。插件字符串实现经Function构造或生成到产物。Windows打包由C#启动器启动同目录node.exe和_payload.js；.NET Framework与dotnet publish分支、依赖闭合及运行兼容待核实。

固定词元表共有21项。解析器有独立中文条件、循环与函数节点，源码支持中文语法收录依据。生成器第79—86行将参数存入共享变量表并产生JS函数／return；第173行创建全局__v。编译器第16—23行为读取→parse→generate→写出。逐行解释器通过正则处理设、显示、若、循环和说，解释覆盖与编译路径分别保存。

打包源码第119行起生成C#启动器，第262行起复制Node、程序体和启动器。dotnet分支第224行net8.0，第227行SelfContained=false，第238行publish参数同样使用false。README的便携分发描述按作者说明记录，所需运行环境与产物完整性继续核实。

## 日期、版本、许可、AI
GitHub仓库创建于2026-08-22T10:38:42Z；现存无父根提交1b594de9857bb26b288cd1f20122bc82f54f5f2b记录2026-08-22T12:03:57Z；首个正式Release v1.0.0公开于2026-08-22T13:18:30Z。仓库、Git历史和发行各自记录；更早公开材料待核实。

GitHub首个正式Release v1.0.0（2026-08-22T13:18:30Z），标签指向acd3fb2a0730e7a03504b749305c9719194b2de3；固定main为15b107ae9f7ce112e678b385b65599d749b6cbdc，其README后续更新于2026-08-22T16:26:05Z。package.json保留0.1.0与MIT声明，包号、发行号和完整许可证文本分别待核。

公开仓库archived=false；本轮读取4条提交、1项正式Release和1个标签。最后推送2026-08-22T16:26:06Z。Release附件集合为空，源码树另保存打包样例；发行物对应、持续维护计划及独立运行待核实。

package.json声明MIT；完整树49项，42个文件，许可证文件名匹配0项。完整许可文本与版权主体待核实。

DeepSeek插件从环境变量读取调用配置并请求公开API，属于产品功能。开发使用的AI模型、工具、代码份额和审核流程待核实。现存历史的删除提交标题作为Git事件保存，开发过程结论以作者公开说明为待补字段。

## 原始参考
- [项目原仓](https://github.com/qbr12/hbr-c.zc)
- [固定README：设计与两条运行路径](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/README.md)
- [固定连续8行中文阶乘原例](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/demo2.zc#L5-L12)
- [固定中文词法集合](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/compiler/lexer.js#L5-L9)
- [固定中文语句分派与函数解析](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/compiler/parser.js)
- [固定AST生成器与共享变量表](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/compiler/codegen.js)
- [固定编译入口及Windows启动器](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/compiler/compiler.js)
- [固定逐行解释器](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/interpreter.js)
- [固定解释入口](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/run.js)
- [固定插件加载接口](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/plugin.js)
- [固定版本与MIT声明](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/package.json)
- [首个正式发行v1.0.0](https://github.com/qbr12/hbr-c.zc/releases/tag/v1.0.0)
- [现存根提交](https://github.com/qbr12/hbr-c.zc/commit/1b594de9857bb26b288cd1f20122bc82f54f5f2b)
- [固定DeepSeek API插件](https://github.com/qbr12/hbr-c.zc/blob/15b107ae9f7ce112e678b385b65599d749b6cbdc/plugin-deepseek.json)
- [固定完整源码树](https://api.github.com/repos/qbr12/hbr-c.zc/git/trees/15b107ae9f7ce112e678b385b65599d749b6cbdc?recursive=1)

## 检索与风险
GitHub查询“中文编程语言 created:2025-01-01..2026-10-10”，首50项中的实际38项结果发现原仓。后续按原仓读取README、完整树、4条提交、分支、Release及标签引用集合，并逐文件读取编译链、原例、解释器、插件和包描述。
网页查询：“Zechariah” “qbr12”；“Zechariah” “中文编程”；“hbr-c.zc”；“Zechariah” 编程 B站。通用英文名称混入宗教资料及同名账号，仅以原仓为技术依据。原作者B站视频、官网和跨平台互链继续待核。
GitHub /readme集合端点返回工具路径错误，改为明确README.md文件读取成功。
目标时窗2024—2026，命中源于2026-08；核验时点2026-10-10。遗漏风险为索引覆盖、同名混淆、版本与包号差异、解释和编译能力区别、生成器作用域、分发依赖及许可全文。独立执行结果待核实。

