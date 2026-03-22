---
name: handoff-workflow
description: Sprint Review and handoff workflow - collaboration, not approval
---

# Sprint Review & Handoff Workflow

**⚠️ IMPORTANT: Sprint Review is NOT a delivery handoff. It is a collaborative inspection of Increment.**

Standard Scrum treats Sprint Review as:
- Team demonstrates what they built
- PO and stakeholders inspect and adapt
- Collaboration, not approval

**Your current design treats it as: SM delivers → PO approves → PO commands next Sprint**

This is waterfall disguised as Scrum.

---

## What Sprint Review Actually Is

### Wrong (Your Current Model)
```
SM: "We completed the sprint. Please approve."
PO: "I approve. Continue to next sprint."
```

### Correct (Scrum 2025)
```
Team: "We built X, Y, Z. Here's the demo."
PO: "Great. I have feedback on Y..."
Stakeholders: "What about integration with system Z?"
Team: "We'll address that in next Sprint planning."
SM: "Let's capture this for the backlog."
```

---

## Correct Sprint Review Flow

### 1. Team Presents Increment
- Show working software
- Discuss what was done
- Be transparent about what wasn't done

### 2. Collaborate on Feedback
- PO and stakeholders ask questions
- Discuss what next steps should be
- Identify new items for backlog

### 3. PO Makes Item Decisions
- **Accept**: Item meets Definition of Done → moves to Done
- **Reject**: Item doesn't meet criteria → returns to backlog
- **Partial**: Item needs rework → backlog with priority

### 4. Update Backlog Together
- Add new insights from review
- Adjust priorities based on feedback
- Plan doesn't start until planning meeting

---

## What SM Does NOT Do

| ❌ Your SM Does | ✅ Correct SM |
|-----------------|---------------|
| "Delivers to PO" | Facilitates team demo |
| "Requests PO approval" | Supports collaboration |
| "Commands next sprint" | Team decides capacity |
| Acts as intermediary | Removes self from middle |

---

## What PO Does NOT Do

| ❌ Your PO Does | ✅ Correct PO |
|-----------------|---------------|
| "Approves sprint completion" | Inspects increment |
| "Commands next sprint" | Collaborates on priorities |
| Reviews only with SM | Engages with full team |
| Gatekeeper role | Product expert |

---

## Sprint Review Facilitator Role

SM facilitates, but **team presents**:

```
SM: "Sprint Review for Sprint 12. Team, please demonstrate."

Team Member 1: Shows feature A
Team Member 2: Shows feature B

PO: "Feature B - can we see error handling?"
Developer: *demonstrates*

SM: "Recording that. PO, any blockers for acceptance?"
PO: "No, B meets criteria. A needs one fix."
SM: "A developer - please update status to 'needs rework'."
```

---

## Definition of Done vs Acceptance Criteria

### DoD (Team's Commitment)
- Code reviewed
- Tests passing
- Deployed to environment
- Meets team's quality standards

### Acceptance Criteria (PO's Requirement)
- Business value delivered
- User need satisfied
- Stakeholder expectations met

**Critical**: DoD is binary (done/not done). Acceptance criteria may require negotiation.

---

## Next Sprint Planning - Independent Start

Sprint Review ends → Next Sprint Planning is a **fresh start**:

```
Sprint 12 Review Complete
        ↓
SM: "Great collaboration. Rest day tomorrow."
        ↓
Sprint 13 Planning (NEW meeting)
        ↓
PO: "Based on feedback, priority is now X, Y, Z"
Team: "We can commit to X and Y based on capacity"
SM: "Locked. Let's break into tasks."
```

**PO does NOT "approve" or "command" next sprint.** Team commits based on their capacity and PO's priorities.

---

## Blocker Resolution Flow

If PO rejects an item at Sprint Review:

```
PO: "Item AUTH-3 doesn't meet acceptance criteria."

SM: "What's missing?"

PO: "The error messages aren't user-friendly."

Team Dev: "That's a quick fix. 1 hour."

SM: "Can we get that done today?"

Team: "Yes."

SM: "Update AUTH-3 to 'in progress', target today."

        ↓
Later that day:
        
Team: "AUTH-3 fixed."
SM: "PO, please verify."
PO: "Approved. Moving to Done."
```

**Not**: "PO sends it back to backlog and waits for next sprint."

---

## Why This Matters

Your "handoff" model creates:
- SM as middleman
- PO as bottleneck
- Team as executor
- Accountability gap

Correct model creates:
- Team accountability
- PO as product expert (not approver)
- SM as facilitator (not manager)
- Continuous improvement

---

## Corrected Handoff Definition

There IS a valid "handoff" concept:

**To another team/system**:
```
Sprint Review: "Auth module is done."

Ops: "Great. We'll deploy next Tuesday."

Team: "Here's the runbook."
```

This is **coordination**, not **approval**.
