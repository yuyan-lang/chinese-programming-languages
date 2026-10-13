# FSG正式收录静态复核

核验日期：2026-10-13。对应Issue #67。原仓固定提交a8314117b6dd7d42376d583797b91f2232a44025。百科基线b41ce32acfc3a927e0db7bbe3ec9e0dd398cc122，97项语言。

## 结论与范围

FSG按中文汇编／字节码语言原型收录为lang-098。真实中文程序、词法映射、两遍标签处理、FSGB生成、VM装载及分派支持当前分类。自编译闭环、字节码一致性和实现兼容性作为条目待核字段保存。本次以证据归档和正式收录为Issue67的有限结案范围。

已读根AGENTS、现有目录、研究记录、开放议题与PR；沿用05:00及06:00对Issue67的调查，复核固定源码与历史。候选安装、构建、测试、执行均为0。

## 原例与调用链

原例来自examples/test_loop_cn.fsg完整第1—15行，blob cbf07e40d059a49ed05982115715b19f6a542294，保留缩进和尾部换行。

```text
_开始:
    载常 R0, 1
循环:
    打印 R0
    载常 R1, 1
    加 R2, R0, R1
    赋值 R0, R2
    载常 R1, 5
    比较 R0, R1
    若大于跳转 结束
    跳转 循环
结束:
    载常 R0, 42
    打印 R0
    停止
```

README声明Python>=3.10和纯Python实现。src/fsg编译器1.py的OPCODES保存中英文映射，lex识别标签、指令、寄存器、整数与字符串；compile_tokens先计算标签地址，再生成指令和数据；build_fsgb写入FSGB魔数、0x0100版本及代码／数据长度。compile_file串联UTF-8文件读取、词法分析、编码与写入。src/simple_vm.py另含Assembler和FSGVM，VMState保存八个寄存器、程序计数器、栈指针、标志位与内存；装载器将代码和只读数据放入内存，run经取指分派调用处理函数。PRINT使用Python print输出寄存器数值。

## 实现边界和作者路线图

2026-10-13只读复核AGENTS.md、Issue67及评论、97项语言数据和原仓固定资料。完整递归树50项、45文件；main保留11条提交。中文编译器把停止编码为0xF0、打印串为0x51、输入为0x52；VM枚举为HALT=0x01、SYSCALL=0xF0、INPUT=0x51、PRINTS=0x52。examples/fsg编译器2_中文版.fsg保存版本数值输出与循环，完整源码输入解析及编译输出链待核实。bootstrap_test_v0.py调用Python Assembler.assemble处理compiler_v0.fsg，并将Stage1编译Stage1列为下一步；bootstrap_result.md长期目标列出自编译及字节码一致性。自举验证.py调用Python编译器和VM并比较打印文本，比较失败分支之后仍可到达末尾成功打印。脚本路径与固定布局对应继续待核。本轮安装、构建、测试及候选程序执行均为0。

作者bootstrap_result.md将Stage1自编译及字节码一致性列为长期目标；按原说明保存。脚本的成功打印记录为控制流事实，运行结果另待核。

## 作者、历史、许可与关系

GitHub账号hctj353056维护。README署名蜉蝣为项目设计者、灵镜为AI助手；根提交署名蜉蝣并关联hctj353056。具体开发分工与人工复核范围待核实。

仓库创建于2026-04-13T10:36:27Z；main保留历史的根提交4c9d3c9b3b6556fc04dccb98d6a9fa242650b7e4记录2026-04-29T23:54:37Z。首次对外公开日待核实。

README将v3.0中文关键字支持、v3.1跳转偏移修复和v3.2内置命令支持均记为2026-04-30；Python编译器自标v3.2，中文FSG示例自标v3.0。固定main提交a8314117b6dd7d42376d583797b91f2232a44025时间为2026-05-09T10:56:50Z。docs/MEMORY.md标题使用2024-04-30，年份对应关系待核实。

固定根LICENSE保存MIT许可证全文，版权署名2026蜉熵阁；GitHub许可元数据识别为MIT。

README将灵镜列为AI助手，中文FSG示例头部署名“蜉熵阁 - 灵镜(ling)”。具体模型、参与任务、生成比例及人工复核范围待核实。

仓库名FSG-language、README名称FSG（蜉熵阁汇编语言）和.fsg原例构成同一项目身份链。GitHub元数据fork=false。bootstrap_result.md将c4列为架构参考，具体源码继承待核实。README将早期符语目录称为早期实验代码；它与当前FSG的版本继承和兼容关系待核实。Python为当前实现语言。

## 检索覆盖与遗漏风险

平台为GitHub／Gitee／GitCode及中文网页索引；发现范围2024—2026微型／AI辅助中文语言。关键词中文编程语言、微型语言、AI、FSG、蜉熵阁、蜉蝣、灵镜、hctj353056、符语。核对当前97项及别名、开放议题与研究索引；项目首次发现记录见Issue67。原仓完整树50项45文件，main保留11提交。未索引资料、其他分支、已删除历史与未提交产物保留遗漏风险。时间差异和未知字段已保存在正式条目。

## 固定来源

- [原始议题及自举补证](https://github.com/yuyan-lang/chinese-programming-languages/issues/67)
- [README.md](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/README.md)
- [examples/test_loop_cn.fsg](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/examples/test_loop_cn.fsg)
- [src/fsg编译器1.py](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/src/fsg编译器1.py)
- [src/simple_vm.py](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/src/simple_vm.py)
- [examples/fsg编译器2_中文版.fsg](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/examples/fsg编译器2_中文版.fsg)
- [bootstrap/bootstrap_test_v0.py](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/bootstrap/bootstrap_test_v0.py)
- [bootstrap/bootstrap_result.md](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/bootstrap/bootstrap_result.md)
- [bootstrap/自举验证.py](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/bootstrap/自举验证.py)
- [docs/MEMORY.md](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/docs/MEMORY.md)
- [早期符语/符语.py](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/早期符语/符语.py)
- [LICENSE](https://github.com/hctj353056/FSG-language/blob/a8314117b6dd7d42376d583797b91f2232a44025/LICENSE)
- [原仓元数据](https://api.github.com/repos/hctj353056/FSG-language)
- [保留提交历史](https://api.github.com/repos/hctj353056/FSG-language/commits?per_page=100)
- [根提交](https://github.com/hctj353056/FSG-language/commit/4c9d3c9b3b6556fc04dccb98d6a9fa242650b7e4)
- [发行集合](https://api.github.com/repos/hctj353056/FSG-language/releases)
