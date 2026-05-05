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
- Keep process proportional. Tiny mechanical edits such as color tweaks, typos, label changes, and prompt wording changes should be made directly with targeted verification.
- Deliver real final functionality by default. NO FAKE COMPONENTS, NO MOCKS, NO PLACEHOLDERS, NO FALLBACKS as substitutes for requested behavior unless the human explicitly asks for a prototype or scaffold.
- For app, UI, and product-surface work, run a PM pass during planning. Treat it as a required part of design, not an optional flourish.
- For app, UI, and product-surface work, consider agentic user journey tests during planning, but do not run them without explicit user approval because they can be token-expensive.
- Refactor oversized files. When a file passes 1200 lines, treat that as a prompt to split responsibilities instead of continuing to pile work into it.
- Keep changes coherent across docs, skills, and references.
- When changing behavior-shaping content, update the nearest supporting docs so the defaults stay discoverable.
- Every project should have a `.gitignore`.
- Never commit or push secrets, credentials, local environment files, `node_modules`, dependency caches, build outputs, coverage output, logs, temporary files, or intermediate/generated artifacts unless the human explicitly asks to version a specific generated artifact.

## Ultrapowers Defaults

- Work in the current repository by default.
- Ask the user whether we should work in worktrees as part of the planning.
- Keep tiny mechanical edits tiny; do not expand them into brainstorming, planning, or full TDD.
- Treat plans as commitments to full, complete, final product functionality for the approved milestone, not mock-driven demos.
- Use user stories in specs and plans when they help define behavior or outcomes.
- Run a PM pass for app, UI, and product-surface work so supporting jobs, state model, operational reality, and north-star thinking become explicit early.
- Plan agentic user journey tests for important user stories when useful, but gate execution on explicit user approval.
- Refactor code when a file passes 1200 lines instead of treating file growth as harmless.
- Default UI work to `shadcn/ui`.
- Start app UIs from a ShadCN Block when possible.
- Design for desktop and mobile from the beginning.
- For React apps, use the `building-react-apps` skill, centralize shared state in global single-source-of-truth Manager classes, and default to `pnpm` instead of `npm`.
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
