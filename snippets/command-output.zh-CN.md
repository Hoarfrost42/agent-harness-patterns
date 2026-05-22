# 命令输出上下文保护

保护上下文用量。任何未知或可能很大的命令输出，都应该先缩小范围，再进入 agent 上下文。

## 规则

优先使用窄查询，而不是完整 dump：

```powershell
rg "pattern" path -n -m 80
git diff --stat
git diff --name-only
Get-Content path -TotalCount 200
Get-Content path -Tail 200
```

对于日志、构建输出、长 JSON、数据库导出、完整 diff 和大文件：

1. 先看文件名、统计、计数或小样本。
2. 搜索相关模式或时间窗口。
3. 只有当完整输出对当前判断必要时，才读取完整内容。

## 为什么

大段命令输出会污染工作上下文、增加 token 消耗，并让后续推理变差。目标不是隐藏证据，而是先拉入最小有用证据。

## AGENTS.md 片段

```md
## Command Output

- 保护上下文。对未知或可能产生大量输出的命令，必须先限制输出范围。
- 优先使用窄查询：`rg pattern path -n -m 80`、`git diff --stat`、`git diff --name-only`、`Get-Content path -TotalCount 200`、`Get-Content path -Tail 200`。
- 查看日志、构建输出、长 JSON、数据库导出、完整 diff、大文件内容前，先用摘要、匹配、行数限制或文件名列表定位范围。
- 只有当完整输出对当前判断确实必要时，才读取完整内容。
```
