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

### Sprint Capacity: Turn-Based Self-Assessment

**AI teams use conversation turns as the capacity unit.**

| Metric | Default | Notes |
|--------|---------|-------|
| **Max turns per Sprint** | 35 | Configurable 25-40 |
| **Team self-assessment** | Yes | Team decides what they can commit |
| **PO cannot override** | Yes | PO sets priority, team sets capacity |

**Turn Budget Example (Default: 35 Turns)**
```
Sprint Planning:     3 turns
Execution:          28 turns (self-assessed)
Review:             2 turns
Retrospective:      2 turns
TOTAL:              35 turns
```

**Key principle**: Team commits to turns based on self-assessment. PO prioritizes, team decides capacity.

### Emergency Reprioritization

**PO can declare emergency and reprioritize. Team decides if they can absorb.**

```
PO: "Emergency: Critical bug affecting 50% of users."
SM: "Team, can we absorb 5 turns for hotfix?"
Team: "Yes" → Remove lower priority item, add hotfix
Team: "No" → PO decides if Sprint cancellation is warranted
```

---

## 🔍 Code Review Policy

### Review Requirement Matrix

| Code Type | Review Required | Why |
|-----------|----------------|-----|
| **Critical Path** (security, payment, auth) | 100% peer review | AI may produce flawed high-stakes code |
| **Regular Features** | Automated gates + optional | Core logic covered by tests |
| **Bug Fixes** | Automated gates + optional | Tests prove fix |
| **Documentation** | None | No execution risk |

### Definition of Done (DoD)

**Automated Gates (100% mandatory)**:
- ESLint/Prettier: 0 errors
- TypeScript: strict mode, 0 errors
- Unit Tests: core business logic
- SAST: 0 vulnerabilities
- CVE: 0 known vulnerabilities

**NOT in DoD**:
- Coverage percentage as number
- Testing setters/getters
- Testing config files

---

## 🤖 AI Agent Team

| Agent | Role | Accountable For |
|-------|------|-----------------|
| `agile-team:chief-product-owner` | Chief PO | Global vision, priorities, strategic decisions |
| `agile-team:product-owner` | PO | Challenge CPO, requirements breakdown, anti-dictatorship |
| `agile-team:scrum-master` | SM | Scrum process, impediments, Kanban/Blocker maintenance |
| `agile-team:architect` | Architect | Technical guidance |
| `agile-team:frontend` | Developer | Frontend delivery (TDD) |
| `agile-team:backend` | Developer | Backend delivery (TDD) |
| `agile-team:devops` | Developer | Infrastructure, deployment |
| `agile-team:ui-ux` | Specialist | Design (pulled when needed) |
| `agile-team:qa` | Specialist | Testing (in testing phase) |

### PO Anti-Dictatorship Protocol

**Product Owner exists to prevent CPO dictatorship:**
- Challenges CPO assumptions with evidence
- Provides alternative perspectives
- Breaks down requirements into testable stories
- Ensures team voice is heard

**Configure multiple PO instances via team settings** when additional product ownership is needed.

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
├── agents/             # 9个AI角色
│   ├── chief-product-owner.md
│   ├── product-owner.md          # Anti-dictatorship PO
│   ├── scrum-master.md
│   ├── architect.md
│   ├── frontend-engineer.md      # TDD-based
│   ├── backend-engineer.md       # TDD-based
│   ├── devops-engineer.md
│   ├── uiux-designer.md
│   └── qa-engineer.md
└── skills/            # 4个技能
    ├── agile-team-scrum-essentials/SKILL.md
    ├── agile-team-agile-best-practices/SKILL.md
    ├── agile-team-flow-rules/SKILL.md
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
