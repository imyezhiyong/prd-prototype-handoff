# handoff.md Template

Use this reference when generating the consolidated `handoff.md`. The file is generated from the Modao prototype annotation panels and should not be manually maintained.

Start every generated file with:

```md
> Generated from the Modao prototype annotation panels. Do not hand-edit this file; update the prototype and regenerate.
```

## Recommended Structure

```md
# <Project Name> Handoff

> Generated from the Modao prototype annotation panels. Do not hand-edit this file; update the prototype and regenerate.

## 1. Project Overview
- Goal:
- Users:
- Background:
- Success criteria:

## 2. Version And Scope
- Version:
- Updated at:
- Included scope:
- Out of scope:
- Key changes:

## 3. Page Directory And Core Flows
| Page ID | Page Name | Related Requirements | Entry | Exit |
| --- | --- | --- | --- | --- |

### Core Flows
- FLOW-001: <steps using PAGE/ACTION/STATE IDs>

## 4. Page Requirements And Rules
### PAGE-001 <Page Name>
- Related requirements:
- Page goal:
- Entry:
- Exit:

#### Fields
| Field ID | Name | Type | Required | Default | Validation | Error Copy |
| --- | --- | --- | --- | --- | --- | --- |

#### Actions
| Action ID | Trigger | Result | Success | Failure |
| --- | --- | --- | --- | --- |

#### Rules
| Rule ID | Rule |
| --- | --- |

#### States
| State ID | State | Behavior |
| --- | --- | --- |

#### Acceptance Criteria
| AC ID | Criteria |
| --- | --- |

## 5. Development Guidance
- Suggested routes:
- Suggested components:
- Data model notes:
- API or mock data requirements:
- Permission logic:
- Error handling:
- Analytics or logging, if any:

## 6. Testing And Acceptance Checklist
| Case ID | Related AC | Scenario | Steps | Expected Result | Priority |
| --- | --- | --- | --- | --- | --- |

## 7. Change Log
| Version | Change Type | Changed IDs | Summary | Impact |
| --- | --- | --- | --- | --- |
```

## Generation Rules

- Keep one consolidated file by default.
- Preserve all IDs from the prototype.
- Convert every `AC-ID` into at least one test checklist row.
- Convert every `STATE-ID` into development and testing guidance.
- Convert every `ACTION-ID` into implementation behavior.
- If API details are unknown, write mock-data requirements and mark the assumption explicitly.
- If visual details are only in the prototype, reference page IDs instead of describing every pixel.
- Include a concise change log for iterations.

## AI Coding Guidance

When handing `handoff.md` to coding tools, include this instruction near the top if useful:

```md
AI implementation instruction: Implement from this handoff using the IDs as stable references. Ask for clarification only when an ID has missing fields, actions, rules, states, or acceptance criteria.
```
