---
name: executing-plans
description: Use when you have a written implementation plan to execute inline with review checkpoints
---

# Executing Plans

Implement a written plan carefully, review it first, then execute it step by step.

**Announce at start:** "I'm using the executing-plans skill to implement this plan."

## Default Posture

- Execute in the current repository unless the user asked for isolation.
- Stop and ask for clarification when the plan or repository state creates real ambiguity.
- Implement the real deliverable, not a demo-shaped substitute. NO FAKE COMPONENTS, NO MOCKS, NO PLACEHOLDERS, NO FALLBACKS as completion substitutes unless the human explicitly approved them.

## Process

1. Load the plan.
2. Review it critically for gaps or contradictions.
3. Reject or pause on any task that treats fake components, mocks, placeholders, canned data, or fallback paths as proof of completion.
4. Execute tasks in order.
5. Run the specified verifications against real functionality.
6. Use `verification-before-completion` before claiming success.
7. Finish the work in place unless the user explicitly asked for a different repository workflow.

## When To Stop

Pause and ask for help if:

- the plan is missing critical detail,
- tests fail in a way the plan does not account for,
- the repository state conflicts with the plan,
- the plan can only be completed by substituting fake functionality for required behavior,
- a task requires a design decision that was never approved.

Do not guess your way through blockers.
