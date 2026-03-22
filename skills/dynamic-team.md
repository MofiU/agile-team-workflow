---
name: dynamic-team
description: Dynamic team composition - who participates in which ceremony based on phase
---

# Dynamic Team Composition

Not all team members participate in every ceremony. SM orchestrates who attends based on the current phase and needs.

## Phase-Based Participation

### Discovery Phase
**When**: Requirements gathering, design work

**Includes**: SM, PO, UI/UX, Architect
**Excludes**: Developers, QA (until design ready)

### Planning Phase
**When**: Sprint planning, backlog refinement

**Includes**: SM, PO, relevant Developers, Architect
**Excludes**: Team members not working next Sprint

### Development Phase
**When**: Active coding, implementation

**Includes**: SM, assigned Developers, DevOps (when needed)
**Excludes**: UI/UX (unless flagged by developer)
**Note**: UI/UX only pulled in when developer raises UI issue

### Testing Phase
**When**: QA testing, bug fixes

**Includes**: SM, QA, Developers (for bug fixes)
**Excludes**: UI/UX (unless design issues found)

### Deployment Phase
**When**: Release, deployment

**Includes**: SM, DevOps, Developer who built it
**Excludes**: Most of team

### Review Phase
**When**: Sprint review, retrospective

**Includes**: 
- Sprint Review: SM, PO, invited Stakeholders
- Retrospective: Full team

## Ceremony Matrix

| Ceremony | Required | Optional | Excluded |
|----------|----------|----------|----------|
| Sprint Planning | SM, PO | Architect, Lead Dev | QA, UI/UX |
| Daily Standup | Devs in Sprint | SM | Not in Sprint |
| Backlog Refinement | SM, PO | Devs, Architect | QA |
| Sprint Review | SM, PO | Stakeholders | - |
| Retrospective | SM, Team | PO | Stakeholders |
| Blocker Sync | SM | Affected members | Unaffected |

## SM Orchestration

As SM, you decide:

1. **Who to invite** to each ceremony
2. **When to pull in** additional expertise
3. **When to excuse** people from ceremonies
4. **How to structure** meetings for phase

## Pull-In Pattern

### Developer Raises UI Issue
```
Developer: "UI doesn't match spec"
SM: Pull in UI/UX for clarification
```

### Technical Blocker
```
Developer: "Database migration blocked"
SM: Pull in Architect or DBA
```

### QA Finds Bug
```
QA: "Critical bug in auth flow"
SM: Pull in relevant Developer
```

## Communication

### Notify Appropriate People
```
/team notify "Sprint planning in 30 min" --to planning
/team notify "Daily standup starting" --to daily
/team notify "Design review needed" --to UI/UX
```

## Dynamic Team Benefits

1. **Efficiency**: People only attend relevant meetings
2. **Focus**: Phase-appropriate expertise
3. **Cost**: Reduced meeting time
4. **Engagement**: People care about meetings they attend
