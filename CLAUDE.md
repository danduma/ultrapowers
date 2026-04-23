# Ultrapowers Fork Guidelines

## Purpose

This repository is a local fork of `obra/superpowers` that we are reshaping into `ultrapowers`. Treat it as our own evolving skill system, not as an upstream contribution effort.

## Working Rules For Agents

- Read the local skill files before changing them.
- Preserve the fork's opinionated defaults unless the human explicitly asks for an exception.
- YOU WILL NEVER CREATE A BRANCH unless explicitly instructed.
- Ask the user whether we should work in worktrees as part of the planning.
- YOU WILL ONLY CREATE A WORKTREE if explicitly instructed.
- Prefer direct edits inside the current repository.
- Keep changes coherent across docs, skills, and references.
- When changing behavior-shaping content, update the nearest supporting docs so the defaults stay discoverable.

## Ultrapowers Defaults

- Work in the current repository by default.
- Ask the user whether we should work in worktrees as part of the planning.
- Use user stories in specs and plans when they help define behavior or outcomes.
- Default UI work to `shadcn/ui`.
- Start app UIs from a ShadCN Block when possible.
- Design for desktop and mobile from the beginning.
- Avoid file-based routing by default.
- Prefer strong backend instrumentation by default.
- Prefer a fully instrumented control plane for backend and product work: persist meaningful events, actions, errors, and state transitions, and expose them through a CLI or other scriptable interface so the system can be tested end-to-end without relying on the UI.
- Do not allow silent or heavily abstracted errors by default.
- Prefer end-to-end error transparency: the frontend should receive the full error details and stack trace so failures stay inspectable, testable, and impossible to hand-wave away.
- Treat persistence of UI settings as an explicit design concern, not an implementation afterthought.
- For every meaningful UI setting, make it explicit whether it persists, where it is stored, how it is encoded, how it is loaded and updated, how it syncs across sessions/devices/users if relevant, and how it is reset, migrated, and tested.

## Change Quality

- A good change updates both the behavior-shaping skill text and the surrounding docs/reference material.
- Avoid half-migrations where the README says one thing and a skill says another.
- Prefer small, readable skill edits over sprawling rewrites unless a full rewrite is clearly cleaner.

## Contributing

This fork may later be reused elsewhere, so favor general-purpose defaults over repository-specific instructions. If a behavior only makes sense for one project, document it as an override example instead of making it the default.
