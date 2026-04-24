# Ultrapowers - Add a PM to your coding agent

Ultrapowers is an opinionated software development methodology for coding agents. It does some of the job of a PM, helping the agent think through the product requirements based on user stories, and some of the work of QA (agentic user journey testing).

Why should you use Ultrapowers? Because you don't want to waste your days
- reinventing the UI - just use shadcn/ui, next.js
- reimplementing basic usage patterns like an AI chat app
- tweaking the interface so it looks good on mobile
- iterating over common API errors
- refactoring a 4000-line `page.tsx` file
- on unnecessary ceremony

This is a fork of `obra/superpowers` that aims to be more practical and usable for product engineering. It comes with strong defaults for shipping useful products quickly, with less ceremony and more attention to what users are actually trying to accomplish.

Works best if you are a solo developer who wants to get a decent product out as quickly as possible.

## What It Helps With

Ultrapowers gives your coding agent a stronger product-engineering spine:

- Asks the agent to think like a practical, results-oriented PM before it starts building.
- Agentic end-to-end  user journey testing.
- Turns rough product ideas into user stories, user journeys, and concrete implementation plans.
- Pushes app work toward fully usable v1s.
- Starts with practical frontend defaults: `shadcn/ui`, ShadCN Blocks, and responsive desktop/mobile design from the start.
- Pushes for more inspectable backend work through instrumentation and explicit errors
- Treats settings persistence, app state, loading states, recovery paths, and trust surfaces as part of the product
- Keeps you out of merge hell

## Basic Workflow

After installing Ultrapowers, the agent will normally automatically use it next time you need to create a plan or tackle a deeper bug.

The usual flow is:

1. **Brainstorm** the product goal, user stories, and scope.
2. **Write a plan** that turns the approved design into concrete implementation steps.
3. **Implement** with the appropriate execution skill.
4. **Verify** with tests, code review, and completion checks.

For app work, Ultrapowers will also push the agent to think about PM concerns, UI completeness, persistence, instrumentation, error visibility, and whether an approval-gated agentic user journey test would be useful.

## Philosophy

Ultrapowers is deliberately opinionated about product work. It tries to make coding agents slower at the moments where shallow automation causes rework: before scoping, before choosing the first UI shape, before declaring a feature done, and before trusting "no errors" as proof of user success.

The big idea is simple: the agent should understand what the user is trying to do, design for the whole journey, build in coherent slices, and verify that the app is actually usable. The hard operational rules live in the skills and defaults docs; this README is the human map.

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

Install it directly from this repository.

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