# Ultrapowers

Ultrapowers is an opinionated software development methodology for coding agents. It starts from `obra/superpowers`, then rewrites the defaults to better fit practical product work: lighter local workflows, clearer user intent, stronger frontend defaults, and less ceremony unless the user actually wants it.

## Core Defaults

- Work in the current repository by default.
- Never create a branch or worktree unless the user explicitly asks or isolation is genuinely necessary.
- Use user stories in specs and plans when they clarify behavior.
- Default UI work to `shadcn/ui`.
- Start app UI from a ShadCN Block before inventing a layout from scratch.
- Treat desktop and mobile responsiveness as first-class from the beginning.
- Do not default to file-based routing.
- Expand familiar product archetypes toward a usable v1 instead of stopping at literal requested controls.
- Infer expected product surfaces from what users need to do, revisit, recover from, and understand.
- Think ambitiously about the full product, then deliver it in coherent milestones without forgetting the bigger vision.

## Basic Workflow

1. **brainstorming** - clarify the goal, shape the design, and write a spec.
2. **writing-plans** - turn the approved spec into an implementation plan.
3. **subagent-driven-development** or **executing-plans** - implement the plan.
4. **test-driven-development** - enforce red/green development during implementation.
5. **requesting-code-review** - review changes before calling the work done.
6. **verification-before-completion** - verify outcomes before claiming success.
7. **finishing-a-development-branch** - only when branch-based work actually needs to be wrapped up.

## Philosophy

- **Skills first** - check for the right workflow before acting.
- **User intent over ritual** - follow the user's instructions even when they override defaults.
- **Lightweight by default** - avoid branches, worktrees, and extra ceremony unless they solve a real problem.
- **Product-minded planning** - use user stories and acceptance thinking where it helps.
- **PM pass first** - discover supporting jobs, state model, ops, observability, onboarding, and trust surfaces before deciding what belongs in the milestone.
- **Story-derived completeness** - derive missing interface behavior from user stories and journeys first, then use familiar archetypes as a sanity check.
- **Usable v1 completeness** - for familiar app types, include the expected baseline surfaces and states that make the product actually usable.
- **North star, then milestone** - define the ambitious product first, then choose the current slice without erasing the rest.
- **Frontend with opinions** - prefer `shadcn/ui`, ShadCN Blocks, and responsive layouts from the start.
- **Explicit architecture** - do not drift into file-based routing unless the project or user specifically wants it.
- **Evidence over claims** - run the checks before saying something works.

## What's Inside

### Core Skills

- **using-ultrapowers** - establishes skill discipline and instruction priority.
- **brainstorming** - turns ideas into an approved design and spec.
- **writing-plans** - turns a spec into a concrete implementation plan.
- **executing-plans** - executes a written plan inline.
- **subagent-driven-development** - executes a written plan with subagents when available.
- **test-driven-development** - enforces red/green/refactor.
- **systematic-debugging** - structured debugging workflow.
- **verification-before-completion** - final proof before completion.
- **requesting-code-review** - asks for review with a bug-finding mindset.
- **receiving-code-review** - helps evaluate and apply review feedback.
- **dispatching-parallel-agents** - coordinates parallel independent tasks.
- **using-git-worktrees** - optional isolation workflow when the user wants it.
- **finishing-a-development-branch** - wraps up branch-based work when relevant.
- **writing-skills** - updates or creates skills with testing discipline.

## Fork Notes

Ultrapowers is intentionally free to diverge from upstream. This repository vendors the upstream project once, then evolves it in place. The goal is not to preserve upstream parity. The goal is to create a reusable skill system with stronger defaults for practical product engineering.

Read [docs/ultrapowers-defaults.md](docs/ultrapowers-defaults.md) for the canonical fork defaults.

## Installation

Ultrapowers is not currently published in the same plugin marketplaces as `obra/superpowers`. Install it directly from this GitHub repository.

Repository:

```text
https://github.com/danduma/ultrapowers
```

### Codex

1. Clone the repository:

```bash
git clone https://github.com/danduma/ultrapowers.git ~/.codex/ultrapowers
```

2. Expose the skills to Codex:

```bash
mkdir -p ~/.agents/skills
ln -s ~/.codex/ultrapowers/skills ~/.agents/skills/ultrapowers
```

3. Restart Codex.

Optional for subagent-heavy skills:

```toml
[features]
multi_agent = true
```

### OpenCode

Add Ultrapowers to the `plugin` array in your `opencode.json`:

```json
{
  "plugin": ["ultrapowers@git+https://github.com/danduma/ultrapowers.git"]
}
```

Restart OpenCode, then load a skill such as `ultrapowers/brainstorming`.

### Notes

- This repo includes plugin metadata for multiple harnesses, but it is not yet available through official plugin marketplaces.
- If you want to pin a version, use a tag or commit hash in the git URL.
