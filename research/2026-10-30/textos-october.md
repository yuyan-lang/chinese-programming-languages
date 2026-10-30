# TextOS：2026年10月源码阶段

核验日期：2026-10-30。平台：GitHub 原仓库、固定源码和 Releases API。检索方式：已有条目 TextOS 的 main 与 2026-10-01 快照比较；时间范围 2026-10-01—2026-10-30。未扩展新线索。

## 本轮范围

已读根 AGENTS.md、README、研究日志、目录与全部开放 Issues/PR；开放 Issue 为 0，仅 PR #62（取消合并）与 #76（草稿）保持原样。正式目录维持语言114、内核26。

## 证据

- [2026-10-30 main 提交](https://github.com/ljQAQ233/textos-dev/commit/a38fbc6fb9e9d08c1f60c476373f99c596c34da1)
- [10月1日至10月30日固定提交比较](https://github.com/ljQAQ233/textos-dev/compare/75ebadf4134f6144ed1ffc0b1d3229582766db4f...a38fbc6fb9e9d08c1f60c476373f99c596c34da1)
- [初步 COW 的作者提交说明](https://github.com/ljQAQ233/textos-dev/commit/db6b3c313bf6334605c108000abb66bc81cbc917)
- [10月30日页表复制](https://github.com/ljQAQ233/textos-dev/blob/a38fbc6fb9e9d08c1f60c476373f99c596c34da1/src/kernel/mm/map.c)
- [10月30日物理页引用记录](https://github.com/ljQAQ233/textos-dev/blob/a38fbc6fb9e9d08c1f60c476373f99c596c34da1/src/kernel/mm/mman/ppg.c)
- [10月30日 init](https://github.com/ljQAQ233/textos-dev/blob/a38fbc6fb9e9d08c1f60c476373f99c596c34da1/src/app/init.c)
- [10月30日 getty](https://github.com/ljQAQ233/textos-dev/blob/a38fbc6fb9e9d08c1f60c476373f99c596c34da1/src/app/getty.c)
- [10月30日共享映射同步](https://github.com/ljQAQ233/textos-dev/blob/a38fbc6fb9e9d08c1f60c476373f99c596c34da1/src/kernel/mm/mman/sync.c)
- [Releases集合](https://api.github.com/repos/ljQAQ233/textos-dev/releases?per_page=100)：最新仍为 buildable-20261001，2026-10-01T13:58:46Z；kit-202604 为2026-04-26T05:56:05Z。

当前 main 固定为 a38fbc6fb9e9d08c1f60c476373f99c596c34da1，提交时间2026-10-30T14:41:11Z，相比75ebadf4134f6144ed1ffc0b1d3229582766db4f新增63提交。

2026-10-17 的提交说明记述初步写时复制（COW）。10月30日 map.c 的 _copy_pgt 清除叶页表项 PE_RW，ppg.c 管理共享物理页记录与引用计数。

sync.c 为 MAP_SHARED 文件映射登记同步区域，vmm_sync_area 扫描脏页，经回调调用 vfs_write。

init.c 启动 /dev/tty1 和 /dev/ttyS0 的 getty；getty.c 调用 setsid、打开终端并复制标准输入输出描述符，设置 TERM 后执行 /bin/login。

短代码（map.c）：

```c
vpg[i] &= ~PE_RW;
vnpg[i] = vpg[i];
```

短代码（getty.c）：

```c
execv("/bin/login", (char *[]){ "login", NULL });
```

百科保留10月1日的原始源码、README路线图、发布与视频来源；调度和旧内存说明加历史日期，新增10月30日静态源码阶段。代码正确性、独立构建/启动与视频时间点继续待核实。本轮没有执行项目或下载发布包。遗漏风险：仅静态阅读限定文件，提交记录与源码路径不能覆盖运行时行为或全部近期变动。没有重新访问既有受限来源。

## 结果

关闭Issue 0；新发现0；既有条目完善1（TextOS），核实1项源码阶段，新增待核实项目0。条目既有运行验证缺口继续明确保留。仅资料变更，默认分支经PR更新。
