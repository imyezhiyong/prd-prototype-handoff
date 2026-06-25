# PRD Prototype Handoff

A Codex skill for turning product requirements, screenshots, style references, and Modao prototypes into an AI-ready delivery workflow.

The workflow keeps delivery simple:

- **Modao clickable prototype** is the only human-edited source of truth.
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
Use $prd-prototype-handoff to turn this requirement into a Modao prototype plan and handoff.md.
```

```text
Use $prd-prototype-handoff to check whether this Modao prototype is AI-ready for development.
```

```text
Use $prd-prototype-handoff to regenerate handoff.md from my updated prototype annotation panels.
```

## Deliverables

The skill defaults to two deliverables only:

1. A Modao clickable prototype with structured annotation panels.
2. A consolidated generated `handoff.md` for development and testing.

It intentionally avoids maintaining separate PRD, development handoff, testing handoff, and change-log files unless the project complexity requires them.
