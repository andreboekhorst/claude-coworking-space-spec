---
name: product-discovery
type: playbook
description: Research users, validate ideas, and write specs that are grounded in evidence.
parameters:
  - product_type: What kind of product — SaaS, mobile app, hardware, internal tool?
  - user_segment: Who are the target users?
references:
  - search: Competitor landscape and feature comparisons in the space
---

# Product Discovery (product_type, user_segment)

A workspace for teams and individuals who need to move from assumptions to validated product decisions. This playbook structures the messy front-end of product work — from raw user signals to clear, actionable specs.


## Follow-up question
What kind of product are you exploring?

## Core problems this workspace solves

- User needs are assumed rather than validated, leading to features nobody wants
- Ideas jump straight to build without supporting evidence or clear rationale
- Specs are vague, leaving engineers to guess at intent and edge cases
- Research lives in scattered docs, slides, and Slack threads — impossible to synthesize
- Decisions lack traceability: no one remembers why something was prioritized


## Skill blueprints to use

- **Research** — Capture and structure findings from user interviews, surveys, and analytics
- **Synthesize** — Turn raw research into patterns, themes, and actionable insights
- **Decide** — Frame decisions clearly, weigh options against evidence, and document outcomes
- **Draft** — Write specs, briefs, and proposals that are grounded in research
- **Compare** — Evaluate competing ideas, features, or approaches side by side


## Skill outputs

| Skill | Output | Format | Folder |
|--------|--------|--------|--------|
| Research | Structured findings from interviews, surveys, or analytics | Markdown | `files/research/` |
| Synthesize | Patterns and actionable insights across sources | Markdown | `files/insights/` |
| Decide | Decision record with options and evidence | Markdown | `files/insights/` |
| Draft | Product spec, brief, or proposal | Markdown | `files/specs/` |
| Compare | Side-by-side evaluation of ideas or features | Markdown | `files/insights/` |

## Required tools & skills

- **WebSearch** — Look up market context, competitor features, and industry benchmarks
- **Google Calendar** — Schedule and track user interviews and stakeholder syncs
- File reading and writing for managing research artifacts and spec documents


## Useful references

- User research reports, interview transcripts, and survey results
- Product strategy documents and vision statements
- Competitor analysis and feature comparisons
- Existing specs or PRDs for context on past decisions
- Analytics dashboards or exported usage data


## Folder structure

Suggested subfolders inside `files/`:

- `files/research/` — Interview notes, survey data, analytics exports
- `files/specs/` — Product specs, PRDs, feature briefs
- `files/insights/` — Synthesized findings, opportunity maps, decision logs
