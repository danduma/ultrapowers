# Story-Derived Completeness

Use this reference to expand a sparse product request into a usable v1 by reasoning from user stories and user journeys. This is the primary mechanism for completeness. Archetype references are only a secondary backstop.

The PM pass should happen first. Use its outputs, especially supporting jobs, state model, operational readiness, observability, onboarding, and trust surfaces, as inputs to the story-derived pass.

## Core Idea

Do not ask only, "What controls did the user mention?" Ask, "What does the user need to do, recover from, revisit, understand, or change?" The interface and system behaviors should be inferred from those stories.

## Story Categories To Derive

For app, UI, and product-surface work, derive stories in these categories when relevant:

- primary journey stories,
- first-run and empty-state stories,
- return/revisit stories,
- failure and recovery stories,
- status-awareness stories,
- mutation stories,
- mobile-use stories.

## What Each Category Means

### Primary Journey Stories

What is the main task the user is here to complete?

Examples:

- "As a user, I want to start a conversation with an agent so I can get work done."
- "As a user, I want to create a task and move it through a board."

These stories usually imply the core surface, main action affordances, and the path from entry to completion.

### First-Run And Empty-State Stories

What happens when nothing exists yet?

Examples:

- "As a first-time user, I want to understand how to begin."
- "As a user with no conversations yet, I want an obvious way to start one."

These stories imply onboarding affordances, empty states, and entry-point actions.

### Return/Revisit Stories

How does a user come back later and continue?

Examples:

- "As a user, I want to find a previous conversation and continue it."
- "As a user, I want to reopen a document I edited yesterday."

These stories imply lists, recents, navigation hierarchy, and persistence visibility.

### Failure And Recovery Stories

What happens when the happy path fails?

Examples:

- "As a user, I want to know when a request failed and what I can do next."
- "As a user, I want to retry after a transient failure without losing my work."

These stories imply error notices, retry flows, recovery actions, and backend/frontend coordination.

### Status-Awareness Stories

What does the user need to understand about current state?

Examples:

- "As a user, I want to know whether the agent is still running, waiting for me, or finished."
- "As a user, I want to know whether my changes were saved."

These stories imply spinners, badges, state labels, progress indicators, and completion signals.

Persistence questions often cut across these categories. When a story depends on preferences, drafts, history, or configuration, ask what must persist, where it should live, and what the user expects to survive across sessions and devices.

### Mutation Stories

How does a user revise, retry, fork, resend, undo, or continue from earlier state?

Examples:

- "As a user, I want to edit an earlier prompt and resend from there."
- "As a user, I want to fork a conversation from a prior turn."
- "As a user, I want to retry a failed generation."

These stories imply edit/resend flows, truncation behavior, forking, retry actions, and explicit state transitions.

### Mobile-Use Stories

How does the same job get done on a smaller screen?

Examples:

- "As a mobile user, I still need to navigate conversations and act on the current thread."

These stories imply drawers, sheets, responsive prioritization, and compact affordances.

## How To Infer Interface And System Behavior

For each derived story, ask:

1. What interface affordance does this require?
2. What system behavior does this require?
3. What visible state does the user need?
4. What happens when this fails?
5. What has to be preserved when the user comes back later?
6. Which settings or preferences does this touch, and should each persist?
7. Where should that persisted state live, and who owns it?
8. What happens on reset, migration, logout, or device change?

Also ask:

9. What product state does this touch?
10. What observability or status signal should exist?
11. What would make this feel untrustworthy if it went wrong?

## What Counts As Obvious Vs Debatable

### Obvious Story-Derived Additions

Include by default when they are clearly implied by the stories:

- lists or history for return/revisit stories,
- status indicators for status-awareness stories,
- error notices and retry paths for failure/recovery stories,
- empty states for first-run stories,
- edit/retry/resend actions when mutation stories are core to the product's job.

### Debatable Additions

Confirm with the user before locking them in:

- expensive or complex additions,
- opinionated product bets,
- large scope expansions,
- advanced collaboration, analytics, or automation features,
- behaviors that are plausible but not clearly implied by the approved stories.

## Role Of Archetype References

Use `v1-product-completeness.md` after the story-derived pass:

- as a sanity check,
- as a prior for familiar product types,
- as a way to catch obvious omissions.

Do not use archetype references as a replacement for deriving stories from the actual user request.
