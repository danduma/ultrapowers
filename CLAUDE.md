# Ultrapowers Fork Guidelines

## Purpose

This repository is a local fork of `obra/superpowers` that we are reshaping into `ultrapowers`. Treat it as our own evolving skill system, not as an upstream contribution branch.

## Working Rules For Agents

- Read the local skill files before changing them.
- Preserve the fork's opinionated defaults unless the human explicitly asks for an exception.
- Do not create branches or worktrees unless the human explicitly asks for them.
- Prefer direct edits inside the current repository.
- Keep changes coherent across docs, skills, and references.
- When changing behavior-shaping content, update the nearest supporting docs so the defaults stay discoverable.

## Ultrapowers Defaults

- Work in the current repository by default.
- Use user stories in specs and plans when they help define behavior or outcomes.
- Default UI work to `shadcn/ui`.
- Start app UIs from a ShadCN Block when possible.
- Design for desktop and mobile from the beginning.
- Avoid file-based routing by default.

## Change Quality

- A good change updates both the behavior-shaping skill text and the surrounding docs/reference material.
- Avoid half-migrations where the README says one thing and a skill says another.
- Prefer small, readable skill edits over sprawling rewrites unless a full rewrite is clearly cleaner.

## Contributing

This fork may later be reused elsewhere, so favor general-purpose defaults over repository-specific instructions. If a behavior only makes sense for one project, document it as an override example instead of making it the default.
