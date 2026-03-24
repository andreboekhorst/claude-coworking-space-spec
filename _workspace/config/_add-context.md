---
name: add-context
description: Register files, URLs, or references as workspace context sources in preferences
trigger: User wants to register context sources (e.g. "use this as context", "remember this file", "add this source")
requirements: AskUserQuestion
---

# Workflow: Add Context

---

# Role

You are a context manager. Your job is to register files, URLs, or references that Claude should treat as background knowledge for this workspace. Context lives wherever it naturally belongs — files in the workspace folder, external URLs, or descriptions in preferences. There is no separate context folder.

---

# Before you begin

- Read `/_workspace/preferences/preferences.md` to see existing context sources.
- If the user points to a file, verify it exists.

---

# Phase 1 — Identify what the user wants to add

Determine the source type:

- **A file in the workspace** — The user points to a file already in the folder. Just register its path.
- **A file outside the workspace** — Ask if they want to copy it into the workspace root (or a subfolder) or just reference the external path.
- **A URL** — Register the URL as a context source.
- **Pasted text or a description** — Save it as a new file in the workspace root (propose a filename), then register that.
- **A PDF, image, or non-markdown file** — Convert to clean markdown, save as a new `.md` file alongside the original (or in workspace root), then register.

If it's unclear what they want to add, ask **one short question**:

> **What would you like to add?** (point me to a file, paste text, or drop a link)

---

# Phase 2 — Convert if needed

Only needed for non-text sources (PDFs, images, pasted text). If the source is already a readable file, skip to Phase 3.

Convert the source material into clean markdown:

- **Preserve structure.** Keep headings, lists, tables, and sections intact.
- **Preserve content.** Never summarize, paraphrase, or omit unless the user asks.
- **Clean up artifacts.** Remove OCR noise, page numbers, headers/footers — but keep all actual content.
- **Handle images/diagrams.** Describe them in `[Image: description]` placeholders.

Save the converted file and propose a location:

> **I'll save this as `[filename].md` — where should it go?**
> Default: workspace root. Or name a subfolder.

---

# Phase 3 — Register in preferences

Add the source to the `## Context Sources` section in `/_workspace/preferences/preferences.md`.

Each entry should have:
- **Path or URL** — relative path from workspace root, or full URL
- **Description** — one-line summary of what it is
- **Added** — date added

Format:
```markdown
## Context Sources
- `path/to/file.md` — Project charter and scope definition (added 2026-03-24)
- `https://example.com/api-docs` — API reference documentation (added 2026-03-24)
```

If the `## Context Sources` section doesn't exist yet, create it in preferences (before `## Workflow-Specific Preferences`).

---

# Phase 4 — Confirm

> **Added to workspace context:**
> - [source type emoji] `[path or URL]` — [description]
>
> Claude will now use this as background knowledge in future conversations.

---

# Quality Rules

- **Never invent.** Only register what the user actually provided.
- **Preserve language.** Keep documents in their original language.
- **No duplication.** Check existing context sources before adding.
- **Files belong where they make sense.** Don't force everything into a single folder — let the user's project structure guide placement.
- **Flag issues.** If parts are unreadable or ambiguous, mark them: `[?] unclear section`
