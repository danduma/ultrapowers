# Codex Tool Mapping

Skills use Claude Code tool names. In Codex, map them to the native equivalents:

| Skill references | Codex equivalent |
|-----------------|------------------|
| `Task` tool (dispatch subagent) | `spawn_agent` |
| Multiple `Task` calls (parallel) | multiple `spawn_agent` calls when delegation is explicitly allowed |
| Task returns result | `wait_agent` |
| Task completes automatically | `close_agent` |
| `TodoWrite` | `update_plan` |
| `Skill` tool | load and follow the relevant skill instructions |
| `Read`, `Write`, `Edit` | native Codex file tools |
| `Bash` | native Codex shell tools |

## Codex Notes

- Default to working in the current repository unless the user explicitly instructs a different repository workflow.
- Do not assume extra repository isolation, push, or PR steps are part of normal execution.
- Use subagents only when the user explicitly allows delegated agent work.
- Adapt completion steps to the actual repository state instead of forcing a different workflow.
