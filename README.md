# Agile Team Workflow Plugin

Claude Code plugin for complete agile team workflow with Scrum framework (2025 Guide).

## ⚠️ Design Correction

This README reflects **correct Scrum 2025**, not your original design. Key corrections:

| Your Original | Correct Scrum |
|--------------|--------------|
| SM delivers → PO approves | Team demonstrates → PO inspects items |
| SM commands next sprint | Team commits based on capacity |
| PO is "highest authority" | PO is product expert, not manager |
| Dynamic = skip ceremonies | Core ceremonies require full team |
| Handoff workflow | Sprint Review (collaboration) |

---

## 🎯 Core Design

### Role Responsibilities

| Role | Accountable For | NOT Accountable For |
|------|-----------------|-------------------|
| **Product Owner** | Product value, backlog priorities, acceptance | Sprint commitment, team capacity |
| **Scrum Master** | Scrum process, ceremonies, impediment removal | Team's technical decisions |
| **Developers** | Deliverables, self-organization, DoD | PO's business priorities |
| **PO + SM + Developers** | The Sprint | Individual glory |

### Key Principles (Scrum 2025)

1. **Empiricism**: Transparency, Inspection, Adaptation
2. **Whole Team**: All three roles collaborate
3. **Self-Organization**: Team decides how to work
4. **Customer Collaboration**: Not contract negotiation

### Correct Sprint Flow

```
Sprint Planning (Full Team Required)
     ↓
Daily Scrums (Working Developers)
     ↓
Sprint Review (Team Demonstrates → PO Inspects)
     ↓
Sprint Retrospective (Full Team Required)
     ↓
Next Sprint Planning (Fresh Start)
```

---

## 📋 Commands (11 total)

### 1. Requirements
```bash
/requirements submit --title "登录功能" --from "用户A" --priority P1
/requirements approve REQ-123
```

### 2. Backlog Management
```bash
/backlog add --title "Google登录" --from-req REQ-123 --priority P1
/backlog view --top 20
/backlog prioritize AUTH-1 AUTH-2
```

### 3. Team
```bash
/team view
/team phase development
/team ceremony planning --sprint sprint-123
```

### 4. Sprint Management
```bash
/sprint planning --goal "Complete auth module" --duration 2
/sprint daily --yesterday "Done" --today "Doing" --blockers "None"
/sprint cancel sprint-123 --reason "Goal obsolete"
```

### 5. Kanban Board
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
/review demo --title "认证模块" --presenter @alice
/review inspect --item AUTH-3 --decision accept
/review feedback --type suggestion --content "Consider mobile"
```

### 10. External Handoff
```bash
/handoff initiate --sprint sprint-123 --to DevOps --type deployment
/handoff confirm HANDOFF-456 --status accepted --timeline "Friday"
```

### 11. Progress
```bash
/progress sprint sprint-123
/progress team sprint-123
/progress po
/progress sm
```

---

## 🤖 AI Agent Team

| Agent | Role | Accountable For |
|-------|------|-----------------|
| `agile:product-owner` | PO | Product vision, backlog, value |
| `agile:scrum-master` | SM | Scrum process, impediments |
| `agile:architect` | Architect | Technical guidance |
| `agile:frontend` | Developer | Frontend delivery |
| `agile:backend` | Developer | Backend delivery |
| `agile:devops` | Developer | Infrastructure, deployment |
| `agile:ui-ux` | Specialist | Design (pulled when needed) |
| `agile:qa` | Specialist | Testing (in testing phase) |

---

## 🔑 Critical Ceremonies

### Sprint Planning (Required: SM + PO + All Developers)
- PO presents priorities
- Team commits to Sprint Goal
- **Team decides capacity, not PO or SM**

### Sprint Review (Required: Full Team + Stakeholders)
- **Developers demo their own work**
- PO inspects items against acceptance criteria
- Stakeholders provide feedback
- **NOT a handoff or approval meeting**

### Sprint Retrospective (Required: Full Team Including PO)
- Team reflects on how to improve
- SM facilitates
- Action items with owners
- **PO participates as team member**

---

## ❌ What This Is NOT

- Not a command-and-control structure
- Not SM managing developers
- Not PO approving sprints
- Not optional ceremonies
- Not waterfall with daily standups

---

## ✅ What This IS

- Empiricism over big upfront planning
- Self-organizing team
- Collaborative inspection
- Continuous improvement
- Product-focused value delivery

---

## 📁 Data Storage

```
.claude/agile/
├── requirements.json
├── backlog.json
├── team.json
├── sprints.json
├── board.json
├── standups.json
├── blockers.json
├── retros.json
├── reviews.json
├── handoffs.json
└── progress.json
```

---

## 🏗️ Architecture

```
agile-team-workflow/
├── .claude-plugin/
│   └── plugin.json
├── commands/           # 11个命令
├── agents/             # 8个AI角色
└── skills/            # 4个技能
    ├── scrum-guide.md
    ├── agile-best-practices.md
    ├── dynamic-team.md
    └── handoff-workflow.md
```

---

## 🔧 Installation

```bash
git clone https://github.com/MofiU/agile-team-workflow ~/.claude/plugins/agile-team-workflow
```

---

## License

MIT
