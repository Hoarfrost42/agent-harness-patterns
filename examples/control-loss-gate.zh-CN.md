# 案例：项目失控闸门

## 之前

一个长期项目里已经有能跑的代码、几份 SPEC，以及很多半成品想法。

Agent 继续提出下一批实现：

```text
接下来我会补剩下的页面、接上状态管理、更新文档并运行测试。
```

但人的真实问题已经变成：

- 看不清哪些部分已经完成
- 看不清哪些文档还是当前事实
- 看不清这个阶段到底该产出什么
- 判断不了这个方向还值不值得继续

继续执行只会让项目更难掌控。

## 触发信号

当用户说出类似这些话时，触发项目失控闸门：

```text
先停一下。
我感觉这个项目有点失控。
我现在不知道我们到底在产出什么。
我不确定这个方向还值不值得做。
```

## 之后

Agent 停止执行优先推进，先输出一个紧凑控制面：

```md
# Project Control Surface

## Current Phase
MVP validation.

## Done
- Local app starts.
- Main workflow has one happy path.

## Half-Done
- Secondary states exist but are not verified.
- Visual polish is inconsistent.

## Unverified
- Error paths.
- Production build.
- User-facing copy.

## Stale Or Suspect
- `docs/v1-plan.md`: replaced by current implementation.
- `docs/backend-contract-old.md`: conflicts with current routes.

## Expected Output
A demoable MVP with one reliable path and known gaps.

## Acceptance Standard
Runs locally, happy path works, build passes, gaps are listed.

## Next Decisions
1. Polish the existing path or expand scope?
2. Delete stale docs or archive them?
3. Add tests now or after the demo pass?
```

## 规则

当人失去项目地图时，清晰本身就是当前交付物。
