# 上下文卫生

长期 Agent 工作需要上下文卫生，而不只是更好的 prompt。

## 规则

- 当前真相源优先于旧总结。
- 大项目保留一份 read-first index。
- handoff 分层：快速恢复提示词、事实索引、完整档案。
- 明确标记旧文档，或把它们移出活跃读取路径。
- 不要让旧契约、旧站点 review、旧 quickstart 看起来像当前事实。
- 如果更新一份活文档就够，不要继续新增 SPEC。

## Read-First Index 形态

```md
# Read First

## Current Truth Sources

1. `README.md` - 项目入口和运行命令
2. `docs/project/status.md` - 当前阶段和开放风险
3. `src/...` - 当前实现

## Stale Or Historical

- `docs/archive/old-contract.md` - 旧 API 契约，不再权威
- `docs/research/site-review.md` - 仅作历史调研
```
