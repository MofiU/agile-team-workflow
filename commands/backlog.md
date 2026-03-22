---
name: backlog
description: Product backlog management - create, update, list, and prioritize backlog items
---

# Backlog Management Command

Use this command to manage the product backlog following Scrum principles.

## Backlog Item Workflow

### Create Backlog Item
```
/backlog create [options]
```

Options:
- `--title` or `-t`: Item title (required)
- `--description` or `-d`: Detailed description
- `--type`: Item type - story|bug|task|tech-debt (default: story)
- `--priority` or `-p`: Priority - P1|P2|P3|P4 (default: P3)
- `--points` or `-s`: Story points (Fibonacci: 1|2|3|5|8|13|21)
- `--acceptance` or `-a`: Acceptance criteria (comma-separated)
- `--labels`: Labels/tags (comma-separated)
- `--sprint`: Assign to sprint ID

**Examples:**
```
/backlog create --title "User login" --description "Implement OAuth2 login" --priority P1 --points 5
/backlog create --title "Fix memory leak" --type bug --priority P2 --points 3
```

### List Backlog
```
/backlog list [options]
```

Options:
- `--status`: Filter by status (backlog|ready|in-progress|in-review|done)
- `--priority`: Filter by priority (P1|P2|P3|P4)
- `--sprint`: Filter by sprint ID
- `--all`: Show all items including completed (default: show incomplete)

### Update Backlog Item
```
/backlog update [item-id] [options]
```

Options:
- `--title`: Update title
- `--description`: Update description
- `--status`: Update status
- `--priority`: Update priority
- `--points`: Update story points
- `--assignee`: Assign to team member
- `--sprint`: Assign to sprint

**Status Flow:**
```
backlog → ready → in-progress → in-review → done
```

### Refine Backlog
```
/backlog refine [item-id]
```

Adds or updates:
- Acceptance criteria
- Technical notes
- Story points estimation

### Prioritize Backlog
```
/backlog prioritize [item-id-1] [item-id-2] ...
```

Reorders items by priority. Use after refinement to reorder the backlog.

## Priority Guidelines

| Priority | Description | Sprint Commitment |
|----------|-------------|------------------|
| P1 | Critical - Must do | Current sprint |
| P2 | High - Should do | Current sprint if capacity |
| P3 | Medium - Nice to have | Next sprint |
| P4 | Low - Backlog candidate | Future planning |

## Story Points Scale

Use Fibonacci sequence for estimation:
- **1 point**: Trivial task, very well understood
- **2 points**: Small task, some thought needed
- **3 points**: Medium task, may need discussion
- **5 points**: Large task, complex
- **8 points**: Very large, consider splitting
- **13 points**: Epic, definitely split
- **21 points**: Too large, must split

## Definition of Done

When marking items as done, ensure:
- Code is written and reviewed
- Tests are written and passing
- Acceptance criteria are met
- No blocking items remain
- Documentation updated if needed

## Data Storage

Backlog data is stored in `.claude/agile/backlog.json` within the project directory.
