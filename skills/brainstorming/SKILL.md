---
name: brainstorming
description: Use before any creative work - creating features, building components, adding functionality, or modifying behavior
---

# Brainstorming Ideas Into Designs

Turn rough ideas into an approved design before implementation begins.

## Hard Gate

Do not implement, scaffold, or change behavior until the design has been presented and approved.

## Checklist

1. Explore project context.
2. Ask clarifying questions one at a time.
3. Run a PM Pass for app, UI, and product-surface requests.
4. Run a Product Completeness Pass for app, UI, and product-surface requests.
5. Propose 2-3 approaches with trade-offs and a recommendation.
6. Present the design in manageable sections and get approval.
7. Write the spec to `docs/superpowers/specs/YYYY-MM-DD-<topic>-design.md`.
8. Self-review for ambiguity, contradictions, placeholders, and scope.
9. Ask the user to review the written spec.
10. Move to `writing-plans`.

## What The Design Should Cover

- goal and constraints,
- architecture and boundaries,
- data flow and error handling,
- error transparency expectations,
- persistence model for settings, preferences, and user-managed state,
- testing strategy,
- user stories when they help define behavior,
- acceptance criteria when they clarify completion,
- supporting jobs,
- state model,
- persistence and ownership model for settings and preferences,
- operational readiness,
- instrumentation and observability expectations,
- control-plane and scriptability expectations,
- error reporting expectations across backend, frontend, and logs,
- onboarding and discoverability expectations,
- risk and trust surfaces,
- north-star product vision,
- current milestone and later milestones,
- baseline expected v1 surfaces and states for familiar product types.

## PM Pass

For app, UI, and product-surface work, run a PM pass before the completeness pass.

During this pass:

- default the first user to the human builder unless the prompt says otherwise,
- assume the core job is usually already implied by the prompt,
- aggressively discover the supporting jobs around that core job,
- identify user segmentation and role clarity when the product genuinely has multiple roles,
- define the state model,
- define the persistence model for settings, preferences, drafts, and other user-managed state,
- define operational readiness expectations,
- define instrumentation and observability expectations,
- define control-plane expectations for inspection, replay, administration, and end-to-end testing,
- define error transparency expectations so failures are not silently swallowed or abstracted away,
- define onboarding and discoverability expectations,
- define the main risk and trust surfaces,
- define the north-star product,
- define the current milestone as one slice of that product,
- define later milestones or deferred-but-intentional work so the product vision is not forgotten.

Use `pm-pass.md` as the reference for this step.

Milestone slicing is for sequencing delivery, not for shrinking the product imagination. Be expansive about the full product. Be deliberate about what belongs in the current milestone.

## Product Completeness Pass

For app, UI, and product-surface work, do not stop at the literal requested controls. Expand the design into a usable v1 by asking what a user would reasonably expect this category of product to include.

During this pass:

- derive the primary user stories,
- derive return/revisit stories,
- derive failure/recovery stories,
- derive status-awareness stories,
- derive mutation stories when the product involves editing, retrying, resubmitting, branching, or other state-changing actions,
- separate:
  - explicitly requested capabilities,
  - baseline expected v1 surfaces and states inferred from the stories,
- map the primary user journey,
- infer the interface surfaces and system behaviors required to satisfy those stories,
- cover expected empty, loading, running, waiting, error, completed, and recovery states,
- cover navigation, hierarchy, and status signaling,
- cover what settings and preferences exist, whether each one persists, and what happens across reload, sign-out, device changes, reset, and migration,
- cover desktop and mobile behavior,
- use the PM pass outputs as inputs,
- use `story-derived-completeness.md` as the primary reference,
- use `v1-product-completeness.md` as a sanity check when the product archetype is familiar.

For non-obvious, costly, opinionated, or materially scope-expanding additions, check with the user before baking them into the spec as committed scope.

You may brainstorm with yourself to expand the completeness pass. Only involve additional agents when the user explicitly wants that or has already allowed delegated brainstorming.

## Ultrapowers Defaults During Brainstorming

When the work involves an app, UI, or product surface, assume these defaults unless the user overrides them:

- use `shadcn/ui`,
- choose a ShadCN Block first for app UI,
- design for desktop and mobile from the beginning,
- make responsiveness part of the initial design,
- avoid file-based routing by default,
- prefer strong backend instrumentation and a scriptable control plane for backend workflows,
- prefer surfacing full error details and stack traces to the frontend instead of replacing them with vague generic failures,
- make persistence behavior for settings explicit instead of leaving storage choices implicit,
- aim for a usable v1, not just the smallest literal UI that exposes requested controls.
- think ambitiously about the full product, then sequence it into coherent milestones.

If the current codebase already has strong conventions, preserve them unless the user asks to change direction.

## Questions

- Ask one question at a time.
- Prefer multiple-choice framing when possible.
- Do not invent extra process when the user has already answered the important decisions.

## Design Quality

- Break systems into focused units with clear responsibilities.
- Prefer explicit interfaces over vague coupling.
- Stay close to the current codebase patterns when working in an existing project.
- Include only refactors that directly support the requested work.
- Discover supporting jobs instead of assuming the prompt listed them all.
- Distinguish obvious category-standard additions from debatable product choices.
- Distinguish story-derived obvious additions from debatable product choices.
- Distinguish north-star product thinking from current-milestone commitment.
- Confirm debatable product choices with the user instead of silently baking them in.

## Review Gate

After writing the spec, ask the user to review it before moving on:

`Spec written and committed to <path>. Please review it and let me know if you want any changes before we start the implementation plan.`

Only after approval should you invoke `writing-plans`.
