---
name: team
description: Team composition - SM manages who participates in which ceremonies
---

# Team Management Command

Manage team composition dynamically. SM decides who participates in which ceremonies based on the current phase.

## Team Composition

### View Team
```
/team view
```

Shows current team members and their roles.

### Add Member
```
/team add [options]
```

Options:
- `--name`: Member name (required)
- `--role`: Role (architect|frontend|backend|devops|uiux|qa)
- `--skills`: Special skills (comma-separated)

### Remove Member
```
/team remove [member-name]
```

### Set Team Phase
```
/team phase [phase-name]
```

Phases:
- `discovery`: Requirements gathering, design
- `planning`: Sprint planning, backlog refinement
- `development`: Active development
- `testing`: QA testing, bug fixes
- `deployment`: Release, deployment
- `review`: Sprint review, retrospective

**Example:**
```
/team phase development
```

## Ceremony Participation

### Who Attends What

| Ceremony | Required Participants |
|----------|---------------------|
| Sprint Planning | SM, PO, relevant developers, Architect |
| Daily Standup | Team members working this Sprint |
| Sprint Review | SM, PO, Stakeholders (invited by PO) |
| Retrospective | Full team |
| Backlog Refinement | SM, PO, developers working on next items |

### Configure Participation
```
/team ceremony [ceremony-name] --include [members] --exclude [members]
```

**Example:**
```
/team ceremony planning --include "SM,PO,Architect,Frontend" --exclude "QA,DevOps"
/team ceremony daily --include "Frontend,Backend" --exclude "Designer"
```

## Phase-Based Defaults

### Discovery Phase
```
/team phase discovery
```
Includes: SM, PO, UI/UX, Architect
Excludes: Developers (until design is ready)

### Development Phase
```
/team phase development
```
Includes: SM, PO, Developers, DevOps
Excludes: UI/UX (unless flagged)

### Testing Phase
```
/team phase testing
```
Includes: SM, QA, Developers
Excludes: UI/UX

## Team Notifications

### Notify Members
```
/team notify [message] --to [ceremony-name]
```

Sends notifications about ceremonies to appropriate participants.

## Data Storage

Team data stored in `.claude/agile/team.json`.
