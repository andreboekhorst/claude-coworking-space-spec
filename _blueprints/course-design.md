---
name: course-design
type: playbook
description: Structure lessons, learning activities, and assessments into a coherent course.
parameters:
  - subject: What are you teaching?
  - learner_level: Who are the learners — beginners, intermediate, advanced?
references:
  - upload: Current syllabus, learning objectives, or existing course materials
---

# Course Design (subject, learner_level)

A workspace for building educational experiences — from defining learning
objectives through sequencing content, designing activities, and creating
assessments. Produces a complete, teachable course package.


## Follow-up question
What are you teaching, and to whom?

## Core problems this workspace solves

- Learning objectives are vague or missing, so lessons lack direction.
- Content is not sequenced well, leaving learners confused or overwhelmed.
- There is no meaningful assessment of understanding — just content delivery.
- Materials are scattered across docs, slides, and drives with no structure.
- Course iteration is hard because there is no single view of the full curriculum.


## Skill blueprints to use

- **Teach** — Structure explanations for clarity, building from simple to complex.
- **Plan** — Map the full course arc — modules, lessons, dependencies, timing.
- **Draft** — Write lesson content, instructions, and handouts.
- **Checklist** — Create rubrics, review criteria, and quality checks for materials.
- **Explain** — Break down difficult concepts into accessible, layered explanations.


## Skill outputs

| Skill | Output | Format | Folder |
|--------|--------|--------|--------|
| Teach | Structured explanation building from simple to complex | Markdown | `files/materials/` |
| Plan | Full course map with modules, lessons, and timing | Markdown | `files/curriculum/` |
| Draft | Lesson content, instructions, or handouts | Markdown | `files/materials/` |
| Checklist | Rubric or quality checklist for materials | Markdown | `files/assessments/` |
| Explain | Accessible breakdown of a difficult concept | Markdown | `files/materials/` |

## Required tools & skills

No additional tools required. This playbook runs entirely within Claude
using text-based curriculum design and content creation.


## Useful references

- Curriculum standards or competency frameworks for your subject area.
- Learner profiles — who they are, what they know, what they struggle with.
- Existing course materials, syllabi, or textbooks to build on or replace.
- Pedagogical frameworks (e.g., Bloom's taxonomy, backward design).


## Folder structure

```
files/
  curriculum/    # Course outlines, module maps, learning objectives
  materials/     # Lesson content, slides, handouts, activity instructions
  assessments/   # Quizzes, assignments, rubrics, answer keys
```
