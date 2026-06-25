# Quality Checklist

Use this checklist before declaring a prototype plan, audit, or `handoff.md` ready.

## Team Readability

- The review homepage explains project, version, scope, roles, page directory, and core flows.
- A reviewer can understand each page without opening a separate PRD.
- Every page has a clear goal, entry, exit, and related requirement IDs.
- Important rules are visible in the prototype annotation panels or rule overlays.

## AI Readiness

- Every page has a `PAGE-ID`.
- Every requirement has a `REQ-ID`.
- Every important field has a `FIELD-ID` plus type, required status, validation, and error copy.
- Every clickable operation has an `ACTION-ID` plus trigger, result, success, and failure behavior.
- Every business rule has a `RULE-ID` written as condition plus outcome.
- Every visible state has a `STATE-ID` plus expected UI behavior.
- Every acceptance criterion has an `AC-ID` and can be tested.
- The prototype or `handoff.md` tells AI to use structured annotation panels as source of truth.

## Development Coverage

- Routes or page entries are clear enough for implementation.
- Suggested components are identifiable from repeated UI patterns.
- Data entities, field constraints, and enums are defined or explicitly assumed.
- API needs are defined, or mock-data requirements are stated.
- Permission and error handling are explicit.
- Loading, empty, error, permission, and success states are covered for core flows.

## Testing Coverage

- Each acceptance criterion maps to a test checklist item.
- Main path, branch path, exception path, permission path, and boundary values are represented.
- Iterations include regression focus and changed IDs.
- Expected results are written as observable outcomes.

## Desync Prevention

- The Modao prototype is the only manual edit source.
- `handoff.md` is marked as generated.
- Changed prototype IDs appear in the change log.
- Unchanged IDs are not renumbered.
- No generated file is treated as a separate source of truth.

## Forbidden Ambiguity

Reject or rewrite these phrases before handoff:

- `同上`
- `见原型`
- `按常规处理`
- `正常校验`
- `待确认`
- `后续补充`
- `适配即可`
- `合理展示`
- `开发自行处理`
