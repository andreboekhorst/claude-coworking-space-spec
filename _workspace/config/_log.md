---
name: log
description: Log completed skill sessions to a daily log file
trigger: Automatically invoked after any skill completes — not user-triggered
requirements: none
---

# Skill: Log Session

This skill runs at the end of every completed skill. It appends a structured entry to the daily log file.

---

# Log File

- **Location:** `/_workspace/logs/LOG_yyyy_mm_dd.md`
- **One file per day.** If the file already exists, **read it first**, then append.
- If the file does not exist, create it with the daily header.

---

# Daily Header (new files only)

```markdown
# Log — yyyy-mm-dd
```

---

# Entry Format

Each entry follows this exact structure. Do not deviate.

```markdown
## hh:mm — [Skill Name]

| Field        | Value                                  |
|--------------|----------------------------------------|
| **Skill**    | [skill name, e.g. setup / add-reference / add-skill] |
| **Trigger**  | [what the user said or did to start it] |
| **Duration** | [approximate: short / medium / long]   |

### What happened
- [1-3 bullet points summarizing what was done — factual, no fluff]

### Artifacts
- [files created or modified, with paths — or "none"]

### Open threads
- [anything unfinished, deferred, or flagged for follow-up — or "none"]
```

---

# Rules

- **Be factual.** Only log what actually happened. Never invent or embellish.
- **Be brief.** Each bullet should be one line. No paragraphs.
- **Use 24h time** in the entry header (e.g. `## 14:30 — Note-Taking`).

- **Artifacts must include full paths** relative to project root (e.g. `/_workspace/skills/some_file.md`).
- **Open threads** are for things the user explicitly deferred or that remain unresolved. Don't manufacture them.
- **Never log private content.** Summarize what was discussed at topic level, don't copy meeting content into the log.
- **Separate entries** with a blank line between them. Nothing else.

---

# After logging

Once the log entry is written, read and execute `_workspace/config/_reflect.md`. This reviews the session and may propose a workspace improvement. If it has nothing to suggest, it stays silent.
