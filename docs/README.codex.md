# Ultrapowers for Codex

Guide for using Ultrapowers with OpenAI Codex via native skill discovery.

Ultrapowers is not currently published in the Codex plugin marketplace. Install it directly from the GitHub repository instead.

## Quick Install

Tell Codex:

```text
Fetch and follow instructions from https://raw.githubusercontent.com/danduma/ultrapowers/refs/heads/main/.codex/INSTALL.md
```

## Manual Installation

### Prerequisites

- OpenAI Codex CLI or Codex App
- Git

### Steps

1. Clone the fork:

```bash
git clone https://github.com/danduma/ultrapowers.git ~/.codex/ultrapowers
```

2. Create the skills symlink:

```bash
mkdir -p ~/.agents/skills
ln -s ~/.codex/ultrapowers/skills ~/.agents/skills/ultrapowers
```

3. Restart Codex.

4. For subagent skills, enable Codex multi-agent support:

```toml
[features]
multi_agent = true
```

## How It Works

Codex scans `~/.agents/skills/` at startup, reads `SKILL.md` frontmatter, and activates matching skills on demand. Ultrapowers works through one visible skills directory:

```text
~/.agents/skills/ultrapowers/ -> ~/.codex/ultrapowers/skills/
```

The important behavioral defaults come from `using-ultrapowers`, plus the rewritten Ultrapowers skill set.

## Default Posture

- current-repo work by default,
- YOU WILL NEVER CREATE A BRANCH unless explicitly instructed.
- ask the user whether we should work in worktrees as part of the planning,
- YOU WILL ONLY CREATE A WORKTREE if explicitly instructed.
- user stories when they clarify plans,
- every project should have a `.gitignore`,
- never commit or push secrets, local environment files, dependencies, caches, build outputs, logs, or intermediate/generated artifacts,
- `shadcn/ui` for UI work,
- ShadCN Blocks as the first stop for app UI,
- desktop and mobile responsiveness from the start,
- React apps use `building-react-apps` for Manager-owned state, explicit transitions, imports, refs, routing, `pnpm`, and frontend settings,
- no file-based routing by default,
- strong backend instrumentation with a scriptable control plane when the project has backend workflows,
- no silent or heavily abstracted errors by default, with full error details and stack traces surfaced to the frontend when a frontend exists,
- explicit persistence design for meaningful UI settings, including storage location and lifecycle behavior.

## Updating

```bash
cd ~/.codex/ultrapowers && git pull
```

## Uninstalling

```bash
rm ~/.agents/skills/ultrapowers
```

Optionally remove the clone:

```bash
rm -rf ~/.codex/ultrapowers
```
