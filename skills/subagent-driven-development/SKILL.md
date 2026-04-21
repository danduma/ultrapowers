---
name: subagent-driven-development
description: Use when executing implementation plans with independent tasks in the current session
---

# Subagent-Driven Development

Execute a written plan by delegating focused tasks to fresh subagents, then reviewing the results before moving forward.

## Core Principle

Fresh subagent per task plus review between tasks keeps context clean and quality high.

## Default Posture

- Stay in the current repository unless the user asked for isolation.
- Do not require a worktree before starting.
- Do not block in-place work on `main` or `master` when the user explicitly chose that workflow.

## Process

1. Read the plan and extract the tasks.
2. Dispatch a focused implementer for the current task.
3. Review the returned work for spec compliance.
4. Review the returned work for code quality.
5. Fix issues before marking the task complete.
6. After all tasks pass verification, use `verification-before-completion`.
7. Only use `finishing-a-development-branch` when a branch/worktree workflow actually exists.

## Red Flags

- dispatching multiple implementers that edit the same files,
- skipping review loops,
- forcing worktree setup when the user asked to work in place,
- treating branch/worktree workflow as mandatory.
