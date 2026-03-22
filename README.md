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

### Sprint Capacity: Configurable Conversation Turns

**Sprint capacity is measured in conversation turns, not story points.**

| Metric | Default | Adjustable | Reason |
|--------|---------|------------|--------|
| **Max turns per Sprint** | 35 | 25-40 | More buffer for emergencies |
| **Planning** | ~3-4 turns | Yes | Sprint Planning |
| **Execution** | ~18-22 turns | Yes | Actual development |
| **Review + Retro** | 2 turns | Fixed | Essential |

### Turn Budget Example (Default: 35 Turns)

```
Sprint Planning:     3 turns
Daily Scrums (10):  10 turns
Backlog Refinement:  2 turns
Development:         18 turns
Sprint Review:       1 turn
Sprint Retro:        1 turn

TOTAL:              35 turns (configurable)
```

**Team decides what they can commit. PO does NOT override.**

**Configurable**: `/team config --sprint-turns 30` (adjustable per team)

### Emergency Reprioritization

**PO can declare emergency and reprioritize. Team decides if they can absorb.**

```
PO: "Emergency: Critical bug affecting 50% of users."
SM: "Team, can we absorb 5 turns for hotfix?"
Team: "Yes" → Remove lower priority item, add hotfix
Team: "No" → PO decides if Sprint cancellation is warranted
```

### Quorum-Based Attendance

**Not everyone must be physically present. Quorum ensures valid decisions.**

| Ceremony | Quorum | Must Attend |
|----------|--------|-------------|
| Sprint Planning | 2/3 + All Devs | All Developers (no exception) |
| Daily Standup | None | Working developers |
| Sprint Review | 2/3 + stakeholders | - |
| Retrospective | 2/3 (incl PO) | PO must attend |

### Correct Sprint Flow

```
Sprint Planning (Quorum + All Developers)
     ↓
Daily Scrums (Working Developers)
     ↓
Sprint Review (Quorum + Stakeholders)
     ↓
Sprint Retrospective (Quorum Including PO)
     ↓
Next Sprint Planning (Fresh Start)
```

---

## 🤖 AI Agent Team (分层 PO 架构 - 2 APO)

| Agent | Role | Accountable For |
|-------|------|-----------------|
| `agile-team:chief-product-owner` | Chief PO | Global vision, cross-area priorities, strategic decisions |
| `agile-team:auth-product-owner` | Auth PO | Authentication, Authorization, Security |
| `agile-team:payment-product-owner` | Payment PO | Payments, Billing, Subscriptions |
| `agile-team:scrum-master` | SM | Scrum process, impediments, Kanban/Blocker maintenance |
| `agile-team:architect` | Architect | Technical guidance |
| `agile-team:frontend` | Developer | Frontend delivery |
| `agile-team:backend` | Developer | Backend delivery |
| `agile-team:devops` | Developer | Infrastructure, deployment |
| `agile-team:ui-ux` | Specialist | Design (pulled when needed) |
| `agile-team:qa` | Specialist | Testing (in testing phase) |

### PO 分层架构（只有2个APO）

```
Chief PO (全局战略)
    │
    ├── @agile-team:auth-product-owner
    │       └── Auth 领域：登录、安全、MFA、OAuth
    │
    └── @agile-team:payment-product-owner
            └── Payment 领域：支付、计费、订阅
```

**决策分层**：
- **Chief PO 决定**：跨领域优先级、资源分配、战略方向
- **Auth PO 决定**：Auth 领域内优先级、需求、安全策略
- **Payment PO 决定**：Payment 领域内优先级、需求、计费策略

---

## 🔑 Critical Ceremonies

### Sprint Planning (Quorum: 2/3 + All Developers)
- PO presents priorities
- Team commits to Sprint Goal
- **All developers must attend** (no proxy, no exception)
- **Team decides capacity, not PO or SM**

### Sprint Review (Quorum: 2/3 + Stakeholders)
- **Developers demo their own work**
- PO inspects items against acceptance criteria
- Stakeholders provide feedback
- **NOT a handoff or approval meeting**

### Sprint Retrospective (Quorum: 2/3 Including PO)
- Team reflects on how to improve
- SM facilitates
- Action items with owners
- **PO participates as team member**
- **Async alternative**: `@agile-team:scrum-master` 发起异步回顾

---

## ❌ What This Is NOT

- Not a command-and-control structure
- Not SM managing developers
- Not PO approving sprints
- Not rigid ceremonies (quorum allows flexibility)
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
├── agents/             # 10个AI角色 (分层PO: 2APO)
│   ├── chief-product-owner.md
│   ├── auth-product-owner.md      # Auth领域专家
│   ├── payment-product-owner.md   # Payment领域专家
│   ├── scrum-master.md
│   ├── architect.md
│   ├── frontend-engineer.md
│   ├── backend-engineer.md
│   ├── devops-engineer.md
│   ├── uiux-designer.md
│   └── qa-engineer.md
└── skills/            # 4个技能
    ├── agile-team-scrum-guide/SKILL.md
    ├── agile-team-agile-best-practices/SKILL.md
    ├── agile-team-dynamic-team/SKILL.md
    └── agile-team-handoff-workflow/SKILL.md
```

---

## 🔧 Installation

```bash
git clone https://github.com/MofiU/agile-team-workflow ~/.claude/plugins/agile-team-workflow
```

---

## License

MIT
