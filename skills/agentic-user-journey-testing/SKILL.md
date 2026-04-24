---
name: agentic-user-journey-testing
description: Use when validating app, UI, or product-surface work through the running app, especially when logs/tests pass but a user job may still be blocked or unclear
---

# Agentic User Journey Testing

## Overview

An app is not done because logs are quiet. It is done when a user can complete the intended job through the running interface.

Agentic user journey testing is a black-box verification mode: give an agent only the running app, an interface to operate it, and a user mission. If the agent cannot complete the mission, the product is not yet usable for that story.

## Approval Gate

This test mode can spend significant tokens and time.

Do not run an agentic user journey test unless the user explicitly approves it or directly asks for it.

Without approval, you may:

- identify candidate journeys,
- write the mission prompts,
- explain what the test would prove,
- add deterministic tests that support the same behavior.

Before running, ask for approval and name:

- the user mission,
- the running app URL or entry point,
- the expected visible completion state,
- the estimated cost or scope in plain language.

If approval is not given, say the agentic journey test was planned but not run.

## When To Use

Use for app, UI, and product-surface work where user success depends on more than a single function or endpoint.

Especially use when:

- logs show no errors but the visible app state may be wrong,
- the UI may be confusing even if the code path works,
- a workflow spans multiple screens, statuses, or async states,
- loading, unread, waiting, completed, or error states matter,
- the task is about whether a real user can accomplish a job.

## Test Contract

Each test needs a mission card:

- **Running app:** URL, route, or entry point.
- **User role:** who the agent is pretending to be.
- **Mission:** the job to accomplish in user language.
- **Allowed interface:** browser, app UI, keyboard, pointer, accessibility tree, or other user-level controls.
- **Forbidden shortcuts:** no source inspection, no backend logs, no database queries, no implementation knowledge unless the user explicitly allows it.
- **Expected completion proof:** the visible state that proves the job is complete.
- **Failure conditions:** places where "no error" still counts as failure.

Example:

```text
Running app: http://localhost:3050/session/<id>
User role: operator returning to a direct-control session
Mission: determine whether the CLI is waiting for input and clear the unread state by reading it
Allowed interface: browser UI only
Expected completion proof: unread state appears until read; after reading, there is no spinner and no unread dot
Failure conditions: spinner keeps spinning, no visible status changes, user cannot tell what to do, or the app silently does nothing
```

## How To Run

Use the current harness's browser or UI-control tools. Behave like a user:

1. Open the app at the provided entry point.
2. Inspect only what a user could perceive.
3. Decide where to click or type from the interface itself.
4. Attempt the mission.
5. Record visible evidence of success or the exact point of failure.

Do not treat clean logs, HTTP 200 responses, or lack of console errors as success. Those are supporting signals only.

## Pass Criteria

The journey passes only when:

- the agent can understand what to do from the UI,
- the agent can complete the mission through user-level actions,
- the visible app state matches the expected completion proof,
- no stale loading, misleading status, silent no-op, or hidden failure remains.

## Failure Means Work Remains

If the journey fails, fix the product or the supporting state model. Do not dismiss the failure as "just the test agent being confused" unless there is clear evidence the mission was malformed.

Common product failures:

- the app is technically idle but still shows running state,
- a click succeeds internally but nothing visible changes,
- the user cannot discover the next action,
- the UI hides the real error,
- the completion state is ambiguous.

## Relationship To Other Tests

Agentic journey tests complement deterministic tests. They do not replace:

- unit tests,
- integration tests,
- state-machine tests,
- accessibility checks,
- deterministic Playwright assertions.

When a journey fails, add deterministic regression coverage for the underlying behavior whenever practical.
