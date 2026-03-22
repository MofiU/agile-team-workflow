# Agile Team Workflow Plugin for Claude Code

Complete agile team workflow management with Scrum framework. **SM controls the iteration**, PO manages product, team has personal Kanban boards.

## 🎯 Core Design

### Role Responsibilities

| Role | Responsibilities |
|------|-----------------|
| **Product Owner** | Receives user requirements, owns backlog, sets priorities |
| **Scrum Master** | Controls iteration lifecycle, facilitates ceremonies, removes blockers |
| **Team Members** | Execute tasks, report progress, participate in retrospectives |

### User Flow

```
用户提交需求 → PO接收需求
     ↓
PO创建团队，分配任务
     ↓
SM控制迭代 → 每日站会 → 任务板更新
     ↓
迭代结束 → SM确认交付 → 下一轮迭代
```

## 📋 Commands

### 1. Requirements (用户需求)
```bash
/requirements submit --title "登录功能" --from "客户A" --priority P1
/requirements view --status pending
/requirements approve REQ-123
```

### 2. Product Backlog (PO管理)
```bash
/backlog add --title "Google登录" --from-req REQ-123 --priority P1 --points 8
/backlog view --top 20
/backlog prioritize AUTH-1 AUTH-2 PAY-1
```

### 3. Sprint Management (SM控制)
```bash
/sprint create --goal "完成用户认证模块" --duration 2
/sprint start sprint-123
/sprint end sprint-123
/sprint report sprint-123
```

### 4. Kanban Board (个人任务清单)
```bash
/board view --sprint sprint-123
/board task --title "实现登录表单" --assignee "Alice" --story-id AUTH-42
/board move TASK-123 in-progress
/board mine --status todo
```

### 5. Daily Standup
```bash
/standup start sprint-123
/standup update --yesterday "完成表单" --today "API对接" --blockers "需要凭证"
/standup summary
```

### 6. Blocker Tracking
```bash
/blocker track --description "API超时" --impact high --affected "PAY-15"
/blocker view --status active
/blocker resolve BLOCKER-123 --resolution "已重启服务"
```

### 7. Sprint Retrospective
```bash
/retro start --format start-stop-continue
/retro feedback --type continue --content "每日站会很有用"
/retro actions --top 5
```

### 8. Sprint Review
```bash
/review schedule --sprint sprint-123 --participants "CEO,CTO"
/review demo --title "认证模块" --url "https://demo.example.com"
/review feedback --type positive --content "用户体验很好"
```

## 🤖 AI Agent Team

| Agent | Role | Description |
|-------|------|-------------|
| `agile:product-owner` | Product Owner | Receives requirements, manages backlog |
| `agile:scrum-master` | Scrum Master | Controls iteration, removes blockers |
| `agile:architect` | Architect | Technical decisions, system design |
| `agile:frontend` | Frontend | UI development |
| `agile:backend` | Backend | API and services |
| `agile:devops` | DevOps | CI/CD, infrastructure |
| `agile:ui-ux` | UI/UX | Design, usability |
| `agile:qa` | QA | Testing, quality |

## 📁 Data Storage

```
.claude/agile/
├── requirements.json    # 用户需求
├── backlog.json        # 产品待办
├── sprints.json         # 迭代记录
├── board.json          # 看板数据
├── standups.json       # 每日站会
├── retros.json         # 回顾会议
├── blockers.json       # 阻塞管理
└── reviews.json        # 评审会议
```

## 🏗️ Architecture

```
agile-team-workflow/
├── .claude-plugin/
│   └── plugin.json
├── commands/
│   ├── requirements.md   # 需求管理
│   ├── backlog.md        # 产品待办
│   ├── sprint.md         # 迭代管理
│   ├── board.md          # 看板(个人任务)
│   ├── standup.md       # 站会
│   ├── blocker.md        # 阻塞
│   ├── retro.md          # 回顾
│   └── review.md         # 评审
├── agents/
│   ├── product-owner.md
│   ├── scrum-master.md
│   └── ... (6 more)
└── skills/
    ├── scrum-guide.md
    └── agile-best-practices.md
```

## 📖 2025 Scrum Guide

- **SM控制迭代**：SM负责整个迭代的生命周期
- **PO对产品负责**：接收需求，管理待办列表
- **团队自组织**：每个成员有自己的任务清单
- **看板追踪**：任务可中断，可继续
- **阻塞管理**：及时发现和解决障碍

## 🔧 Installation

```bash
git clone https://github.com/MofiU/agile-team-workflow ~/.claude/plugins/agile-team-workflow
```

## License

MIT
