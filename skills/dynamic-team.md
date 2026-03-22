---
name: dynamic-team
description: Dynamic team composition - Sprint capacity based on conversation turns
---

# Dynamic Team Composition

**⚠️ CRITICAL: Some ceremonies are non-negotiable - the entire Scrum Team must participate.**

---

## Sprint Capacity: 40 Conversation Turns

**Sprint capacity is measured in conversation turns, not story points.**

| Metric | Value | Reason |
|--------|-------|--------|
| **Max turns per Sprint** | 40 | Session limit is 50, 10 reserved for Sprint Review/Retro |
| **Planning estimate** | ~4-6 turns | Sprint Planning + Daily Scrums |
| **Execution budget** | ~30-34 turns | Actual development work |
| **Buffer** | ~2-4 turns | Unexpected issues, refinements |

### Turn Budget Breakdown

```
Sprint Planning:     2 turns (goal setting, commitment)
Daily Scrums:        10 turns (10 days × 1 turn)
Backlog Refinement:  2 turns
Execution:           24 turns (development tasks)
Sprint Review:       1 turn  (demo)
Sprint Retro:        1 turn  (reflection)

TOTAL:               40 turns
```

### Team Decides Capacity

**Team self-organizes and decides what they can deliver in 40 turns.**

```
PO: "Priority is A, B, C, D, E"

SM: "Team, we have 40 turns. What can we commit?"

Team: "A needs 15 turns, B needs 12, C needs 8. That's 35."

SM: "C or D?"

Team: "C. D is ambiguous anyway."

PO: "Ok, C takes priority. Let's break C into smaller pieces."

SM: "Committed: A, B, C. Sprint Goal locked."
```

---

## Core Ceremonies Required

Not all members need to be in every meeting, BUT:
- Sprint Planning: **Full team required**
- Daily Scrum: **Only people working that day**
- Sprint Review: **Full team + stakeholders**
- Sprint Retrospective: **Full team required** (SM facilitates)

---

## Phase-Based Participation (Corrected)

### Discovery Phase
**When**: Requirements gathering, design work

**Includes**: SM, PO, UI/UX, Architect
**Excludes**: Developers, QA (until design ready)
**Note**: This is PRE-Sprint work, not Sprint ceremonies

### Planning Phase
**When**: Sprint planning

**Required**: 
- SM (facilitates)
- PO (provides priorities)
- **All Developers** (they make the commitment!)
- Architect (technical guidance)

**Excluded**: 
- QA (unless needed for test feasibility)
- UI/UX (unless critical design decisions needed)

**Why all developers**: Team self-organization requires everyone to hear the discussion and commit together.

### Development Phase
**When**: Active coding, implementation

**Includes**: 
- SM (coordinate)
- Assigned Developers
- DevOps (when needed for deployment)
- Pull in UI/UX **only when developer raises issue**

**Note**: This is between Daily Scrums - no formal ceremony

### Testing Phase
**When**: QA testing, bug fixes

**Includes**: 
- Developers (for bug fixes)
- QA (owns testing)

**Excludes**: UI/UX (unless design-related bug)

### Deployment Phase
**When**: Release, deployment

**Includes**: 
- DevOps (leads)
- Developer who built it
- SM (coordinate)

### Sprint Review
**Required**: 
- **Full Scrum Team** (SM, PO, All Developers)
- **Stakeholders** (invited by PO)

**Why full team**: 
- Developers demonstrate their own work
- Team sees the complete picture
- Collective accountability

**SM role**: Facilitator, not presenter

### Sprint Retrospective
**Required**: 
- **Full Scrum Team** (SM, PO, All Developers)

**PO participation**: Required - PO is part of the team

**SM role**: Facilitator, may also participate as team member

**Why full team**: Trust and transparency require everyone

---

## Ceremony Matrix (Corrected)

| Ceremony | Required | Optional | Excluded | Notes |
|----------|----------|----------|----------|-------|
| Sprint Planning | **SM, PO, All Devs** | Architect | QA, UI/UX | All Devs must commit |
| Daily Standup | Devs working today | SM | Not working today | 15 min max |
| Backlog Refinement | SM, PO | Devs (relevant) | - | |
| Sprint Review | **Full Team + Stakeholders** | - | - | Developers demo |
| Retrospective | **Full Team (incl PO)** | - | - | SM facilitates |
| Blocker Sync | SM + Affected | - | Unaffected | |

---

## SM Orchestration (Corrected)

As SM, you decide:

1. **When to hold additional meetings** (syncs, ad-hoc)
2. **Who to pull in** for specific expertise
3. **How to timebox** ceremonies
4. **When to excuse** people from non-core ceremonies

**You CANNOT excuse people from**:
- Sprint Planning (all devs needed for commitment)
- Sprint Review (all devs needed for demo)
- Retrospective (all team needed for trust)

---

## Pull-In Pattern (Corrected)

### Developer Raises UI Issue
```
Developer: "UI doesn't match spec"
SM: *arranges time with UI/UX* → Developer and UI/UX sync
SM: Not in standup, scheduled separately
```

### Technical Blocker
```
Developer: "Database migration blocked"
SM: Pull in Architect or DBA for specific consultation
SM: Document resolution in blocker log
```

### QA Finds Bug
```
QA: "Critical bug in auth flow"
SM: Notify relevant Developer → sync scheduled
SM: No need for full team unless major
```

---

## Communication

### Notify Team Members
```
/team ceremony planning --sprint sprint-123
/team ceremony review --sprint sprint-123  
/team ceremony retro --sprint sprint-123
```

### Dynamic Team DOES NOT Mean

- "I only work on my stuff"
- "I skip ceremonies I don't like"
- "SM decides who shows up to core ceremonies"

---

## Benefits of Correct Dynamic Team

1. **Commitment**: Team commits because they participated in planning
2. **Transparency**: Everyone sees what everyone else is doing
3. **Trust**: Retrospective builds team trust
4. **Accountability**: Developers demo their own work
5. **Self-organization**: Team decides how to divide work
