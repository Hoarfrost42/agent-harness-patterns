# Agent Harness Patterns

中文 | [English](README.md)

一套用于让长期 Agent Coding 工作保持可控的实践模式。

这不是一套普适理论，也不是“装上效率翻倍”的提示词包。它更像一个从真实重度使用中整理出来的工具箱：用一些小规则、Codex skills 和轻量参考模板，减少上下文膨胀、旧文档污染、过度执行，以及人在 AI 协作项目里逐渐失去掌控的问题。

## 核心想法

Agent Coding 失控不一定是因为模型代码写得差。很多时候，问题出在外层 harness 没有护栏，导致 agent：

- 把大量日志、diff、构建输出塞进上下文
- 相信已经过期的文档，而不是当前代码和运行状态
- 在人已经看不清项目地图时继续执行
- 用更多 SPEC 假装项目更清楚
- 把开发者备注写进用户可见文案
- 造出越来越多概念、抽象和中间层，最后没人看得懂

这个仓库把这些都当成 harness 问题处理。

## 仓库内容

```text
snippets/     可以粘进 AGENTS.md 或项目规则的小片段。
skills/       Codex 风格的 skill 示例，封装可复用流程。
references/   轻量模板和决策参考。
examples/     具体失败模式和 before/after 示例。
```

## 推荐从哪里开始

如果只想先花 5 分钟试一下，先看：

- [5 分钟快速开始](QUICKSTART.zh-CN.md)
- [采用层级](references/adoption-levels.zh-CN.md)

先看这三个：

1. `snippets/command-output.zh-CN.md`
2. `skills/project-continuity-control/SKILL.md`
3. `references/control-loss-gate.zh-CN.md`

它们解决的是最常见的几类问题：token/上下文爆炸、旧 handoff 或旧文档误导、agent 在真正需要恢复掌控时仍然继续执行。

## 安装 Skill

把某个 skill 文件夹复制到你的 Codex skills 目录：

```powershell
Copy-Item -Recurse .\skills\project-continuity-control "$env:USERPROFILE\.codex\skills\project-continuity-control"
```

安装或改名后，重启 Codex。

## 主要模式

### 保护命令输出

未知或可能很大的命令输出，应先截断、搜索、统计或缩小范围，再进入模型上下文。

### 恢复项目掌控

当人已经不知道哪些完成、哪些半成品、下一步该产出什么、什么算合格时，不要继续执行优先；先恢复控制面板。

### 当前事实优先

当前代码、运行行为、脚本、测试和生产状态，优先于写得很正式但可能已经过期的文档。

### 控制概念数量

代码短还不够。概念、manager、adapter、状态、文档、抽象层也要少到后续的人和 agent 能看懂。

### 用户可见文案不是开发备注

UI、公开页面、演示稿和报告里的文字应该写给用户看，不应该暴露实现说明、未来 TODO 或技术字段维护口径。

## 案例

- [SPEC 膨胀 before/after](examples/spec-bloat-before-after.zh-CN.md)
- [旧文档污染](examples/stale-doc-contamination.zh-CN.md)
- [项目失控闸门](examples/control-loss-gate.zh-CN.md)

## 使用方式

不要一开始整套全装。

更稳的方式是按痛点逐步使用：

1. 先加 `snippets/` 里的轻量规则。
2. 再参考 `references/` 里的控制面板和索引模板。
3. 只有当你真的遇到长项目、长上下文、多窗口、handoff 或 skill 调度问题时，再安装 `skills/`。

如果你想看这套工具箱背后的个人决策偏好，可以读 [个人决策镜头候选](references/personal-decision-lens-candidates.zh-CN.md)。它不是通用规则，而是一个如何把个人判断偏好沉淀成轻量 reference 的完整样例。

## 哲学

最佳实践是输入，不是权威。

可以学习强来源、工程经验和优秀理念，但应该先拆解、适配到自己的工作流，在真实任务里验证，再保留那些确实能降低摩擦或恢复掌控的部分。

## 友链

- [LINUX DO](https://linux.do/)

## 状态

这是一个早期个人实践仓库。它适合作为可试用的 pattern 工具箱，不是成熟 doctrine。
