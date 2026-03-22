---
name: blocker
description: Blocker and impediment management - create, track, and resolve blockers
---

# Blocker Management Command

Use this command to track and resolve impediments following Scrum practices.

## Blocker Workflow

### Create Blocker
```
/blocker create [options]
```

Options:
- `--description` or `-d`: Blocker description (required)
- `--impact`: Impact level - critical|high|medium|low (default: medium)
- `--blocked`: Team members blocked (comma-separated)
- `--items`: Affected backlog items (comma-separated)
- `--owner`: Who can resolve this (optional)

**Example:**
```
/blocker create --description "API credentials expired" --impact high --blocked "Alice,Bob" --items "AUTH-42,PAY-15"
```

### List Blockers
```
/blocker list [options]
```

Options:
- `--status`: Filter by status - active|resolved|all (default: active)
- `--impact`: Filter by impact level
- `--sprint`: Filter by sprint
- `--mine`: Show only blockers blocking you

### Resolve Blocker
```
/blocker resolve [blocker-id] [options]
```

Options:
- `--resolution` or `-r`: Resolution description (required)
- `--solved`: Problem solved (true|false)

**Example:**
```
/blocker resolve BLOCKER-123 --resolution "New API credentials obtained and rotated"
```

### Update Blocker
```
/blocker update [blocker-id] [options]
```

Options:
- `--description`: Update description
- `--impact`: Update impact level
- `--owner`: Assign owner
- `--escalate`: Escalate to higher authority

## Impact Levels

| Level | Definition | Response |
|-------|------------|----------|
| Critical | Sprint cannot continue | Immediate action |
| High | Significant delay expected | Within 4 hours |
| Medium | Some impact on progress | Within 1 day |
| Low | Minimal impact | Next planning |

## Blocker Categories

Common blocker types:
- **Technical**: Infrastructure, tools, dependencies
- **External**: Third-party services, vendors
- **Business**: Decisions, priorities, resources
- **Process**: Meetings, approvals, reviews
- **Knowledge**: Unclear requirements, skills gap

## Resolution Patterns

### Quick Wins
- Already fixed by someone else
- Misunderstanding clarified
- Simple configuration change

### Escalation Required
- Requires management decision
- Budget approval needed
- External dependency issue

### Long-term Fixes
- Technical debt to address
- Process improvement needed
- Tool upgrade required

## Data Storage

Blocker data is stored in `.claude/agile/blockers.json` within the project directory.

## Integration with Standup

Blockers raised in standups are automatically tracked:
```
/standup update --yesterday "Working on auth" --today "Continue auth" --blockers "Need API keys"
```

This creates a blocker entry linked to the standup.
