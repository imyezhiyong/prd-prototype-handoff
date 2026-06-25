---
name: prd-prototype-handoff
description: Use when turning product requirements, new feature ideas, existing-feature iterations, screenshots, style references, or Modao prototypes into an AI-ready delivery workflow. Guides PRD clarification, Modao clickable prototype structure, AI-readable page annotation panels, simplified handoff.md generation, iteration updates, and quality checks so teams and mainstream AI coding/testing tools can develop from the handoff with minimal clarification.
---

# PRD Prototype Handoff

Use this skill to turn a product idea or iteration request into two simple deliverables:

1. A Modao clickable prototype as the only human-edited source of truth.
2. A generated `handoff.md` as the single AI-readable text handoff for development and testing.

Do not multiply documents unless the user explicitly asks. Keep the workflow optimized for low maintenance: edit the prototype once, regenerate `handoff.md`, and avoid hand-editing generated files.

## Operating Principles

- Treat the Modao prototype as the only manual edit surface after the first draft.
- Treat `handoff.md` as generated output. Mark it as generated and do not ask the user to maintain it by hand.
- Make AI read structure, not guess screenshots. Every prototype page needs an AI annotation panel with IDs, rules, states, and acceptance criteria.
- Keep all IDs stable across iterations: `PAGE`, `REQ`, `FIELD`, `ACTION`, `RULE`, `STATE`, `AC`.
- Remove vague language before handoff. Do not leave phrases such as "same as above", "handle normally", "see prototype", "TBD", or "confirm later".

## Workflow

1. Classify the request as a new product/feature, an existing-feature iteration, a prototype audit, or a handoff regeneration.
2. Read `references/prd-analysis-guide.md` before clarifying or structuring requirements.
3. If the user is creating or updating a Modao prototype, read `references/prototype-standard.md` and output the page list, interaction paths, annotation panel content, and state coverage requirements.
4. If the user asks for final delivery content or a regenerated handoff, read `references/handoff-template.md` and generate one consolidated `handoff.md`.
5. Before final handoff or audit conclusions, read `references/quality-checklist.md` and explicitly check whether the prototype and handoff are AI-ready.

## Clarification Rules

Ask only for missing information that materially affects the product spec. Prefer proceeding with explicit assumptions when the risk is low.

Always establish:

- Goal and target users.
- New project or existing-feature iteration.
- In-scope and out-of-scope behavior.
- Main pages and user flow.
- Data fields, actions, business rules, permissions, states, and acceptance criteria.
- Visual source: style reference for new projects, existing screenshots or prototype references for iterations.

## Output Defaults

For planning a prototype, output:

- Modao review homepage content.
- Page directory with `PAGE-ID` and related `REQ-ID`.
- Core clickable interaction paths.
- Per-page annotation panel content.
- Required states, modals, and rule overlays.
- Open assumptions and unresolved risks.

For delivery, output one `handoff.md` with:

- Project overview.
- Version and scope.
- Page directory and core flows.
- Page requirements and rules.
- Fields, actions, states, and exceptions.
- Development guidance.
- Testing and acceptance checklist.
- Change log.

## Iteration Mode

When the user changes the requirement or prototype:

- Keep the prototype as the only manual change target.
- Identify changed pages, actions, rules, states, and acceptance criteria.
- Preserve stable IDs for unchanged items.
- Add new IDs only for genuinely new items.
- Regenerate the full `handoff.md`; do not patch isolated sections unless the user asks.
- Include a concise change log for the current version.

## Boundaries

- Do not claim Modao API automation exists unless the user provides a working API/export path.
- If direct prototype extraction is unavailable, ask the user to provide exported screenshots plus copied annotation-panel text, then generate or update `handoff.md` from that structured content.
- Do not create separate `PRD.md`, `ai-dev-handoff.md`, `ai-test-handoff.md`, or `change-log.md` unless the project complexity or user request requires it.
