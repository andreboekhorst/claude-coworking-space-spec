---
name: meeting-operations
type: playbook
description: Prep agendas, run meetings, and capture decisions so nothing falls through the cracks.
parameters:
  - meeting_types: What kinds of meetings do you run — standups, 1:1s, planning, all-hands?
  - cadence: How often — daily, weekly, biweekly?
references:
  - upload: Recent meeting notes or current agenda templates
---

# Meeting Operations (meeting_types, cadence)

A workspace for people who run meetings and need them to actually produce results. Covers the full lifecycle: preparation, facilitation support, and post-meeting follow-through.

## Follow-up question
What kind of meetings do you run most?

## Core problems this workspace solves

- Meetings start without a clear agenda, so participants show up unprepared and time is wasted on alignment.
- Decisions made during meetings are not captured in a durable format, leading to confusion about what was agreed.
- Action items are assigned verbally but never tracked, so follow-up falls apart within days.
- Too many meetings happen by default — no one evaluates whether a meeting is the right format for the discussion.
- Recurring meetings drift from their original purpose and accumulate stale agenda items.

## Skill blueprints to use

- **Prep** — Build a focused agenda before each meeting, including goals, time blocks, and pre-reads.
- **Debrief** — Immediately after a meeting, extract decisions, action items, and open questions into a structured note.
- **Checklist** — Create reusable pre-meeting and post-meeting checklists so nothing gets skipped.
- **Summarize** — Turn raw meeting notes into concise summaries for stakeholders who weren't present.
- **Decide** — Structure decision-making during meetings using clear criteria and options, so the group reaches closure.

## Skill outputs

| Skill | Output | Format | Folder |
|--------|--------|--------|--------|
| Prep | Meeting agenda with goals, time blocks, and pre-reads | Markdown | `files/agendas/` |
| Debrief | Decisions, action items, and open questions | Markdown | `files/notes/` |
| Checklist | Reusable pre- and post-meeting checklist | Markdown | `files/actions/` |
| Summarize | Concise meeting summary for stakeholders | Markdown | `files/notes/` |
| Decide | Decision record with options, criteria, and outcome | Markdown | `files/notes/` |

## Required tools & skills

- **Google Calendar** — For viewing upcoming meetings, checking scheduling conflicts, and linking agendas to calendar events.
- **File management** — Reading and writing markdown files for agendas, notes, and action tracking.

## Useful references

- Meeting agenda templates (standing meetings, one-offs, workshops)
- Recurring agenda formats for weekly syncs, retrospectives, and planning sessions
- Decision log templates
- Action item tracking formats
- Guidelines for deciding when a meeting is necessary vs. async communication

## Folder structure

```
files/
  agendas/       # Pre-meeting agendas and pre-read materials
  notes/         # Raw and processed meeting notes
  actions/       # Action item lists and follow-up tracking
```
