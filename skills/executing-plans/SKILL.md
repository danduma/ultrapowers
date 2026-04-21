---
name: executing-plans
description: Use when you have a written implementation plan to execute inline with review checkpoints
---

# Executing Plans

Implement a written plan carefully, review it first, then execute it step by step.

**Announce at start:** "I'm using the executing-plans skill to implement this plan."

## Default Posture

- Execute in the current repository unless the user asked for isolation.
- Do not assume a worktree or branch exists.
- Stop and ask for clarification when the plan or repository state creates real ambiguity.

## Process

1. Load the plan.
2. Review it critically for gaps or contradictions.
3. Execute tasks in order.
4. Run the specified verifications.
5. Use `verification-before-completion` before claiming success.
6. Only use `finishing-a-development-branch` if branch-based wrap-up is actually relevant.

## When To Stop

Pause and ask for help if:

- the plan is missing critical detail,
- tests fail in a way the plan does not account for,
- the repository state conflicts with the plan,
- a task requires a design decision that was never approved.

Do not guess your way through blockers.
