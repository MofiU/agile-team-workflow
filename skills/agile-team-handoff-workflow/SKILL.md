---
name: agile-team:handoff-workflow
description: Sprint Review协作流程 - 团队演示、PO检查、增量交付。
---

# Sprint Review & Collaboration

## Sprint Review是协作检查

Sprint Review不是handoff，而是**协作检查**：

- 团队演示他们构建的内容
- PO和利益相关者检查和adapt
- 协作，不是approval

---

## Sprint Review正确流程

### 1. 团队呈现Increment

```
SM: "Sprint 12 Review。团队，请演示。"

Team Member 1: 演示功能A
Team Member 2: 演示功能B
```

### 2. 协作反馈

```
PO: "功能B - 能看一下错误处理吗？"
Developer: *演示*

SM: "记录。PO，有任何accept的blocker吗？"
PO: "没有，B符合标准。A需要一个小修复。"
```

### 3. PO做Item决策

| 决策 | 含义 |
|------|------|
| **Accept** | Item符合DoD → 移到Done |
| **Reject** | Item不符合标准 → 返回backlog |
| **Partial** | Item需要返工 → backlog with priority |

### 4. 一起更新Backlog

- 从review添加新洞察
- 根据反馈调整优先级
- 计划从planning会议开始，不从review开始

---

## Sprint Review vs Handoff

### Sprint Review（团队内）

团队向PO和利益相关者演示：
- 展示工作软件
- 讨论已完成的内容
- 透明说明未完成的内容
- 接收反馈

### 外部Handoff（给其他团队）

```
Sprint Review: "Auth模块完成了。"

Ops: "好。我们下周二部署。"

Team: "这是runbook。"
```

这是**协调**，不是**approval**。

---

## Definition of Done vs Acceptance Criteria

### DoD (Team's Commitment)

- 代码已review
- 测试通过
- 已部署到环境
- 符合团队质量标准

### Acceptance Criteria (PO's Requirement)

- 业务价值已交付
- 用户需求已满足
- 利益相关者期望已达成

**关键区别**: DoD是二进制的(完成/未完成)。Acceptance criteria可能需要协商。

---

## Sprint Review中的SM角色

SM facilitates，但**团队presents**：

```
SM: "Sprint Review for Sprint 12。团队，请演示。"

Team Member 1: Shows feature A
Team Member 2: Shows feature B

PO: "Feature B - can we see error handling?"
Developer: *demonstrates*

SM: "Recording that. PO, any blockers for acceptance?"
PO: "No, B meets criteria. A needs one fix."
SM: "Developer, please update A to 'needs rework'."
```

---

## 团队自组织

Sprint Review结束后 → Next Sprint Planning是**全新开始**：

```
Sprint 12 Review完成
        ↓
SM: "好的协作。明天休息一天。"
        ↓
Sprint 13 Planning（新会议）
        ↓
PO: "基于反馈，优先级现在是X, Y, Z"
Team: "基于容量，我们只能commit X和Y"
SM: "锁定。拆成任务。"
```

**PO不"批准"或"命令"下一个sprint。** Team基于他们的容量和PO的优先级commit。

---

## 实际团队协作示例

### 场景1：Item需要修复

```
PO: "Item AUTH-3不符合acceptance criteria。"

SM: "缺什么？"

PO: "错误消息对用户不友好。"

Team Dev: "这是快速修复。1小时。"

SM: "今天能完成吗？"

Team: "能。"

SM: "更新AUTH-3到'in progress'，目标今天。"

        ↓
Later that day:

Team: "AUTH-3已修复。"
SM: "PO，请验证。"
PO: "已批准。移到Done。"
```

### 场景2：新item加入backlog

```
Stakeholder: "集成system Z怎么样？"

Team: "下个Sprint planning时处理。"

SM: "记录到backlog。PO确认优先级。"
```

---

## Blocker Resolution at Review

如果PO在Sprint Review拒绝item：

```
PO: "Item AUTH-3不符合acceptance criteria。"

SM: "缺什么？"

PO: "错误消息不友好。"

Team Dev: "快速修复，1小时。"

SM: "能今天完成吗？"

Team: "能。"

SM: "Update AUTH-3 to 'in progress', target today."
```

---

## 协作价值

正确的Sprint Review创造：
- **Team accountability** - 团队展示自己的工作
- **PO as product expert** - PO检查产品，不是批准交付
- **SM as facilitator** - SM协调，不是中间人
- **Continuous improvement** - 持续改进的反馈循环
