# 5 分钟快速开始

把这个仓库当成一个小工具箱，不要一开始整套全装。

## 我需要它吗？

如果你的 Agent Coding 经常出现这些症状，大概率值得试：

| 症状 | 先看 |
| --- | --- |
| 命令把大量日志、diff 或 JSON 灌进上下文 | `snippets/command-output.zh-CN.md` |
| Agent 相信旧文档，而不是当前代码 | `skills/project-continuity-control/SKILL.md` |
| 项目一直在推进，但你看不清哪些已经完成 | `references/control-loss-gate.zh-CN.md` |
| SPEC 和 handoff 越写越多，反而更不清楚 | `examples/spec-bloat-before-after.zh-CN.md` |
| UI 文案像开发备注 | `snippets/user-visible-copy.zh-CN.md` |
| 代码能跑，但概念、manager、adapter 越堆越多 | `skills/straight-line-code-discipline/SKILL.md` |

如果你的 Agent 任务大多很短、独立、容易验证，可以先不使用这套。

## 先粘这一段

先把这段放进项目规则或 `AGENTS.md`：

```md
## Command Output

- 保护上下文。对未知或可能产生大量输出的命令，必须先限制输出范围。
- 优先使用窄查询：`rg pattern path -n -m 80`、`git diff --stat`、`git diff --name-only`、`Get-Content path -TotalCount 200`、`Get-Content path -Tail 200`。
- 查看日志、构建输出、长 JSON、数据库导出、完整 diff、大文件内容前，先用摘要、匹配、行数限制或文件名列表定位范围。
- 只有当完整输出对当前判断确实必要时，才读取完整内容。
```

## 第一次失控检查

当项目开始失去掌控感时，不要继续让 agent 开下一批实现。先让它输出这个：

```md
停止执行优先推进。先建立一个紧凑的项目控制面：

1. 哪些已经完成？
2. 哪些半完成？
3. 哪些还没验证？
4. 哪些已经过时或可疑？
5. 当前处于什么阶段？
6. 这个阶段应该产出什么？
7. 什么算达到验收标准？
8. 接下来 1-3 个关键决策是什么？
```

## 先装一个 Skill

如果你使用 Codex skills，先从一个开始：

```powershell
Copy-Item -Recurse .\skills\project-continuity-control "$env:USERPROFILE\.codex\skills\project-continuity-control"
```

安装或改名后，重启 Codex。

## 保持轻量

加一条规则，跑一个真实任务，再判断它有没有帮助。

如果一条规则没有减少混乱、上下文膨胀、旧文档污染或返工，就删掉它。
