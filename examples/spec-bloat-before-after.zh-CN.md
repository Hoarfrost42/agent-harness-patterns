# 案例：SPEC 膨胀 Before/After

## 之前

一个长期项目积累了几十份 SPEC。每份单看都合理，但没人知道：

- 哪份文档是当前事实
- 哪份文档已经过时
- 下一步应该产出什么
- 什么算达到验收标准
- 哪些概念仍然重要

Agent 继续写更多文档来恢复清晰度，但文档堆本身已经变成问题。

## 之后

建立一个小型控制面：

```md
# Project Control Surface

## Read First
1. `docs/status.md` - 当前阶段和验收标准
2. `README.md` - 运行命令
3. `src/...` - 当前实现

## Current Phase
Validation

## Expected Output
Playable MVP with smoke-tested core loop.

## Acceptance Standard
Runs locally, one happy path works, known gaps are listed.

## Stale Docs
- `docs/old-contract.md` - archive only
- `docs/v1-plan.md` - replaced by current status
```

## 规则

当 SPEC 增长得比清晰度更快时，停止写新 SPEC，先建立 read-first 控制面。
