# Ultrapowers

Ultrapowers is an opinionated software development methodology for coding agents. It does some of the job of a PM without the faff, helping the agent think through the product requirements based on user stories.

Why should you use Ultrapowers? Because you don't want to
- reinvent the UI wheel - just use shadcn/ui, next.js
- waste the first 2 days reimplementing basic usage patterns like an AI chat app
- waste another day tweaking the interface so it looks good on mobile
- waste another day iterating over common API errors
- waste 100 days in unnecessary workflow ceremony

Ultrapowers is an opinionated fork of `obra/superpowers` that tries to be more practical and usable for product engineering. It has strong defaults to better fit practical product work and less ceremony. 

This works best if you are solo developer who just wants to get a decent product out as quickly as possible.

## Core Defaults

- Work in the current repository by default.
- YOU WILL NEVER CREATE A BRANCH unless explicitly instructed.
- Ask the user whether we should work in worktrees as part of the planning.
- YOU WILL ONLY CREATE A WORKTREE if explicitly instructed.
- Run a PM pass for app, UI, and product-surface work before completeness or implementation planning.
- Plan agentic user journey tests for important app/user stories when useful, but only run them with explicit user approval.
- Refactor code when a file passes 1200 lines instead of continuing to grow it without structure.
- Use user stories in specs and plans when they clarify behavior.
- Default UI work to `shadcn/ui`.
- Start app UI from a shadcn/ui block or pattern, no point in inventing a layout from scratch.
- Treat desktop and mobile responsiveness as first-class from the beginning.
- Do not default to file-based routing.
- Prefer strong backend instrumentation and a fully instrumented control plane.
- Prefer explicit, non-silent error handling with full error details and stack traces surfaced to the frontend.
- Make persistence of UI settings explicit: decide per setting whether it persists, where it is stored, and how lifecycle concerns like reset and migration work.
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

## Philosophy

- **Skills first** - check for the right workflow before acting.
- **User intent over ritual** - follow the user's instructions even when they override defaults.
- **No surprise repo workflow** - stay in the current repository unless the user explicitly instructs otherwise.
- **Lightweight by default** - avoid extra ceremony unless it solves a real problem.
- **Product-minded planning** - use user stories and acceptance thinking where it helps.
- **PM pass first** - this is not optional for app, UI, and product-surface work. Discover supporting jobs, state model, ops, observability, onboarding, trust surfaces, and north-star product direction before deciding what belongs in the milestone.
- **Story-derived completeness** - derive missing interface behavior from user stories and journeys first, then use familiar archetypes as a sanity check.
- **Agentic journey tests by approval** - when useful, verify user stories by giving an agent only the running app and a mission, but run that higher-cost test mode only with explicit user approval.
- **Usable v1 completeness** - for familiar app types, include the expected baseline surfaces and states that make the product actually usable.
- **North star, then milestone** - define the ambitious product first, then choose the current slice without erasing the rest.
- **Frontend with opinions** - prefer `shadcn/ui`, ShadCN Blocks, and responsive layouts from the start.
- **Explicit architecture** - do not drift into file-based routing unless the project or user specifically wants it.
- **Instrumented by default** - capture meaningful backend events, actions, errors, and outcomes in durable logs, and expose a CLI or other scriptable control plane so workflows can be exercised and verified without the UI.
- **No silent failures** - do not hide, overly abstract, or hand-wave errors; surface real error details and stack traces to the frontend so failures are inspectable and testable.
- **Persistence is designed, not implied** - for each meaningful UI setting, make storage location, ownership, sync model, reset path, and migration behavior explicit.
- **File growth is a signal** - when a file passes 1200 lines, refactor it rather than normalizing continued growth.
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
- **agentic-user-journey-testing** - approval-gated black-box user journey verification for running apps.
- **requesting-code-review** - asks for review with a bug-finding mindset.
- **receiving-code-review** - helps evaluate and apply review feedback.
- **dispatching-parallel-agents** - coordinates parallel independent tasks.
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

### Claude Code

1. Clone the repository:

```bash
git clone https://github.com/danduma/ultrapowers.git ~/.claude/ultrapowers
```

2. Expose the skills to Claude Code:

```bash
mkdir -p ~/.claude/skills
for d in ~/.claude/ultrapowers/skills/*; do
  ln -s "$d" ~/.claude/skills/$(basename "$d")
done
```

3. If you previously had the upstream `superpowers` plugin enabled, disable it in `~/.claude/settings.json` to avoid duplicate skill resolution.

4. Restart Claude Code.

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

### Gemini

1. Clone the repository into Gemini's extensions directory:

```bash
git clone https://github.com/danduma/ultrapowers.git ~/.gemini/extensions/ultrapowers
```

2. If your Gemini CLI uses `~/.gemini/extensions/extension-enablement.json`, add an `ultrapowers` entry there so the extension is enabled for your workspace paths.

3. Restart Gemini CLI.

The repo already includes `gemini-extension.json` and `GEMINI.md`, so Gemini can load Ultrapowers directly from the cloned extension directory.

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
