# Modao Computer-Use Workflow

Use this reference when the user asks Codex to create, edit, or finish the actual editable Modao prototype source.

## Required Outcome

The primary deliverable is a real editable Modao project/file created or updated inside Modao. The deliverable should be a Modao share link, project URL, file URL, or visible saved file in the user's Modao workspace.

Supplementary Markdown, HTML, screenshots, SVG, PNG, or static specs are not acceptable substitutes for the Modao source.

## Tool Requirement

Use the `computer-use` plugin to operate the Modao desktop app or Modao web app directly.

Before operating Modao:

- Read and follow the `computer-use` skill instructions.
- Use its app/window discovery and screenshot workflow.
- Do not automate Windows apps through PowerShell, SendKeys, or ad hoc UI scripts.
- Do not automate login, CAPTCHA, payment, or permission-changing steps. Ask the user to complete those steps.

## Readiness Checklist

Before promising source-file delivery, verify:

- Modao desktop app or Modao web app is reachable.
- The user is logged in, or the user can log in manually when prompted.
- The target workspace/project is known, or the user permits creating a new project.
- The target prototype can be saved and shared.
- The visible Modao canvas allows editable text, shapes, components, links, pages, and annotation panels.

If any item is blocked, stop and report the blocker.

## Source Design Steps

1. Open or launch Modao.
2. Create a new prototype file or open the existing target file.
3. Create `REVIEW-HOME` as the first page.
4. Create the page directory using `PAGE-ID` names.
5. Build screens with editable Modao elements, not flattened images.
6. Add reusable patterns for nav, topbar, forms, tables, cards, modals, status tags, and buttons.
7. Add clickable interactions for main flows, page transitions, modal open/close, success paths, and failure paths.
8. Add state pages or state blocks for default, loading, empty, error, permission, and success states.
9. Add AI annotation panels beside each screen using the template in `prototype-standard.md`.
10. Save the file, create/share the link when requested, and verify the final page list and interactions visually.

## Efficient UI Operation Guidance

- Prefer keyboard shortcuts and Modao's built-in duplicate/group/component tools where available.
- Build one high-quality page pattern first, then duplicate and adapt for related pages.
- Keep annotation panels as visible text blocks on the canvas so reviewers and AI tools can read them from screenshots or copied text.
- Use stable page names: `PAGE-001 | REQ-001 | <page name>`.
- Use visible labels for key actions: `ACTION-001`, `RULE-001`, `STATE-001`, `AC-001`.
- If exact pixel-perfect layout is slow, prioritize editable structure, component consistency, interaction completeness, and AI-readable annotations.

## Verification Before Final Answer

Check inside Modao that:

- The project/file is saved.
- The review homepage exists.
- Each required page exists and uses editable elements.
- Core flow links are clickable.
- Annotation panels are visible and readable.
- Required states are represented.
- The share link or project identifier is available when requested.

## Blocker Response Template

When Modao cannot be operated, respond with:

```md
Cannot create or update the editable Modao source yet because Modao is blocked.

Blocked at:
- <app not installed / login required / CAPTCHA / missing permission / workspace unknown / save/share blocked>

Needed from you:
- <specific action the user must take>

I can still prepare the page structure and annotation-panel content, but I will not label Markdown/HTML/screenshots as the editable Modao source.
```
