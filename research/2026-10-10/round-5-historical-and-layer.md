# 第五轮：SPCNYY与Sheng资料核验

核验日期：2026-10-10（UTC）。

本轮先读取目标仓库的 `AGENTS.md`、`data/languages.json`、[第四轮发现记录](https://github.com/yuyan-lang/chinese-programming-languages/blob/main/research/2026-10-10/round-4-discovery.md)和[Issue #16](https://github.com/yuyan-lang/chinese-programming-languages/issues/16)。研究采用普通网页和GitHub只读工具，安装、打包、运行验证列为待核实。

## 分类结论

- Sheng（结绳）：按历史中文关键字语言收录。作者PyPI发行说明提供实际中文程序、作者、版本和发行物信息。Python与PLY实现按作者声明记录，具体源码正文待核实。
- SPCNYY：保留候选。已核实Python关键词转译机制、平台脚本关系及编辑器执行路径；作者原始.spc程序和教学短例继续待补充。

## SPCNYY

### 来源与日期

- 仓库：[xs-smz/spcnyy-](https://github.com/xs-smz/spcnyy-)。
- 固定提交：`2d9087cade68fff2c966a7bf057141935b439ec0`，提交时间2026-08-15T16:46:47Z。
- [仓库元数据](https://api.github.com/repos/xs-smz/spcnyy-)：创建于2026-08-15T16:42:42Z，pushed_at为2026-08-15T16:46:48Z；fork=false，license=null。
- [完整递归树](https://api.github.com/repos/xs-smz/spcnyy-/git/trees/2d9087cade68fff2c966a7bf057141935b439ec0?recursive=1)共5项，truncated=false：README.md、setup目录、setup/pipe、setup/spcnyysetup.sh、windows_spcnyy.ps1。
- [提交集合](https://api.github.com/repos/xs-smz/spcnyy-/commits?per_page=100)共2项；根提交`2b99fb85eaf91284d5d0bd0aa047772db41dd75c`在2026-08-15T16:43:42Z创建，parents为空，其完整树仅含README。
- [Releases](https://api.github.com/repos/xs-smz/spcnyy-/releases)和[全部议题](https://api.github.com/repos/xs-smz/spcnyy-/issues?state=all&per_page=100)集合为空；git/refs/tags端点返回404。正式版本号、许可证及更早公开日期待核实。

### 翻译与执行语义

[Linux脚本第288—312行](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh#L288-L312)内嵌language.py。映射涵盖“如果”“否则”“否则如果”“循环”“当”“遍历”“定义”“返回”“打印”“输入”“导入”“类”，并包含部分拼音与中文标点。

translate按映射键长度降序对完整输入文本调用str.replace，因此字符串、注释和标识符中的匹配文本也参与替换。随后四条for正则将数字或ASCII字母/下划线开头的变量形式转换成for i in range(...)；另有while格式整理。替换顺序由原始源码直接确认。

[运行入口第600—618行](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh#L600-L618)先调用translate，再交给Python exec。[导出入口第646—653行](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh#L646-L653)将相同转译结果保存为.py。编辑器使用.spc后缀。

[ai.py模块](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/setup/spcnyysetup.sh#L247-L285)负责DeepSeek问答和代码纠错；本地translate函数承担语法转换。源码提供在线与离线编辑器入口。

### Windows与Linux关系

静态提取两个安装脚本中的7个Python模块正文，按字符比较全部相同：

- main.py：15行
- launcher.py：52行
- login.py：114行
- recharge.py：25行
- ai.py：38行
- language.py：23行
- editor.py：365行

Linux脚本的blob SHA为`bd896ef420a1e7a2040e5bdd8ad87d24d53b51fa`；Windows脚本为`7e4abde4fb89966bf8f5826d4a6c1e080172357f`。Windows对应的[language.py正文位于第337—359行](https://github.com/xs-smz/spcnyy-/blob/2d9087cade68fff2c966a7bf057141935b439ec0/windows_spcnyy.ps1#L335-L360)。

Linux入口使用apt、venv及PyInstaller；Windows入口检测Python 3，按需下载Python 3.12.4，并以PyInstaller打包EXE。两个脚本分别含有桌面SPCNYY目录的删除与重建操作。内嵌源文本一致性已经核实，Shell展开后的生成文件一致性及安装运行效果待核实。

### 原例与资料缺口

当前README为名称和一句简介；新建编辑器缓冲区为空。完整现存文件树、根提交、发行及议题资料提供了安装实现。作者认可的用户程序、原始教学示例、正式语言名展开及名称沿革待核实。

GitHub查询`SPCNYY fork:true`返回xs-smz/spcnyy-一项；普通网页查询`"SPCNYY"`、`"SPCNYY" "打印"`及作者范围代码检索的有效新增来源待补。按“Python中文关键词转译层／配套编辑器”记录候选分类。

## Sheng（结绳）

### 作者资料与发行历史

[作者PyPI页](https://pypi.org/project/sheng/)列作者luojiahai、维护者ljiahai、Python >=3.9和MIT License元数据，并将实现记为Python与PLY。中文语言名来自作者的结绳命名说明。

版本表保存0.1.0至0.1.22共23个版本：

- 最早可见[0.1.0](https://pypi.org/project/sheng/0.1.0/)：2021-11-07
- 已有线索[0.1.18](https://pypi.org/project/sheng/0.1.18/)：2021-11-15
- 最新可见0.1.22：2021-11-17

项目更早首次公开时间、精确上传时刻和当前维护计划待核实。

### 作者实际中文程序

[0.1.18发行说明](https://pypi.org/project/sheng/0.1.18/#description)的Getting Started给出以下连续原例，文件名为example/helloworld.zh：

```text
甲 赋值 "你好，世界！"
打印(甲)
```

作者解释首行为赋值，次行调用内置打印函数。[0.1.19页](https://pypi.org/project/sheng/0.1.19/)和当前0.1.22主项目页保留相同原例。它直接证明中文赋值语法和中文内置函数名称。

0.1.0发行页保留更早的example/helloworld.yn写法，使用“字符串”“开始”“结束”组织字符串值；后期说明使用.zh、引号与括号。语法迁移的完整版本边界待核实。

### 发行物与源码取得边界

PyPI当前页列出：

- sheng-0.1.22.tar.gz，49.0 kB，SHA256：`c539ffb992492fbd6ecb501d4cc66605696bdbace40a279bc73a5e43dd17702d`
- sheng-0.1.22-py3-none-any.whl，56.3 kB，SHA256：`757ab0e04e0d464265ab5f36ad7692a5fa8c3cbabe39d9893827a38ce555689e`

这些文件信息和校验值取自PyPI元数据。[源代码包原始链接](https://files.pythonhosted.org/packages/22/db/cdd808ba75467e4a6844d0f97e51ec69856b0388ec2610c4328a645aa906/sheng-0.1.22.tar.gz)已保留。

当前PyPI主项目页可直接读取，版本化页面正文通过网页搜索返回的作者页面核对。版本化URL、tar.gz及wheel的直接网页读取返回Cache miss；[原GitHub仓库](https://github.com/luojiahai/sheng)的API返回404。GitHub查询`"luojiahai/sheng" in:readme fork:true`、`sheng in:name fork:true "programming language"`与精确项目标题代码搜索返回空结果。可读源码正文、词元表、语法产生式、执行后端及发行包内许可文本待核实。

### 同名关系

Sheng按PyPI包名、作者和维护者建立独立资料链。现有lang-012结绳中文对应tiecode.cn、Scave与MobileIPE；本轮保留两个项目身份。它们之间的代码继承或合作关系待核实。

