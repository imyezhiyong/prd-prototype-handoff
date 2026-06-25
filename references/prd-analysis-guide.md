# PRD Analysis Guide

Use this reference before clarifying or structuring requirements.

## Request Classification

Classify the user's request into one of four modes:

- **New project or new feature**: needs goals, roles, page structure, visual references, and full flow definition.
- **Existing-feature iteration**: needs current screenshots/prototype, change list, impacted pages, compatibility and regression concerns.
- **Prototype audit**: checks whether the current prototype is understandable and AI-ready.
- **Handoff regeneration**: uses updated prototype annotation text to regenerate `handoff.md`.

## Minimum Clarification Targets

Resolve these before producing final prototype instructions or handoff content:

- Product goal and target users.
- Business scope and explicit out-of-scope items.
- Main user tasks and success criteria.
- Page list and navigation flow.
- Data fields and validation rules.
- User actions and system responses.
- Permissions, roles, and visibility rules.
- Default, loading, empty, error, success, and permission states.
- Acceptance criteria in testable language.
- Visual reference: style/layout/component reference for new work; current screenshots/prototype for iteration.

## New Project Workflow

1. Summarize the product goal and user roles.
2. Derive the page directory and core flows.
3. Define the design/style reference that the Modao prototype should follow.
4. Produce per-page annotation-panel drafts.
5. Call out missing business rules and assumptions.
6. Prepare the first `handoff.md` only after the prototype annotation content is stable.

## Existing Iteration Workflow

1. Identify current-state source: screenshots, existing Modao page, production URL, or user description.
2. Separate changes into added, modified, removed, and unchanged behavior.
3. Preserve IDs for unchanged pages, fields, actions, rules, states, and ACs when known.
4. Add new IDs only for new behavior.
5. Include impact scope and regression focus in the review homepage and `handoff.md` change log.
6. Regenerate the complete `handoff.md`; avoid manual patchwork that can desync from the prototype.

## Writing Requirements For AI

Use explicit condition/outcome language:

- Good: `RULE-003 If date range exceeds 180 days, disable Search and show "最多查询 180 天".`
- Bad: `Date search should be reasonable.`

Use testable acceptance criteria:

- Good: `AC-002 Given an empty result set, when search completes, then show STATE-002 with copy "暂无数据" and keep Reset enabled.`
- Bad: `Empty state should be handled.`

## Assumption Handling

When information is missing but work can continue:

- State the assumption in the prototype annotation panel and `handoff.md`.
- Use `ASSUMPTION-ID` only when the assumption materially affects development.
- Do not hide uncertain rules inside visual-only mockups.
