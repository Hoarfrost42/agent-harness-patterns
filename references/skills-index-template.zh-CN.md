# Skills 索引模板

把它当成轻量路由参考。它不会改变 Codex 的 skill discovery。

## 路由规则

- 不需要 skill 时，使用普通推理。
- 选择最小有用 skill 集。
- 项目级规则优先于宽泛领域 skill。
- 对重叠 skill 按角色分类：主方法、护栏、执行轮、验收轮。
- 官方或供应商 skill 保守处理；优先改本地路由规则，而不是编辑供应商内部文件。

## 清单

| Skill | 用途 | 触发 | 状态 |
| --- | --- | --- | --- |
| `skill-router` | 选择最小有用 skill 集 | skill 冲突或路由不清 | active |
| `project-continuity-control` | 恢复当前事实并防止旧文档污染 | handoff、续窗、旧文档、read-first index | active |
| `straight-line-code-discipline` | 保持代码和概念清晰 | 写代码、重构、diff 膨胀 | active |
| `no-visible-meta-copy` | 移除开发者视角可见文案 | UI 文案、公开页面、演示稿、报告 | optional |

## 备注

保持这个文件短。项目专属覆盖规则应该放到单独 reference。
