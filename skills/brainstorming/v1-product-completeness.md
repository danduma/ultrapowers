# V1 Product Completeness Reference

Use this reference during brainstorming when the request involves a familiar app or product surface. The goal is not to invent extra features. The goal is to avoid shipping a literal shell that lacks the expected surfaces and states needed for a usable v1.

This file is a sanity check and prior, not the primary source of truth. Derive completeness from user stories and journeys first. Use this reference afterward to catch obvious omissions for familiar archetypes.

## How To Use This Reference

1. Derive user stories and journeys from the request first.
2. Identify the closest product archetype.
3. Expand the design into:
   - explicitly requested capabilities,
   - baseline expected v1 surfaces and states.
4. Keep obvious, conventional additions as baseline expected v1 scope.
5. Confirm non-obvious, expensive, risky, or strongly opinionated additions with the user before locking them in.

## Questions To Ask For Any Archetype

- What is the primary user journey?
- What does first-run or empty state look like?
- What does loading, waiting, or in-progress state look like?
- What does success or completed state look like?
- What does failure or recovery look like?
- How does a user find prior work again later?
- What navigation and hierarchy are expected?
- What is different on desktop versus mobile?

## AI Chat / Agent Harness

### Baseline Expected V1

- conversation list or history,
- clear hierarchy when projects or workspaces exist,
- new conversation action,
- active conversation view,
- visible in-progress, waiting, completed, and failed status,
- input area with obvious send/submit affordance,
- empty state when no conversation exists,
- path to resume or revisit prior conversations,
- mobile-safe navigation pattern such as a drawer or sheet.

### Confirm With User Before Locking In

- advanced filtering or search,
- rich multi-pane monitoring surfaces,
- forked conversations,
- advanced model/provider configuration,
- collaborative or multi-user features.

## Kanban / Workflow Board

### Baseline Expected V1

- board navigation,
- column/group structure,
- visible card status,
- clear move/add/edit actions,
- empty state for new boards or columns,
- loading/error handling,
- mobile-safe presentation when horizontal space is limited.

### Confirm With User Before Locking In

- swimlanes,
- automation rules,
- complex permissions,
- timeline or reporting views.

## Document Editor

### Baseline Expected V1

- document list or recents,
- active editing surface,
- save state or persistence signal,
- empty state,
- loading and conflict/error messaging,
- navigation between documents,
- mobile editing fallback that still works.

### Confirm With User Before Locking In

- real-time collaboration,
- comments and suggestions,
- version history,
- advanced formatting systems.

## Admin CRUD Surface

### Baseline Expected V1

- list view,
- detail or edit view,
- create action,
- delete/archive handling,
- empty/loading/error states,
- basic status messaging,
- mobile-safe access to actions and details.

### Confirm With User Before Locking In

- bulk operations,
- role-based permissions,
- audit history,
- advanced filters and exports.

## Dashboard / Monitoring Surface

### Baseline Expected V1

- overview surface,
- clearly labeled primary metrics or status cards,
- refresh/loading behavior,
- empty or no-data states,
- visible alerts/errors,
- path from summary to underlying item or detail,
- mobile layout that preserves priority order.

### Confirm With User Before Locking In

- custom report builders,
- advanced drill-down analytics,
- notification systems,
- saved views or personalization.
