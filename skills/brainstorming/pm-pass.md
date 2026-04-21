# PM Pass

Use this reference before the completeness pass for app, UI, and product-surface work. The goal is to think like a strong product manager: understand what the product wants to become, discover the supporting jobs around the core job, and preserve that larger vision even when delivery is staged.

## Core Assumptions

- The first user is usually the human builder unless the prompt says otherwise.
- The core job is usually already implied by the request.
- The missing work is often in the supporting jobs, state model, trust model, and operational reality.
- Agents tend to underbuild unless forced to think beyond the literal prompt. Counteract that tendency here.

## PM Pass Outputs

Produce or infer these sections when relevant:

- First User
- Core Job
- Supporting Jobs
- User Segmentation And Role Clarity
- State Model
- Operational Readiness
- Instrumentation And Observability
- Onboarding And Discoverability
- Risk And Trust Surfaces
- North Star Product
- Current Milestone
- Later Milestones Or Deferred But Intentional Work

## What Each Section Means

### First User

Who is the first person this is really being built for right now?

Default: the human builder.

### Core Job

What is the one main job the first user wants to accomplish?

Do not waste time rediscovering what is already obvious from the prompt.

### Supporting Jobs

What other jobs must the product support so the core job is actually workable in practice?

These often include:

- returning to prior work,
- recovering from failure,
- understanding current status,
- revising earlier state,
- monitoring progress,
- discovering what to do next.

### User Segmentation And Role Clarity

Only go deep here when the product actually has multiple roles. Do not invent fake role complexity for single-user tools.

### State Model

Define the meaningful product states, not just visual states.

Examples:

- draft,
- queued,
- running,
- waiting-for-user,
- failed,
- completed,
- archived,
- forked.

### Operational Readiness

Ask what must work when the real world is messy:

- transient failures,
- missing config,
- degraded providers,
- long-running work,
- partial completion,
- retries and re-entry.

### Instrumentation And Observability

Ask what signals should exist so both the user and the builder can understand what is happening.

This includes:

- user-visible status,
- key logs or events,
- enough observability to debug failures and stuck states.
- durable event history for backend actions and state transitions.
- a scriptable control plane, preferably CLI-accessible, for inspection, replay, admin operations, and end-to-end testing without the UI.
- explicit propagation of real errors to user-facing and operator-facing surfaces instead of generic fallback messages.

For systems with conversations, jobs, tools, or agents, prefer event models that preserve:

- inputs and outputs,
- tool calls and tool results,
- errors and retries,
- stack traces and failure context,
- state transitions,
- timestamps and identifiers needed to reconstruct what happened later.

### Onboarding And Discoverability

Ask what a first-time or returning user sees:

- first-run guidance,
- empty states,
- obvious next action,
- terminology and labels that make sense.

### Risk And Trust Surfaces

Ask where user trust could break:

- silent failure,
- generic error abstraction that hides the real cause,
- ambiguous state,
- lost work,
- destructive actions,
- misleading completion signals.

### North Star Product

Describe what the finished product wants to become if fully realized. Be ambitious. Do not collapse this into the current milestone.

### Current Milestone

Describe the current coherent slice to build now.

This is a sequencing choice, not a reduction in imagination.

### Later Milestones Or Deferred But Intentional Work

List what is intentionally later but still part of the product vision, so the system does not forget it in future iterations.

## Important Distinction

- Be expansive in product imagination.
- Be deliberate in milestone commitment.

YAGNI applies to implementation detail inside the approved milestone. It does not mean shrinking product thinking before the design is even understood.
