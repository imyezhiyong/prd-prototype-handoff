---
name: prd-prototype-handoff
description: Use when turning product requirements, feature ideas, existing-feature iterations, screenshots, style references, or Modao prototypes into an AI-ready delivery workflow that creates or updates a real editable Modao prototype by operating the Modao app/web UI through the computer-use plugin, then generates handoff.md. Use for PRD clarification, direct Modao source design, clickable interaction creation, AI annotation panels, handoff.md regeneration, iteration updates, and quality checks. Do not substitute Markdown, HTML, screenshots, SVG, PNG, or static specs when the user asks for an editable Modao prototype/source.
---

# PRD Prototype Handoff

Use this skill to turn a product idea or iteration request into two deliverables:

1. A real editable Modao prototype source, created or updated by operating Modao through the `computer-use` plugin when source design is requested.
2. A generated `handoff.md` as the single AI-readable text handoff for development and testing.

The Modao prototype is the only human-edited source of truth after the first draft. `handoff.md` is generated from prototype annotation panels and must be marked generated.

## Hard Boundary: Editable Modao Source

- If the user asks for a Modao prototype, editable Modao source file, 墨刀源文件, or asks Codex to complete prototype design, Codex must use the `computer-use` plugin to operate the Modao desktop app or Modao web app directly.
- Do not deliver only Markdown, HTML, screenshots, SVG, PNG, a descriptive spec, or a Figma-style substitute when an editable Modao source is requested.
- Use MCP/API/import automation only when it is actually available and more reliable than UI operation. Otherwise use computer-use.
- If Modao is not installed, not open, not logged in, blocked by CAPTCHA, lacks permission, or cannot save/share the file, stop and report the exact blocker. Ask the user to complete the blocked step or provide access.
- HTML prototypes may be used only as visual references or fallback previews, never as the editable Modao source of truth.

## Required Computer-Use Flow

When creating or editing the Modao prototype source:

1. Read `references/prd-analysis-guide.md` and clarify the product requirements enough to avoid ambiguous UI work.
2. Read `references/modao-computer-use.md` and `references/prototype-standard.md`.
3. Load and follow the `computer-use` skill before automating Windows apps.
4. Find or launch Modao. Prefer an already logged-in Modao desktop app or browser window.
5. Create or open the target project/file, then build editable pages, components, interactions, states, and AI annotation panels directly in Modao.
6. Verify the created source visually inside Modao before claiming completion.
7. Return the Modao share link or project/file identifier, plus the generated `handoff.md` if requested.

## Operating Principles

- Treat the Modao prototype as the only manual edit surface after the first draft.
- Treat `handoff.md` as generated output. Mark it as generated and do not ask the user to maintain it by hand.
- Make AI read structure, not guess screenshots. Every prototype page needs an AI annotation panel with IDs, rules, states, and acceptance criteria.
- Keep all IDs stable across iterations: `PAGE`, `REQ`, `FIELD`, `ACTION`, `RULE`, `STATE`, `AC`.
- Remove vague language before handoff. Do not leave phrases such as `same as above`, `handle normally`, `see prototype`, `TBD`, `confirm later`, `同上`, `按常规处理`, `待确认`, or `后续补充`.

## Workflow

1. Classify the request as a new product/feature, existing-feature iteration, prototype audit, handoff regeneration, or direct Modao source-design task.
2. Read `references/prd-analysis-guide.md` before clarifying or structuring requirements.
3. For Modao source creation/update, read `references/modao-computer-use.md` and `references/prototype-standard.md`; then operate Modao through computer-use.
4. Build the editable Modao prototype with review homepage, page screens, reusable UI patterns, clickable interactions, state pages/cards, and annotation panels.
5. If the user asks for final delivery or handoff regeneration, read `references/handoff-template.md` and generate one consolidated `handoff.md` from the Modao annotation panels.
6. Before final handoff or audit conclusions, read `references/quality-checklist.md` and explicitly check whether the prototype and handoff are AI-ready.

## Clarification Rules

Ask only for missing information that materially affects the product spec or source creation. Prefer proceeding with explicit assumptions when risk is low, except when Modao access, login, or permissions are blocked.

Always establish:

- Goal and target users.
- New project or existing-feature iteration.
- In-scope and out-of-scope behavior.
- Main pages and user flow.
- Data fields, actions, business rules, permissions, states, and acceptance criteria.
- Visual source: style reference for new projects, existing screenshots or prototype references for iterations.
- For direct Modao source delivery: target Modao workspace/project, whether to create a new file or update an existing file, and share/export expectations.

## Output Defaults

For planning a Modao prototype, output:

- Modao review homepage content.
- Page directory with `PAGE-ID` and related `REQ-ID`.
- Core clickable interaction paths.
- Per-page annotation panel content.
- Required states, modals, and rule overlays.
- Open assumptions and unresolved risks.
- Modao access status: ready, blocked, or needs user action.

For delivery after operating Modao, output:

- Editable Modao project/file URL or source identifier.
- Summary of created/updated pages and interactions.
- Generated `handoff.md` path or content when requested.
- Quality checklist result.

For delivery when Modao cannot be operated, output only a blocker report and the exact user action needed. Do not call a Markdown or HTML file a Modao source file.

For handoff delivery, output one `handoff.md` with:

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
- Use computer-use to modify the existing Modao source directly when requested.
- Identify changed pages, actions, rules, states, and acceptance criteria.
- Preserve stable IDs for unchanged items.
- Add new IDs only for genuinely new items.
- Regenerate the full `handoff.md`; do not patch isolated sections unless the user asks.
- Include a concise change log for the current version.

## Boundaries

- Do not create separate `PRD.md`, `ai-dev-handoff.md`, `ai-test-handoff.md`, or `change-log.md` unless the project complexity or user request requires it.
- Do not create a fake `.modao` file or arbitrary JSON and present it as importable unless Modao documentation confirms that format.
- If direct prototype extraction is unavailable, use visible annotation panels in Modao as the source for `handoff.md`, or ask the user to provide copied annotation-panel text.
