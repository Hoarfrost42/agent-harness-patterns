# 采用层级

使用能解决当前问题的最小层级。

## Level 1：粘一条规则

适合还不想引入 skill 系统的人。

先看：

- `snippets/command-output.zh-CN.md`
- `snippets/user-visible-copy.zh-CN.md`
- `snippets/context-hygiene.zh-CN.md`

预期价值：减少上下文爆炸、减少开发者视角 UI 文案、让本地指令更清楚。

## Level 2：使用一份参考文档

适合问题主要是判断，而不是实现。

先看：

- `references/control-loss-gate.zh-CN.md`
- `references/skills-index-template.zh-CN.md`
- `references/personal-decision-lens-example.zh-CN.md`

预期价值：更好的停/继续判断、更清楚的 read-first 顺序、更少的重复 workflow。

## Level 3：安装一个 Skill

适合某个失败模式反复出现。

先看：

- `skills/project-continuity-control`
- `skills/straight-line-code-discipline`
- `skills/no-visible-meta-copy`

预期价值：让某些行为可以跨窗口、跨项目复用。

## Level 4：建立自己的 Harness

适合你已经知道自己反复遇到什么失败模式。

只在做过几个真实任务后再做：

1. 写下失败模式。
2. 提取曾经阻止它的最小规则。
3. 拿另一个任务验证。
4. 只有当它能减少返工或恢复掌控时，才保留。

## 规则

不要因为系统看起来优雅就升级层级。只有真实任务反复出现同一类痛点时，才升级。
