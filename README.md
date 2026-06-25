# PRD Prototype Handoff

A Codex skill for turning product requirements, screenshots, style references, and Modao prototypes into an AI-ready delivery workflow.

The workflow keeps delivery simple:

- **Modao editable prototype source** is created or updated by Codex operating Modao through the `computer-use` plugin when source design is requested.
- **Modao clickable prototype** remains the only human-edited source of truth.
- **`handoff.md`** is generated from prototype annotation panels for development and testing.
- Requirements, fields, actions, rules, states, and acceptance criteria use stable IDs so mainstream AI coding tools can implement with minimal clarification.

## Install

Copy this repository into your Codex skills directory:

```powershell
cd $env:USERPROFILE\.codex\skills
git clone https://github.com/imyezhiyong/prd-prototype-handoff.git
```

Or manually copy the folder so the structure is:

```text
~/.codex/skills/prd-prototype-handoff/SKILL.md
~/.codex/skills/prd-prototype-handoff/agents/openai.yaml
~/.codex/skills/prd-prototype-handoff/references/*.md
```

Restart Codex after installation if the skill does not appear immediately.

## Usage

```text
Use $prd-prototype-handoff to clarify this requirement, operate Modao via computer-use to create the editable prototype, then generate handoff.md.
```

```text
Use $prd-prototype-handoff to update my existing Modao prototype based on these iteration requirements and regenerate handoff.md.
```

```text
Use $prd-prototype-handoff to check whether this Modao prototype is AI-ready for development.
```

## Deliverables

The skill defaults to two deliverables only:

1. An editable Modao prototype source with clickable interactions and structured annotation panels.
2. A consolidated generated `handoff.md` for development and testing.

It intentionally avoids maintaining separate PRD, development handoff, testing handoff, and change-log files unless the project complexity requires them.

## Notes

When Codex needs to create or edit the actual Modao source, Modao must be reachable and logged in. If login, CAPTCHA, workspace permission, save, or share actions are blocked, Codex should stop and ask the user to complete the blocked step instead of substituting Markdown, HTML, or screenshots for the editable source.
