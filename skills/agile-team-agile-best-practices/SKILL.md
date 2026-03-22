---
name: agile-team:agile-best-practices
description: Agile engineering best practices - estimation, retrospectives, continuous improvement
---

# Agile Best Practices Reference

This skill provides practical guidance for implementing agile engineering practices effectively.

## Turn-Based Estimation (AI Teams)

### Why Turns?
- AI work happens in conversation turns (50-turn session limit)
- Each turn has measurable output
- Team self-assesses what they can commit in turns
- PO cannot override team capacity estimate

### Estimation Process
1. PO presents prioritized backlog items
2. Team discusses complexity in turns
3. Each developer estimates turns for their part
4. Team agrees on total turns for Sprint
5. PO confirms priority order

### Turn Allocation Example (35-turn Sprint)
```
Planning:        3 turns
Execution:      28 turns
Review:          2 turns
Retro:           2 turns
TOTAL:           35 turns (configurable)
```

### Key Principle
**Team commits to turns, not PO allocates turns.**

## Sprint Planning (AI Teams)

### Before Planning
- Backlog refined (top 2 Sprints ready)
- Sprint Goal draft prepared by Product Owner
- Team capacity calculated (turns-based)

### AI-Specific Considerations
- Team decides how many turns they can commit
- PO presents priorities, team estimates turns
- No "top-down" turn allocation
- Buffer turns for unexpected work

### Capacity Discussion
- Each developer estimates their turns honestly
- Team aggregates and confirms total capacity
- SM facilitates, does not dictate

## Daily Coordination (AI Teams)

### Event-Driven Alternative
- SM monitors blockers actively
- Team updates status when work completes
- No fixed 5-minute health checks
- SM intervenes when impediments arise

### When to Meet
- Only when coordination needed
- Async updates preferred
- 15-min standup only if valuable

## Backlog Refinement

### Definition of Ready
Items are ready for Sprint when:
- Clear user value defined
- Acceptance criteria documented
- Estimated by team
- Dependencies identified
- Small enough to complete in Sprint (ideally < 50% of Sprint)

### Refinement Guidelines
- 10% of Sprint time for refinement
- Keep 2-3 Sprints refined
- Don't over-refine distant items

## Retrospectives

### Formats

**Start-Stop-Continue**
- Start: What should we begin doing?
- Stop: What should we stop doing?
- Continue: What should we keep doing?

**4Ls**
- Loved: What did we enjoy?
- Learned: What knowledge did we gain?
- Lacked: What was missing?
- Longed For: What did we wish we had?

**Sailboat**
- Wind: What propelled us forward?
- Anchor: What held us back?
- Rock: What risks did we face?
- Island: What are our goals?

### Action Items
- Specific and measurable
- Assigned to one person
- Follow up in next retro
- Limited number (3-5 max)

## Definition of Done (AI Teams)

### Automated Gates (100% Mandatory)
- ESLint/Prettier: 0 errors
- TypeScript: strict mode, 0 errors
- Unit Tests: core business logic covered
- SAST Scan: 0 vulnerabilities
- CVE Check: 0 known vulnerabilities

### Manual Gates
- Critical path code: peer review approval
- Regular code: automated gates sufficient

### NOT in DoD
- Coverage percentage as a number game
- Testing setter/getter methods
- Testing configuration files

## Code Review Policy (AI Teams)

### Review Requirement Matrix

| Code Type | Review Required | Rationale |
|-----------|----------------|-----------|
| **Critical Path** (security, payment, auth) | 100% peer review | AI may produce flawed high-stakes code |
| **Regular Features** | Automated gates + optional async | Core logic covered by tests |
| **Bug Fixes** | Automated gates + optional | Tests prove fix |
| **Documentation/Config** | None | No execution risk |

### Critical Path Definition
- Authentication and authorization logic
- Payment and financial calculations
- Data privacy and compliance code
- Infrastructure and security configurations

### Who Reviews?
- Developers review each other's code
- Critical path requires 2+ reviewers
- Reviewer must be a different person than author

### Review Process
1. Submit PR with description
2. Automated gates must pass (ESLint, tests, SAST, CVE)
3. If critical path → await peer review approval
4. If regular → merge when automated gates pass

### Code Review vs Agent Role
Code review is a **flow/process rule**, not an agent-specific behavior.
Agents follow these rules as part of the sprint process, regardless of their specific role.

## Continuous Improvement

### Retrospective Follow-up
- Review previous action items
- Ask: Did actions help?
- Share improvements with team
- Celebrate wins

### Sprint Review → Sprint Retrospective Flow
1. Sprint Review: Demo work, gather feedback
2. Retrospective: Reflect on process
3. Planning: Apply learnings to next Sprint

## Anti-Patterns

### Planning Anti-Patterns
- Commitment based on "what management wants"
- Not breaking down large items
- Ignoring team capacity
- Skipping technical complexity discussion

### Standup Anti-Patterns
- Status reporting to manager
- Problem-solving during standup
- Skipping days or being late
- Only talking about completed tasks

### Retrospective Anti-Patterns
- No follow-up on action items
- Blaming individuals
- Same issues raised repeatedly
- Action items without owners

## Team Dynamics

### Forming → Norming → Storming → Performing
- **Forming**: Getting to know each other
- **Storming**: Disagreements and conflicts
- **Norming**: Establishing patterns
- **Performing**: High collaboration

### Self-Organization Tips
- Trust team to make decisions
- Let team choose working methods
- Provide context, not commands
- Remove impediments, don't micro-manage

## Metrics That Matter

### Leading Indicators (Predict Future)
- Sprint Planning commitment met
- Daily standup blockers resolved quickly
- Backlog refinement ratio
- Team happiness

### Lagging Indicators (Measure Past)
- Velocity (use carefully)
- Defect rate
- Sprint Goal achievement
- Customer satisfaction

## Scaling Considerations

### For Multiple Teams
- Coordinate Sprint Planning/Review
- Share architectural decisions
- Synchronize Daily Scrums if needed
- Maintain single Product Backlog

### Common Scaling Mistakes
- Too many teams on one product
- No cross-team coordination
- Competing priorities
- Siloed thinking
