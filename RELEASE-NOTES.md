# Ultrapowers Release Notes

This file tracks major Ultrapowers-specific changes in this fork.

It is not a copy of upstream `superpowers` history. We only record the changes that meaningfully shape Ultrapowers itself.

## Unreleased

### Fork Direction

- started an Ultrapowers-native release notes file instead of carrying forward upstream release history.
- clarified that Ultrapowers is free to diverge from upstream and should be evaluated on its own defaults and workflow.

### Core Defaults

- made current-repo work by default behavior more central in the docs.
- reinforced product-minded defaults: user stories when useful, `shadcn/ui` for UI work, ShadCN Blocks as the first stop for app UI, desktop and mobile responsiveness from the beginning, and no file-based routing by default.
- emphasized usable-v1 completeness and north-star-first thinking instead of stopping at literal requested controls.

### Instrumentation And Control Plane

- added a stronger default that backend and agent workflows should be instrumented by default.
- established the expectation of a fully instrumented control plane: meaningful actions, tool calls, results, errors, and state transitions should be captured durably and exposed through a CLI or other scriptable interface.
- made end-to-end testability without the UI an explicit default expectation in design and planning guidance.

### Error Transparency

- made silent or heavily abstracted failures explicitly against Ultrapowers defaults.
- established a default of end-to-end error transparency: when a frontend exists, it should preserve full backend error details and stack traces rather than replacing them with vague generic failures.
- pushed this requirement into brainstorming, planning, and verification so it is treated as a design and acceptance concern, not a late implementation detail.

### Persistence Design

- made persistence of UI settings and preferences an explicit design responsibility.
- added guidance that each meaningful setting should declare whether it persists, where it is stored, who owns it, how it is loaded and saved, whether it is local or account-level, and how reset, sync, migration, and verification work.
- extended the PM pass, completeness pass, implementation planning, and verification guidance to check persistence behavior explicitly.

### Process And Verification

- updated the design and planning skills so state model, persistence model, observability, control-plane behavior, and trust surfaces are expected inputs rather than optional nice-to-haves.
- strengthened verification guidance so product-surface checks include observability, error transparency, and persistence behavior when the approved scope depends on them.

### Agentic User Journey Testing

- added `agentic-user-journey-testing` as a black-box verification mode for running apps.
- defined the core standard: product-surface work is not done merely because logs are quiet; a user must be able to complete the intended job through the app.
- made this test mode approval-gated because it can spend significant tokens and time.
- wired candidate journey tests into brainstorming, planning, TDD, and verification while requiring explicit user approval before running them.

## Notes For Future Entries

- Record only major Ultrapowers-specific changes.
- Prefer entries that change defaults, workflow, architecture guidance, or user-visible behavior of the skill system.
- Do not mirror every small edit.
- If a change only belongs to upstream `superpowers`, do not add it here unless Ultrapowers adopts and reframes it as part of this fork.
