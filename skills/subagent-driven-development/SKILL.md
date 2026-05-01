---
name: subagent-driven-development
description: Use when executing implementation plans with independent tasks in the current session
---

# Subagent-Driven Development

Execute a written plan by delegating focused tasks to fresh subagents, then reviewing the results before moving forward.

## Core Principle

Fresh subagent per task plus review between tasks keeps context clean and quality high.

Every subagent task must deliver real functionality for its slice. NO FAKE COMPONENTS, NO MOCKS, NO PLACEHOLDERS, NO FALLBACKS as substitutes for required behavior unless the human explicitly approved prototype/scaffold work.

## Default Posture

- Stay in the current repository unless the user asked for isolation.
- Do not block in-place work on `main` or `master` when the user explicitly chose that workflow.

## Process

1. Read the plan and extract the tasks.
2. Dispatch a focused implementer for the current task, including the full-functionality standard in the prompt.
3. Review the returned work for spec compliance.
4. Review the returned work for code quality.
5. Fix issues before marking the task complete.
6. After all tasks pass verification, use `verification-before-completion`.
7. After all tasks pass verification, finish the work in place unless the user explicitly asked for a different repository workflow.

## Red Flags

- dispatching multiple implementers that edit the same files,
- skipping review loops,
- forcing extra repository isolation when the user asked to work in place,
- accepting mocked, placeholder, canned, or fallback-only behavior as task completion,
- continuing to add code to a file after it passes 1200 lines without refactoring or splitting responsibilities.
