---
name: board
description: Kanban board - manage team tasks, track progress, personal task lists
---

# Kanban Board Command

Manage team tasks on a Kanban board. Each team member has their own task list.

## Board Overview

### View Board
```
/board view [options]
```

Options:
- `--sprint`: Show tasks for specific Sprint (default: current sprint)
- `--member`: Show tasks for specific team member
- `--filter`: Filter by status (todo|in-progress|review|done)

Shows the full Kanban board:
- **TODO**: Tasks ready to start
- **IN-PROGRESS**: Tasks being worked on
- **REVIEW**: Tasks awaiting review
- **DONE**: Completed tasks

### My Tasks
```
/board mine [options]
```

Shows your personal task list.

Options:
- `--status`: Filter by status
- `--sprint`: Show tasks for sprint (default: current)

## Task Management

### Create Task
```
/board task [options]
```

Options:
- `--title` or `-t`: Task title (required)
- `--description` or `-d`: Task description
- `--assignee` or `-a`: Assign to team member (default: you)
- `--story-id` or `-s`: Parent story/backlog item
- `--estimate`: Estimated hours
- `--priority`: P1|P2|P3|P4

**Example:**
```
/board task --title "Implement login form UI" --story-id AUTH-42 --assignee "Alice" --estimate 4 --priority P2
```

### Move Task
```
/board move [task-id] [status]
```

Move task to a new status.

Statuses: `todo` | `in-progress` | `review` | `done`

**Example:**
```
/board move TASK-123 in-progress
```

### Assign Task
```
/board assign [task-id] --to [member]
```

Reassign task to another team member.

### Update Task
```
/board update [task-id] [options]
```

Options:
- `--title`: Update title
- `--description`: Update description
- `--estimate`: Update estimate
- `--priority`: Update priority

### Comment Task
```
/board comment [task-id] --text "Started working on this"
```

Add comment to a task.

## Personal Task List

### My Todo
```
/board todo
```

Shows your TODO items.

### My In Progress
```
/board doing
```

Shows your in-progress items.

### My Done Today
```
/board done --today
```

Shows your completed items today.

## Sprint Board

### Sprint Board
```
/board sprint [sprint-id]
```

Shows board filtered to a specific Sprint.

### Sprint Progress
```
/board progress [sprint-id]
```

Shows:
- Total tasks
- Completed percentage
- Tasks by status
- Team member workload

## Board Features

### Task Dependencies
```
/board depends [task-id] --on [other-task-id]
```

Link dependent tasks.

### Blocked Tasks
```
/board blocked
```

Shows tasks blocked by impediments.

### Overdue Tasks
```
/board overdue
```

Shows tasks past their estimate.

## Data Storage

Board data stored in `.claude/agile/board.json`.
