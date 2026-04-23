# Ultrapowers for OpenCode

Guide for using Ultrapowers with [OpenCode.ai](https://opencode.ai).

## Installation

Add Ultrapowers to the `plugin` array in your `opencode.json`:

```json
{
  "plugin": ["ultrapowers@git+https://github.com/danduma/ultrapowers.git"]
}
```

Restart OpenCode. The plugin should install and register the skills automatically.

## Usage

List available skills:

```text
use skill tool to list skills
```

Load a skill directly:

```text
use skill tool to load ultrapowers/brainstorming
```

## Default Posture

- current-repo work by default,
- YOU WILL NEVER CREATE A BRANCH unless explicitly instructed.
- ask the user whether we should work in worktrees as part of the planning,
- YOU WILL ONLY CREATE A WORKTREE if explicitly instructed.
- user stories when they help define behavior,
- `shadcn/ui` as the default UI system,
- start app UI from a ShadCN Block,
- responsive desktop and mobile design from the start,
- avoid file-based routing by default,
- strong backend instrumentation with a scriptable control plane when the project has backend workflows,
- no silent or heavily abstracted errors by default, with full error details and stack traces surfaced to the frontend when a frontend exists,
- explicit persistence design for meaningful UI settings, including storage location and lifecycle behavior.

## Personal Skills

Create your own skills in `~/.config/opencode/skills/`.

## Project Skills

Project-specific skills can live in `.opencode/skills/` inside a repository.

**Skill Priority:** Project skills > Personal skills > Ultrapowers skills

## Updating

OpenCode reinstalls git-based plugins on restart. To pin a specific revision, use a tag or commit hash in the plugin URL.
