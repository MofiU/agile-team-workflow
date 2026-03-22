# Agile Team Workflow Plugin for Claude Code

A comprehensive Claude Code plugin that brings an entire Agile team into your development workflow. Manages sprints, backlogs, standups, retrospectives, reviews, and blockers using the Scrum framework (2025 Guide).

## 🤖 AI Agent Team

This plugin provides 8 specialized AI agents representing your Agile team:

| Agent | Role | Color |
|------|------|-------|
| `agile:product-owner` | Product Owner - maximizes value, owns backlog | #FF6B6B |
| `agile:scrum-master` | Scrum Master - facilitates ceremonies, removes blockers | #45B7D1 |
| `agile:architect` | Architect - technical decisions, system design | #9B59B6 |
| `agile:frontend` | Frontend Engineer - UI development | #3498DB |
| `agile:backend` | Backend Engineer - API and services | #27AE60 |
| `agile:devops` | DevOps Engineer - CI/CD, infrastructure | #E67E22 |
| `agile:ui-ux` | UI/UX Designer - user experience | #E91E63 |
| `agile:qa` | QA Engineer - testing and quality | #00BCD4 |

## 📋 Commands

### Sprint Management
```bash
/sprint create --name "Sprint 1" --goal "Complete user auth" --duration 2
/sprint start sprint-123
/sprint end sprint-123
/sprint list
/sprint report sprint-123
```

### Backlog Management
```bash
/backlog create --title "User Login" --priority P1 --points 5
/backlog list --status ready
/backlog update AUTH-42 --status done
```

### Daily Standup
```bash
/standup start --format three-questions
/standup update --member "John" --yesterday "Completed login" --today "API integration" --blockers "Need keys"
/standup summary
```

### Sprint Retrospective
```bash
/retro start --format start-stop-continue
/retro feedback --type start --content "Start daily code reviews"
/retro actions --top 5
```

### Sprint Review
```bash
/review start --sprint sprint-123
/review demo --title "Auth Feature" --url "https://demo.example.com"
/review feedback --type positive --content "Great UX!"
```

### Blocker Management
```bash
/blocker create --description "API credentials expired" --impact high --blocked "Alice,Bob"
/blocker list --status active
/blocker resolve BLOCKER-123 --resolution "New credentials issued"
```

## 🎯 Skills

This plugin includes two reference skills:

- **scrum-guide**: 2025 Scrum Guide reference with all Scrum principles
- **agile-best-practices**: Practical guidance for estimation, retrospectives, and continuous improvement

## 📦 Installation

### Option 1: From GitHub

```bash
git clone https://github.com/MofiU/agile-team-workflow ~/.claude/plugins/agile-team-workflow
```

### Option 2: Add to your Claude Code config

In your `.claude/settings.json`:

```json
{
  "plugins": [
    "agile-team-workflow"
  ]
}
```

Or use the `/plugin install` command in Claude Code:

```
/plugin install MofiU/agile-team-workflow
```

## 🏗️ Architecture

```
agile-team-workflow/
├── .claude-plugin/
│   └── plugin.json          # Plugin manifest
├── commands/                 # Slash commands
│   ├── sprint.md
│   ├── backlog.md
│   ├── standup.md
│   ├── retro.md
│   ├── review.md
│   └── blocker.md
├── agents/                  # AI agents
│   ├── product-owner.md
│   ├── scrum-master.md
│   ├── architect.md
│   ├── frontend-engineer.md
│   ├── backend-engineer.md
│   ├── devops-engineer.md
│   ├── uiux-designer.md
│   └── qa-engineer.md
├── skills/                  # Reference skills
│   ├── scrum-guide.md
│   └── agile-best-practices.md
└── README.md
```

## 📁 Data Storage

Agile data is stored in `.claude/agile/` within your project:

```
.claude/agile/
├── sprints.json           # Sprint records
├── backlog.json          # Product backlog items
├── standups.json         # Daily standup entries
├── retros.json           # Retrospective feedback
├── retro-actions.json     # Action items from retros
├── reviews.json          # Sprint reviews
├── demos.json            # Demo records
├── review-feedback.json  # Feedback from reviews
└── blockers.json         # Blockers and impediments
```

## 📖 Documentation

### 2025 Scrum Guide Compliance

This plugin follows the 2025 Scrum Guide principles:
- Five events: Sprint, Sprint Planning, Daily Scrum, Sprint Review, Sprint Retrospective
- Three accountabilities: Product Owner, Scrum Master, Developers
- Empiricism: Transparency, Inspection, Adaptation
- AI recognized as an actor in Scrum (Expansion Pack 2025)

### Role Hierarchy

Per the 2025 Scrum Guide:
1. **Product Owner** is the highest authority for product decisions
2. **Scrum Master** serves both PO and team (servant leadership)
3. **No Project Manager** - Development Team is self-organizing

## 🔧 Configuration

Create a `.claude/agile-local.md` file in your project for custom settings:

```markdown
---
team-size: 5
sprint-duration: 2
working-days: 5
default-priority: P3
---
```

## 🤝 Contributing

Contributions welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## 📄 License

MIT

## 🙏 Acknowledgments

- Scrum Guide 2025 - https://scrumguides.org
- Claude Code Plugin System - Anthropic
