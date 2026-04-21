# Ultrapowers Defaults

This file is the canonical summary of the fork's opinionated defaults.

## Workflow

- Work in the current repository by default.
- Do not create branches unless the user explicitly asks.
- Do not create worktrees unless the user explicitly asks or isolation is genuinely necessary.
- Keep ceremony proportional to the task.

## Planning

- Use user stories when they clarify intent, value, or acceptance criteria.
- Prefer concrete specs and plans over vague checklists.
- Keep workflow discipline, but do not invent process overhead the user did not ask for.
- Run a PM-style pass before completeness work for app and product surfaces.
- Derive usable-v1 completeness primarily from user stories and journeys.
- Use familiar product archetypes as a secondary backstop, not the primary source of truth.
- Expand familiar product archetypes toward a usable v1, not just a literal shell.
- Discover supporting jobs aggressively instead of assuming the prompt listed them all.
- Treat milestone slicing as delivery sequencing, not as permission to forget the full product vision.
- Confirm non-obvious, costly, or strongly opinionated additions with the user before locking them in.

## Frontend

- Default UI work to `shadcn/ui` unless the user says otherwise.
- Start app UI by choosing a ShadCN Block before inventing a layout from scratch.
- Treat desktop and mobile as first-class targets from the beginning.
- Build responsiveness into the first implementation pass.

## Architecture

- Do not default to file-based routing.
- Prefer explicit routing choices unless the framework or existing codebase makes another pattern necessary.
- Preserve existing project conventions when the human asks to work within an established system.
- Prefer strong instrumentation for backend and product behavior.
- When the project has backend workflows, prefer a fully instrumented control plane: every meaningful action, state transition, error, and result should be captured in durable logs or events, and exposed through a CLI or other scriptable interface so end-to-end behavior can be tested without a UI.
- Do not default to silent, hidden, or heavily abstracted failures.
- When the project has a frontend and backend boundary, prefer surfacing full error details and stack traces to the frontend so the real failure remains visible during development, debugging, and automated testing.
- Treat persistence of UI settings and preferences as an explicit product and architecture decision.
- For each meaningful setting, specify whether it persists, where it lives, who owns it, how it is serialized, when it is read and written, whether it is device-local or account-level, and how reset, migration, backup, and recovery are handled.
