---
name: dynamic-team
description: Dynamic team composition - configurable turns and quorum-based attendance
---

# Dynamic Team Composition

**⚠️ Some ceremonies require quorum - not necessarily everyone physically present.**

---

## Sprint Capacity: Configurable Conversation Turns

**Sprint capacity is measured in conversation turns, not story points.**

| Metric | Default | Adjustable | Reason |
|--------|---------|------------|--------|
| **Max turns per Sprint** | 35 | Yes (25-40) | Session limit is 50, more buffer for emergencies |
| **Planning** | ~3-4 turns | Yes | Sprint Planning |
| **Daily Scrums (10)** | 10 turns | Yes | 1 turn per day |
| **Refinement** | 2 turns | Yes | As needed |
| **Execution** | ~18-22 turns | Yes | Main work |
| **Review + Retro** | 2 turns | Fixed | Essential |

### Turn Budget (Default: 35 Turns)

```
Sprint Planning:     3 turns
Daily Scrums:       10 turns (10 days × 1 turn)
Backlog Refinement:  2 turns
Execution:          18 turns (development tasks)
Sprint Review:       1 turn  (demo)
Sprint Retro:        1 turn  (reflection)

TOTAL:              35 turns (configurable)
```

### Configurable Turns

**Teams can adjust turn budget based on experience.**

```
/team config --sprint-turns 30   # Struggling team, more buffer
/team config --sprint-turns 40   # High-performing team
```

**Recommendation**: Start at 35, adjust after 2 sprints based on completion rates.

### Team Decides Capacity

**Team self-organizes and decides what they can deliver in configured turns.**

```
PO: "Priority is A, B, C, D, E"

SM: "Team, we have 35 turns. What can we commit?"

Team: "A needs 15 turns, B needs 12, C needs 8. That's 35."

SM: "C or D?"

Team: "C. D is ambiguous anyway."

PO: "Ok, C takes priority. Let's break C into smaller pieces."

SM: "Committed: A, B, C. Sprint Goal locked."
```

### Turn Borrowing (Emergency)

**In genuine emergencies, team can borrow from next sprint.**

```
SM: "Critical bug found. Need 5 extra turns."

Team: "Consensus to borrow 5 from next sprint?"

Team: *consensus* "Yes."

SM: "Borrowing 5 turns. Notify PO. Log it."
```

---

## Quorum-Based Attendance

**Not everyone must be physically present. Quorum ensures decisions are valid.**

| Ceremony | Quorum Required |
|----------|-----------------|
| Sprint Planning | **2/3 of team + ALL developers + PO + SM** |
| Daily Scrum | Developers working that day (no quorum) |
| Sprint Review | **2/3 of team + stakeholders** |
| Retrospective | **2/3 of team (including PO)** |

### Quorum Rules

```
✅ Quorum met: Ceremony can proceed, decisions valid
❌ Quorum NOT met: Delay or async alternative required
⚠️ All developers must be present for Planning (no exceptions)
```

### Quorum Examples

```
Planning with 3 devs:
- All 3 devs + PO + SM = 5 people = Quorum ✅
- 2 devs + PO + SM = 4 people = Quorum ✅  
- 1 dev + PO + SM = 3 people = NOT Quorum ❌

Planning with 5 devs:
- 4 devs + PO + SM = 6 people = Quorum ✅
- 3 devs + PO + SM = 5 people = Quorum ✅
- 2 devs + PO + SM = 4 people = NOT Quorum ❌
```

### Async Alternatives (When Quorum Not Possible)

```
/retro async --format start-stop-continue  # Async retro
/planning delay 1 day                      # Wait for availability
/planning proxy @dev1 represents @dev2     # Designated representative
```

---

## Core Ceremonies Required

Not all members need to be in every meeting, BUT:
- Sprint Planning: **Quorum required** (all developers must attend)
- Daily Scrum: **Developers working that day** (no quorum needed)
- Sprint Review: **Quorum + stakeholders**
- Sprint Retrospective: **Quorum required** (including PO)

---

## Phase-Based Participation

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

## Ceremony Matrix

| Ceremony | Quorum | Must Attend | Optional | Notes |
|----------|--------|-------------|----------|-------|
| Sprint Planning | **2/3 + All Devs** | SM, PO, All Devs | Architect | All Devs required |
| Daily Standup | None | Devs working | SM | 15 min max |
| Backlog Refinement | None | SM, PO | Devs | |
| Sprint Review | **2/3 + Stakeholders** | SM, PO, Devs | Stakeholders | Developers demo |
| Retrospective | **2/3 (incl PO)** | SM, Team | - | SM facilitates |
| Blocker Sync | None | SM + Affected | Unaffected | |

---

## SM Orchestration

As SM, you decide:

1. **When to hold additional meetings** (syncs, ad-hoc)
2. **Who to pull in** for specific expertise
3. **How to timebox** ceremonies
4. **How to achieve quorum** when team is partially unavailable

**Quorum management**:
- If dev is unavailable → delay planning or get async input
- If PO is unavailable → can proceed with PO proxy
- If SM is unavailable → designate facilitator

**You CANNOT skip ceremonies, but you CAN**:
- Delay by 1 day if quorum not met
- Use async alternatives
- Get designated proxies

---

## Pull-In Pattern

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
- "SM decides who shows up" (quorum is the rule, not SM's choice)
- "Full attendance or nothing" (quorum allows flexibility)

---

## Benefits of Dynamic Team with Quorum

1. **Commitment**: Team commits because they participated in planning
2. **Transparency**: Everyone sees what everyone else is doing
3. **Trust**: Retrospective builds team trust
4. **Accountability**: Developers demo their own work
5. **Self-organization**: Team decides how to divide work
6. **Practicality**: Real life happens - quorum allows flexibility
7. **Validity**: Decisions are valid when quorum is met
