---
name: agile-team:scrum-essentials
description: Scrum核心原则和AI团队适应 - 用于敏捷团队工作流程。当需要了解Scrum框架、角色职责、事件规则时使用。
---

# Scrum Essentials (2025)

## 三大支柱

1. **Transparency** - 共同理解
2. **Inspection** - 定期检查
3. **Adaptation** - 适时调整

## 三个角色

| 角色 | 职责 | 不负责 |
|------|------|--------|
| **Product Owner** | 产品价值、backlog优先级 | Sprint容量、技术决策 |
| **Scrum Master** | 流程facilitator、blocker清除 | 团队的技术决策 |
| **Developers** | 交付物、自组织、DoD定义 | 业务优先级 |

## 五个事件

| 事件 | 目的 |时长(2周Sprint) |
|------|------|----------------|
| Sprint Planning | 决定做什么、如何做 | 4小时 |
| Daily Scrum | 进展、blocker、调整 | 15分钟/天 |
| Sprint Review | 演示、inspect、adapt | 4小时 |
| Sprint Retrospective | 反思、改进 | 3小时 |

## Sprint规则

- Sprint是固定长度容器(1-4周)
- Sprint内不允许损害Goal的变更
- 只有在Goal过时时才取消Sprint

## Sprint Goal

- **PO commits to Product Goal**
- **Team commits to Sprint Goal**
- **DoD is commitment for Increment**

## Self-Organization

- 团队决定如何完成工作
- 无外部强加的方法
- 跨职能团队，不分sub-team

---

## AI团队适应

### Turn-based容量

- AI团队使用对话轮次作为容量单位
- 默认35 turns，可配置25-40
- Team评估自己能commit多少turns
- PO不能override团队容量

### Turn分配示例(35 turns)

```
Planning:     3 turns
Execution:   28 turns
Review:      2 turns
Retro:       2 turns
TOTAL:      35 turns
```

### 事件驱动协调

- SM在需要时介入，非固定时间
- 最小化同步会议
- 最大化并行工作

### 关键路径代码审查

- 安全/支付/认证代码需要100% peer review
- 常规代码：自动化门控通过即可
- 详见 `agile-team:flow-rules`

---

## 正确Sprint流程

```
Sprint Planning (Quorum: 2/3 + All Developers)
     ↓
Daily Scrum (Event-driven)
     ↓
Sprint Review (Quorum + Stakeholders)
     ↓
Sprint Retrospective (Quorum: 2/3 + PO)
     ↓
Next Sprint Planning (Fresh Start)
```

---

## Resources

- Official Scrum Guide: https://scrumguides.org
