---
name: handoff
description: Handoff - SM delivers to PO, PO validates, commands next iteration
---

# Handoff Command

The critical handoff between SM and PO after each iteration.

## Handoff Workflow

### SM Requests Handoff
```
/handoff request [options]
```

Options:
- `--sprint`: Sprint ID (required)
- `--deliverables`: What was delivered
- `--status`: completed|partial|cancelled
- `--notes`: Additional notes

**Example:**
```
/handoff request --sprint sprint-123 --deliverables "User auth module, API endpoints" --status completed
```

### PO Reviews Delivery
```
/handoff review [handoff-id] [options]
```

Options:
- `--decision`: accepted|rejected|conditional
- `--feedback`: Review feedback
- `--conditions`: Conditions for acceptance (if conditional)

**Example:**
```
/handoff review HANDOFF-123 --decision accepted --feedback "Great work! Auth is solid."
```

### PO Commands Next Iteration
```
/handoff next [options]
```

Options:
- `--sprint`: Next sprint number (auto-generated)
- `--focus`: Focus areas for next sprint
- `--changes`: Changes to team composition
- `--continue`: SM continues with next sprint

**Example:**
```
/handoff next --focus "Payment integration, Bug fixes" --continue true
```

## Handoff States

```
pending → reviewed → accepted/rejected
                      ↓
              [conditional] → conditions met → accepted
```

## Handoff Report Contents

When SM requests handoff:
- Sprint goal achievement
- Deliverables completed
- Blockers encountered
- Team performance metrics
- Remaining items
- Recommended next steps

## PO Review Checklist

- [ ] Deliverables match Sprint Goal?
- [ ] Quality acceptable?
- [ ] Acceptance criteria met?
- [ ] No critical blockers?
- [ ] Stakeholder value delivered?

## After Acceptance

Once PO accepts:
1. PO communicates to stakeholders
2. PO adjusts Product Backlog if needed
3. PO commands SM for next iteration
4. SM plans next Sprint

## Data Storage

Handoff data stored in `.claude/agile/handoffs.json`.
