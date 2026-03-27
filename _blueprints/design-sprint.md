---
name: design-sprint
type: playbook
description: Frame problems, generate ideas, and test concepts before building.
parameters:
  - design_challenge: What problem are you trying to solve?
  - timeline: How long is the sprint — a day, a week, something else?
references:
  - search: Existing solutions and competitor approaches to the challenge
---

# Design Sprint (design_challenge, timeline)

A workspace for structured creative problem-solving. Moves a team from
vague problem space to tested concepts through disciplined framing,
divergent ideation, and rapid validation.


## Follow-up question
What are you designing, and who's in the room?

## Core problems this workspace solves

- Teams jump to solutions before properly understanding the problem.
- Ideas are not tested or validated before committing resources to build them.
- There is no structured ideation process, so the loudest voice wins.
- Stakeholder alignment is missing, causing late-stage surprises and rework.
- Design decisions are not documented, making it hard to explain rationale later.


## Skill blueprints to use

- **Research** — Gather user insights, competitive landscape, and constraints.
- **Brainstorm** — Generate diverse ideas using structured divergent thinking.
- **Decide** — Evaluate options against criteria and converge on a direction.
- **Pre-mortem** — Identify risks and failure modes before committing to a path.
- **Draft** — Document concepts, decisions, and next steps for handoff.


## Skill outputs

| Skill | Output | Format | Folder |
|--------|--------|--------|--------|
| Research | User insights and constraints summary | Markdown | `files/research/` |
| Brainstorm | Clustered ideas with evaluation notes | Markdown | `files/concepts/` |
| Decide | Evaluation matrix and selected direction | Markdown | `files/concepts/` |
| Pre-mortem | Risk analysis with mitigation strategies | Markdown | `files/concepts/` |
| Draft | Concept document and next steps for handoff | Markdown | `files/prototypes/` |

## Required tools & skills

No additional tools required. This playbook runs entirely within Claude
using text-based ideation, evaluation, and documentation.


## Useful references

- User research findings — interviews, surveys, behavioral data.
- Design principles or heuristics your team follows.
- Competitive examples and analogous solutions from other domains.
- Technical constraints or platform guidelines that bound the solution space.


## Folder structure

```
files/
  research/     # User insights, competitive analysis, problem framing docs
  concepts/     # Ideas, sketches, concept descriptions, evaluation matrices
  prototypes/   # Refined concepts, wireframes, test plans, feedback logs
```
