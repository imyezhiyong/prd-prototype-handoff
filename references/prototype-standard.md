# Modao Prototype Standard

Use this reference when creating, reviewing, or updating the Modao clickable prototype spec.

## Prototype Role

The Modao prototype is the only human-edited source of truth. It must contain both visual UI and structured requirements so reviewers and AI coding tools do not need to jump between separate PRD files.

## Required Page Layout

Each prototype page should include three areas:

- **UI canvas**: the real screen, using editable Modao elements and clickable interactions.
- **AI annotation panel**: a structured text panel next to the UI.
- **State area**: related modals, empty states, loading states, errors, permission states, and success states.

Avoid full-screen flattened screenshots as the primary UI. Screenshots may be used only as references or visual assets.

## Review Homepage Template

Create a first page named `REVIEW-HOME` with:

```md
PROJECT: <project name>
VERSION: <version>
UPDATED-AT: <date>
OWNER: <owner>

REVIEW-SCOPE:
- <included feature or flow>

OUT-OF-SCOPE:
- <explicit exclusion>

USER-ROLES:
- <role and goal>

PAGE-DIRECTORY:
- PAGE-001 <page name> -> related REQ IDs

CORE-FLOWS:
- FLOW-001 <entry page> -> <result page/state>

CHANGE-SUMMARY:
- <added/changed/removed item>

AI-INSTRUCTION:
Use annotation panels and IDs as the source of truth. Do not infer business rules from visuals only.
```

## Page Annotation Panel Template

Every page must include this panel, adapted to the page:

```md
PAGE-ID: PAGE-001
PAGE-NAME: <page name>
RELATED-REQ: REQ-001, REQ-002
USER-ROLE: <role>

PAGE-GOAL:
<what the user accomplishes here>

ENTRY:
<how users arrive here>

EXIT:
<where users can go next; include target PAGE or STATE IDs>

FIELDS:
FIELD-001 <name>: <type>, <required/default/value range>, <validation>, <error copy>

ACTIONS:
ACTION-001 <trigger>: <result>; success -> <PAGE/STATE>; failure -> <STATE>

RULES:
RULE-001 <business rule written as an explicit condition and outcome>

STATES:
STATE-001 Default: <visible data and controls>
STATE-002 Loading: <loading behavior and disabled controls>
STATE-003 Empty: <empty copy and available action>
STATE-004 Error: <error copy and retry behavior>
STATE-005 Permission: <hidden/disabled/read-only behavior>

ACCEPTANCE:
AC-001 Given <condition>, when <action>, then <expected result>.
```

## ID Rules

- Use stable IDs: `PAGE-001`, `REQ-001`, `FIELD-001`, `ACTION-001`, `RULE-001`, `STATE-001`, `AC-001`.
- Do not renumber unchanged items during iteration.
- Use clear prefixes for special elements when needed: `MODAL-001`, `FLOW-001`, `API-001`.
- Link interactions by ID, for example: `ACTION-003 click order row -> PAGE-002`.

## Interaction Rules

- Every clickable control needs an `ACTION-ID`.
- Every action needs a success result and failure result when failure is possible.
- Every navigation needs a target page or target state.
- Every modal needs an open condition, confirm result, cancel result, and close behavior.
- Every form field needs type, required status, default, validation, and error copy.
- Every permission rule needs actor, visibility behavior, and blocked behavior.

## State Coverage

For each core page, represent required states visibly as pages, modals, cards, or annotated state blocks:

- Default state.
- Loading or submitting state.
- Empty state.
- Error or network failure state.
- Permission denied or read-only state.
- Success state when the user receives confirmation.

Do not rely on text-only PRD descriptions for high-risk states.
