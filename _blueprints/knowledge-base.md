---
name: knowledge-base
type: playbook
description: Organize, write, and maintain documentation so knowledge is findable and current.
parameters:
  - knowledge_domain: What kind of knowledge — technical docs, policies, processes?
  - audience: Who needs to find and use this — engineers, new hires, customers?
references:
  - upload: Your existing style guide or doc templates
---

# Knowledge Base (knowledge_domain, audience)

A workspace for teams drowning in undocumented knowledge. This playbook turns tribal knowledge into structured, reviewable documentation with clear ownership and a maintenance cycle that keeps everything from going stale.

## Follow-up question
What kind of knowledge are you organizing, and who needs it?

## Core problems this workspace solves

- Documentation is outdated — articles describe how things worked six months ago, eroding trust in the entire knowledge base.
- Knowledge is siloed in people's heads — critical processes and decisions exist only in the memory of specific team members.
- It is hard to find the right document — poor organization and inconsistent naming make search useless and browsing painful.
- There is no review process — documents are written once and never revisited, so errors and gaps accumulate silently.
- New documentation has no standard — every author uses a different format, level of detail, and structure, making the collection incoherent.

## Skill blueprints to use

- **Document** — Write new documentation from scratch following a consistent template and structure.
- **Edit** — Revise existing documents for accuracy, clarity, and completeness during scheduled review cycles.
- **Checklist** — Generate review and maintenance checklists to ensure nothing falls through the cracks.
- **Explain** — Break down complex topics into clear, accessible explanations suitable for the target audience.
- **Review** — Run a quality and consistency check on documents before they are published or after major updates.

## Skill outputs

| Skill | Output | Format | Folder |
|--------|--------|--------|--------|
| Document | New documentation article following standard template | Markdown | `files/docs/` |
| Edit | Revised document with accuracy and clarity improvements | Markdown | `files/docs/` |
| Checklist | Review and maintenance checklist | Markdown | `files/templates/` |
| Explain | Accessible explanation of a complex topic | Markdown | `files/docs/` |
| Review | Quality and consistency report for a document | Markdown | `files/docs/` |

## Required tools & skills

No additional tools required. This playbook works entirely with Claude's built-in reading and writing capabilities.

## Useful references

- **Existing docs** — The current state of your documentation, used as a starting point for audits and rewrites.
- **Style guide** — Writing standards for documentation, including formatting rules, terminology, and structural conventions.
- **Information architecture** — The taxonomy, categories, and navigation structure that determines how documents are organized and found.

## Folder structure

```
files/
  docs/         # Active documentation — the current source of truth
  templates/    # Reusable document templates and structural patterns
  archive/      # Retired or superseded documents kept for reference
```
