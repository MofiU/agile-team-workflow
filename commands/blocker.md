---
name: blocker
description: Blocker management - track impediments, SM removes, decisions made
---

# Blocker Management Command

Blockers are impediments that prevent the team from delivering. SM works to remove them.

## Blocker Workflow

### Track Blocker
```
/blocker track [options]
```

Options:
- `--description` or `-d`: Blocker description (required)
- `--impact`: critical|high|medium|low (default: medium)
- `--affected`: Affected tasks or team members
- `--task`: Related task ID

**Example:**
```
/blocker track --description "API credentials expired" --impact high --affected "AUTH-42" --task TASK-123
```

### View Blockers
```
/blocker view [options]
```

Options:
- `--status`: active|resolved|all (default: active)
- `--impact`: Filter by impact
- `--sprint`: Filter by Sprint

### Blocker Details
```
/blocker detail [blocker-id]
```

Shows:
- Description
- Impact level
- Affected tasks
- Age
- Resolution history

### Resolve Blocker
```
/blocker resolve [blocker-id] --resolution "New credentials obtained"
```

Mark blocker as resolved.

### Update Blocker
```
/blocker update [blocker-id] [options]
```

Options:
- `--description`: Update description
- `--impact`: Update impact level
- `--notes`: Add resolution notes

### Escalate Blocker
```
/blocker escalate [blocker-id] --to [stakeholder]
```

Escalate critical blockers.

## Impact Levels

| Level | Definition | Response |
|-------|------------|----------|
| Critical | Sprint cannot continue | Immediate action |
| High | Significant delay expected | Same day |
| Medium | Some impact | Within 2 days |
| Low | Minimal impact | Next planning |

## Blocker Categories

- **Technical**: Infrastructure, tools, dependencies
- **External**: Third-party, vendors
- **Business**: Decisions, priorities
- **Process**: Meetings, approvals
- **Knowledge**: Requirements, skills

## Your Role as SM

### When Blockers Arise
1. **Acknowledge** the blocker
2. **Assess** impact on Sprint
3. **Identify** removal path
4. **Work** to remove or escalate
5. **Track** until resolved

### Removal Strategies
- Handle yourself if possible
- Escalate to appropriate authority
- Find workarounds
- Adjust scope if necessary

## Data Storage

Blocker data stored in `.claude/agile/blockers.json`.
