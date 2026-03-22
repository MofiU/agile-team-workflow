---
name: agile-team:agile-best-practices
description: Agile engineering best practices - estimation, retrospectives, continuous improvement
---

# Agile Best Practices Reference

This skill provides practical guidance for implementing agile engineering practices effectively.

## Story Point Estimation

### Why Story Points?
- Relative estimation, not absolute time
- Accounts for complexity, uncertainty, effort
- Team-specific (your 3 ≠ my 3)
- Fibonacci sequence: 1, 2, 3, 5, 8, 13, 21

### Planning Poker
1. Product Owner reads item
2. Team discusses briefly
3. Everyone estimates simultaneously
4. Discuss outliers (high and low)
5. Repeat until consensus

### Velocity
- Story points completed per Sprint
- Use for capacity planning only
- Don't compare teams by velocity
- Account for iteration (average last 3 Sprints)

## Sprint Planning

### Before Planning
- Backlog refined (top 2 Sprints ready)
- Sprint Goal draft prepared by Product Owner
- Team capacity calculated (vacations, conflicts)

### During Planning
- Confirm Sprint Goal with Product Owner
- Select items in priority order
- Break items into tasks
- Commit only what team believes achievable

### Capacity Calculation
```
Available = Team Members × Days × Hours × (1 - Overhead)
Overhead = Meetings + Code Reviews + Admin
```

Example: 5 people × 10 days × 6 hours × 0.75 = 225 hours

## Daily Standup

### Effective Standups
- Same time, same place daily
- 15 minutes maximum
- Everyone speaks
- Focus on Sprint Goal

### Three Questions Template
1. What did I **yesterday**?
2. What will I **today**?
3. What **blockers** do I have?

### Handling Blockers
- If raised, Scrum Master notes it
- After standup, detail blockers
- SM works to remove or escalate
- Track blockers until resolved

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

## Definition of Done

### Example DoD Checklist
- [ ] Code written and reviewed
- [ ] Unit tests written (>80% coverage)
- [ ] Integration tests passing
- [ ] Accessibility tests passed
- [ ] Feature works on target browsers
- [ ] Documentation updated
- [ ] No known bugs

### When to Update DoD
- New testing requirements
- Compliance needs
- Customer feedback
- Process improvements

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
