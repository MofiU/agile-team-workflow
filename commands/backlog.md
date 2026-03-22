---
name: backlog
description: Product Backlog - PO owns the backlog, items flow from requirements
---

# Product Backlog Command

As PO, you own the Product Backlog. Items flow from user requirements into refined backlog items.

## Backlog Workflow

### View Backlog
```
/backlog view [options]
```

Options:
- `--sprint`: Show items for specific Sprint
- `--status`: Filter by status (backlog|ready|in-progress|done)
- `--priority`: Filter by priority (P1|P2|P3|P4)
- `--top`: Show top N items (default: 20)

### Add Item from Requirement
```
/backlog add [options]
```

Options:
- `--title` or `-t`: Item title (required)
- `--description` or `-d`: Detailed description
- `--from-req` or `-r`: Requirement ID this came from
- `--priority` or `-p`: P1|P2|P3|P4 (default: P3)
- `--points`: Story points (1|2|3|5|8|13|21)
- `--acceptance` or `-a`: Acceptance criteria

**Example:**
```
/backlog add --title "Social login feature" --from-req REQ-123 --priority P1 --points 8
```

### Refine Item
```
/backlog refine [item-id] [options]
```

Options:
- `--description`: Update description
- `--acceptance`: Set acceptance criteria
- `--points`: Set story points
- `--criteria`: Definition of Ready checklist

### Prioritize
```
/backlog prioritize [item-ids...]
```

Reorder items by priority.

### Assign to Sprint
```
/backlog sprint [item-ids...] --sprint sprint-123
```

Move items to Sprint.

### Update Item
```
/backlog update [item-id] [options]
```

Options:
- `--status`: Update status
- `--priority`: Update priority
- `--points`: Update points
- `--assignee`: Assign to team member

## Backlog States

```
backlog → ready → in-progress → done
          ↑
    (from requirements)
```

## Your Responsibilities

- **Order** the backlog by value, risk, dependencies
- **Refine** items so they're ready for Sprint
- **Communicate** priorities to the team
- **Accept** completed work

## Definition of Ready

Items are ready for Sprint when:
- Clear user value
- Acceptance criteria written
- Estimated by team
- Dependencies identified

## Data Storage

Backlog stored in `.claude/agile/backlog.json`.
