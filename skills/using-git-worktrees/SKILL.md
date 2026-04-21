---
name: using-git-worktrees
description: Use when the user explicitly wants an isolated workspace or the task genuinely needs one
---

# Using Git Worktrees

Git worktrees are an optional isolation tool, not the default workflow.

**Announce at start:** "I'm using the using-git-worktrees skill to set up an isolated workspace."

## Rule

Never create a worktree unless:

- the user explicitly asked for one, or
- isolation is clearly necessary and the user agrees.

If direct work in the current repository is acceptable, prefer that.

## When Worktrees Are Appropriate

- risky refactors needing isolation,
- parallel independent efforts,
- keeping one checkout stable while another changes,
- user preference.

## Safety

- choose a sensible worktree location,
- verify project-local worktree directories are gitignored,
- create the worktree on the requested branch if the user asked for branch isolation,
- run project setup and a clean baseline check if the task depends on that.

## Red Flags

- creating a worktree automatically,
- using a worktree to satisfy process habit rather than a real need,
- assuming branch creation is allowed when the user said not to create branches.
