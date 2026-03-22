# Agile Team Workflow Plugin

Claude Code plugin for complete agile team workflow with Scrum framework.

## 🎯 Core Design

### Role Responsibilities

| Role | Responsibilities |
|------|------------------|
| **Product Owner** | Owns product, receives requirements, validates delivery, prioritizes backlog |
| **Scrum Master** | Controls iteration lifecycle, orchestrates team, removes blockers |
| **Team Members** | Execute tasks, report progress, participate selectively |

### Key Principles

1. **Dynamic Team Composition** - Not all members in every meeting
2. **SM Controls Rhythm** - SM decides who attends what
3. **Clear Handoff** - SM delivers → PO validates → next iteration
4. **Continuous PO** - PO always investigating product, adjusting backlog
5. **User Requirements** - New requirements flow in continuously

### User Flow

```
用户提交需求
     ↓
PO接收 → 创建/更新Backlog
     ↓
SM控制迭代
  ├─ 设计阶段: PO + UI/UX + Architect (developers excluded)
  ├─ 开发阶段: SM + Developers (UI/UX excluded unless flagged)
  ├─ 测试阶段: SM + QA + Developers
  └─ ...
     ↓
SM交付 → PO验收
     ↓
PO: 验收通过 → 命令SM继续下一轮
     ↓
PO: 持续优化产品 + 调整优先级
```

## 📋 Commands (11 total)

### 1. Requirements (用户需求)
```bash
/requirements submit --title "登录功能" --from "用户A" --priority P1
/requirements view --status pending
/requirements approve REQ-123
```

### 2. Product Backlog (PO管理)
```bash
/backlog add --title "Google登录" --from-req REQ-123 --priority P1 --points 8
/backlog view --top 20
/backlog prioritize AUTH-1 AUTH-2
```

### 3. Team Composition (SM管理)
```bash
/team view
/team phase development  # 设置当前阶段
/team ceremony planning --include "SM,PO,Architect,Frontend"
```

### 4. Sprint Management (SM控制)
```bash
/sprint create --goal "完成用户认证" --duration 2
/sprint start sprint-123
/sprint end sprint-123
```

### 5. Kanban Board (个人任务)
```bash
/board view --sprint sprint-123
/board task --title "实现登录" --assignee "Alice"
/board move TASK-123 in-progress
/board mine --status todo
```

### 6. Daily Standup
```bash
/standup start sprint-123
/standup update --yesterday "完成表单" --today "API对接"
/standup summary
```

### 7. Blocker Tracking
```bash
/blocker track --description "API超时" --impact high
/blocker view --status active
/blocker resolve BLOCKER-123
```

### 8. Sprint Retrospective
```bash
/retro start --format start-stop-continue
/retro feedback --type continue --content "站会很有用"
/retro actions
```

### 9. Sprint Review
```bash
/review schedule --sprint sprint-123
/review demo --title "认证模块"
/review feedback --type positive
```

### 10. Handoff (交接)
```bash
/handoff request --sprint sprint-123 --deliverables "Auth模块" --status completed
/handoff review HANDOFF-123 --decision accepted
/handoff next --focus "支付集成" --continue true
```

### 11. Progress (进度查看)
```bash
/progress sprint sprint-123  # Sprint进度
/progress team sprint-123   # 团队进度
/progress po                # PO视角
/progress sm                # SM视角
/progress status            # 利益相关者视角
```

## 🤖 AI Agent Team

| Agent | Role | Color |
|-------|------|-------|
| `agile:product-owner` | PO | #FF6B6B |
| `agile:scrum-master` | SM (controls iteration) | #45B7D1 |
| `agile:architect` | 架构师 | #9B59B6 |
| `agile:frontend` | 前端工程师 | #3498DB |
| `agile:backend` | 后端工程师 | #27AE60 |
| `agile:devops` | DevOps | #E67E22 |
| `agile:ui-ux` | UI/UX设计师 | #E91E63 |
| `agile:qa` | QA工程师 | #00BCD4 |

## 📁 Data Storage

```
.claude/agile/
├── requirements.json    # 用户需求
├── backlog.json        # 产品待办
├── team.json          # 团队组成
├── sprints.json       # 迭代记录
├── board.json        # 看板
├── standups.json      # 站会
├── blockers.json      # 阻塞
├── retros.json        # 回顾
├── reviews.json       # 评审
├── handoffs.json     # 交接记录
└── progress.json     # 进度数据
```

## 🏗️ Architecture

```
agile-team-workflow/
├── .claude-plugin/
│   └── plugin.json
├── commands/           # 11个命令
│   ├── requirements.md   # 需求
│   ├── backlog.md      # 待办
│   ├── team.md         # 团队
│   ├── sprint.md       # 迭代
│   ├── board.md        # 看板
│   ├── standup.md      # 站会
│   ├── blocker.md      # 阻塞
│   ├── retro.md        # 回顾
│   ├── review.md       # 评审
│   ├── handoff.md      # 交接
│   └── progress.md      # 进度
├── agents/             # 8个AI角色
└── skills/            # 4个技能
    ├── scrum-guide.md
    ├── agile-best-practices.md
    ├── dynamic-team.md
    └── handoff-workflow.md
```

## 📖 Key Skills

### Dynamic Team
- 不同阶段不同成员参会
- SM orchestrates participation
- Pull-in pattern when needed

### Handoff Workflow
- SM → PO 清晰交接
- PO validates delivery
- PO commands next iteration

### Scrum Guide (2025)
- SM控制迭代生命周期
- PO对产品负责
- 团队自组织

## 🔧 Installation

```bash
git clone https://github.com/MofiU/agile-team-workflow ~/.claude/plugins/agile-team-workflow
```

## License

MIT
