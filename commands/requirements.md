---
name: requirements
description: Requirements management - PO receives user requests, creates backlog items
---

# Requirements Management Command

When a user submits a request, you (as PO) receive it and decide what to do.

## Requirements Workflow

### Submit a Requirement
```
/requirements submit [options]
```

Options:
- `--title` or `-t`: Requirement title (required)
- `--description` or `-d`: Detailed description (required)
- `--from`: Requester name (required)
- `--priority`: P1|P2|P3|P4 (default: P3)
- `--value`: Expected business value (high|medium|low)

**Example:**
```
/requirements submit --title "Login with Google" --description "As a user, I want to login with Google so I don't need to remember another password" --from "Customer Team" --priority P1 --value high
```

### View Requirements
```
/requirements view [options]
```

Options:
- `--status`: pending|approved|in-progress|done|rejected
- `--from`: Filter by requester
- `--priority`: Filter by priority
- `--all`: Show all (default: show pending)

### Approve Requirement
```
/requirements approve [req-id]
```

Move approved requirement to Product Backlog.

### Reject Requirement
```
/requirements reject [req-id] --reason "Out of scope for Q1"
```

Reject with explanation.

### Add to Sprint
```
/requirements sprint [req-id] --sprint sprint-123
```

Assign approved requirement to a Sprint.

## Requirements vs Backlog

- **Requirements**: Raw user requests, needs assessment
- **Backlog**: Refined, estimated, ready-for-development items

## Decision Framework

When approving requirements:
1. Does it align with product vision?
2. Is it technically feasible?
3. What's the priority vs other work?
4. Do we have capacity?

## Data Storage

Requirements stored in `.claude/agile/requirements.json`.
