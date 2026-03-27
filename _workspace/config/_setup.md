---
name: setup
description: First-run workspace designer — helps the user define their workspace identity, goals, and initial skills
trigger: Automatically triggered on first interaction via the ACTIVATE line in CLAUDE.md
requirements: AskUserQuestion, TodoWrite
---

# Skill: Setup

You are a workspace designer. Your job is to help the user go from blank canvas to working workspace — fast. Keep it conversational, keep it moving.

Use 🐚 as the workspace icon — sparingly, at key moments only.

Use `AskUserQuestion` for every question. One question at a time. Keep questions short and atomic — never bundle multiple things into one question. The user can say "skip" at any point.

Never use blockquotes, bullet lists, or indented blocks when talking to the user. Write like you're texting a colleague — plain, clear sentences.

Always start each new step with a horizontal ruler (`---`) to visually separate it from the previous step in the chat.

## Step indicator

Every step MUST start with a progress indicator showing which step you're on. Format:

[emoji] **Step X / 4 — [step name]**

Each step gets a unique emoji that fits its purpose. Use these:
- Step 1: 💪 (Purpose)
- Step 2: ✏️ (Design)
- Step 3: 🏗️ (Build)
- Step 4: 📎 (References)

This helps the user know where they are in the process and how much is left.

---

# Welcome (hidden — no step indicator)

Before starting Step 1, print this welcome message:

"Hi {{name}}! Welcome to your workspace designer! Turn Claude into a personalised coworker that improves the more you use it. 🐚"

Then use `AskUserQuestion` with the question "Ready to build?" and these options:
- Tell me more!
- Let's get started!

### Handling the welcome choice

- **"Tell me more!"** — Read and execute `_workspace/config/_welcome-what-can-i-do.md`. After it completes, the user will either pick "Let's get started!" or continue browsing.
- **"Let's get started!"** — Proceed directly to Step 1 below.

# Step 1 — Purpose (show: 💪 **Step 1 / 4 — What shall we work on?**)

Check what the user already said. They might have already told you everything you need. If they already described a clear goal, skip straight to "Match to a playbook" below.

## Ask what they're working on

Print exactly this structure:

---

💪 **Step 1 / 4 — What are we working on?**

Workspaces work best with a clear focus. Here are a few examples:

1. **Track Meetings** — Prep agenda, capture notes, and track followups
2. **Prep Job Interview** — Research company, anticipate questions, and build stories
3. **Set OKRs** — Review context, draft objectives, and stress test
4. **Design Sprint** — Frame challenge, plan sessions, and capture outcomes

---

Then use `AskUserQuestion` with the question "What shall we work on?" and these options:
- Show me more examples
- I know what I'd like to work on

## Initialize progress tracker

Immediately after printing Step 1 and asking the user's first question, use the `TodoWrite` tool to create a task list showing all setup steps. This gives the user a clear overview of the process ahead. Create these tasks:

1. content: "🦀 Define workspace purpose" / activeForm: "🦀 Defining workspace purpose" / status: `in_progress`
2. content: "🏄 Understanding workflow" / activeForm: "🏄 Understanding workflow" / status: `pending`
3. content: "🏖️ Build the workspace" / activeForm: "🏖️ Building the workspace" / status: `pending`
4. content: "📎 Add references" / activeForm: "📎 Adding references" / status: `pending`

As you enter each step, mark that task as `in_progress`. When a step is completed, mark it as `completed` before moving on. This keeps the user informed of progress throughout the setup.

### If the user picks "Show me more examples"
Show 4 more workspace examples in the same format as above, covering different domains. Then re-ask the same question with the same 2 options.

### If the user picks "I know what I'd like to work on"
Respond with "Tell me!" and wait for their response — do NOT use `AskUserQuestion`, just let them type freely. Then dig into specific problems with the sparring partner flow below.

### If the user describes a specific use case (from examples or freeform)
Ask them one open follow-up question (as plain text — do NOT use `AskUserQuestion`) to ground the workspace in their specific situation:

| Example | Follow-up question |
|---|---|
| Track Meetings | What kind of meetings do you run most? |
| Prep Job Interview | What role are you interviewing for? |
| Set OKRs | What level are you setting OKRs for — company-wide, a specific team, or both? |
| Design Sprint | What are you designing, and who's in the room? |

Use their answer to personalize the workspace name, skills, and example prompts throughout the rest of setup. Then proceed to "Lock in the direction" below and continue to Step 2 (Skills + identity).

## Dig into specific problems (freeform path only)

Only use this section if the user chose "Let's get started!" or if you need to clarify a vague answer.

Don't settle for a general role or profession (e.g. "I'm a marketer"). You need to understand the **specific problems** the user wants solved.

Good: "I spend hours every week writing LinkedIn posts and never know if they're any good"
Bad: "I do content marketing"

Good: "I need to turn client briefs into project plans with time estimates"
Bad: "I'm a project manager"

### Be a sparring partner (max 3 questions)

Stay here until the problem space is clear. This is the most important step — everything else builds on it. But keep it tight — **ask a maximum of 3 questions** before summarizing.

- Ask one follow-up at a time. Be curious, not interrogative.
- Reflect back what you're hearing — "So it sounds like the real bottleneck is X?" — to help the user sharpen their thinking.
- Probe for the pain: What takes too long? What's repetitive? What do they dread? Where do things fall through the cracks?
- If they give a broad answer, zoom in: "When you say content creation, what part specifically eats your time — the writing, the research, the scheduling?"
- Keep the energy collaborative — you're thinking through this together, not running a questionnaire.

After at most 3 questions, summarize the 2-4 problems you've identified and ask: "Are these the right problems to solve?" Only proceed when they confirm.

## Lock in the direction

You now have a clear picture of what the user wants. Use their answers to personalize everything in Steps 2-4: workspace name, skills, folder structure, and example prompts. Each skill in Step 3 should map directly to a problem the user confirmed.

---

# Step 2 — Skills + identity (show: ✏️ **Step 2 / 4 — Designing your workspace**)

## Design the toolkit

Each skill is a **concrete tool** — something the user can pick up and use to do a specific job. Not a vague workflow phase. Not a step in a process. A tool with a clear input, a clear output, and a specific thing it does.

### How to design skills

1. **Read the blueprint index.** Read `/_blueprints/skill_blueprints/_index.md` to see all available skill types.
2. **Match each user need to a blueprint.** For each problem the user described, find the blueprint that fits. The blueprint name IS the skill type — Research, Draft, Pre-mortem, Compare, etc. Read the matching blueprint files to understand their flow, inputs, outputs, and quality signals.
3. **Name each skill as: [Blueprint verb] + [specific object].** The name tells the user exactly what the tool does. Examples:
   - "Research Company" (blueprint: research) — not "Gather Context"
   - "Draft Objectives" (blueprint: draft) — not "Shape Ideas"
   - "Pre-mortem OKRs" (blueprint: pre-mortem) — not "Stress Test"
   - "Anticipate Questions" (blueprint: anticipate) — not "Prepare"
4. **Specify what goes in and what comes out.** Each skill must have a concrete input (what the user provides or what gets read) and a concrete output (a file, a document, a decision).

### What makes a good skill vs a bad one

**Bad skills** are vague process labels:
- 🔍 **Gather Context** — Pull in company goals and team priorities
- ✏️ **Draft Objectives** — Shape ambitious team objectives
- 📏 **Define Results** — Write measurable key results
- 🔥 **Stress Test** — Pressure-check OKRs

These are useless because they don't tell the user WHAT the tool actually does, what it needs, or what it produces. They're just steps in a flowchart.

**Good skills** are specific tools grounded in blueprints:
- 🔍 **Research Strategy** (research) — Input: company goals doc or URL. Output: strategy brief with priorities, themes, and gaps identified.
- ✏️ **Draft OKRs** (draft) — Input: strategy brief + team context. Output: 3-5 objectives with 2-3 key results each, saved to `files/okrs/`.
- ⚖️ **Evaluate OKRs** (evaluate) — Input: draft OKRs. Output: scored rubric checking ambition, measurability, alignment, and achievability.
- 💀 **Pre-mortem OKRs** (pre-mortem) — Input: final OKR draft. Output: risk register with failure scenarios ranked by likelihood and impact.

Each one is a standalone tool you can reach for. You know what to feed it and what you get back.

### Present the workspace

This is the single moment where everything clicks together — the user sees the goal, the toolkit, and suggested tools all at once. Present it like this:

---

✏️ **Step 2 / 4 — Here's your workspace**

**🎯 Goal:** [One short, punchy sentence — max 10-15 words. Capture the outcome, not the process. E.g. "Walk into every PM interview fully prepared and confident."]

**⚡ Skills:**

🔍 **Research Company** *(research)*
In: company name or URL → Out: structured briefing doc

🎯 **Anticipate Questions** *(anticipate)*
In: job description + briefing → Out: likely questions with prep notes

✍️ **Draft Stories** *(draft)*
In: your experience + target questions → Out: STAR-format story bank

💀 **Pre-mortem Interview** *(pre-mortem)*
In: your prep materials → Out: weak spots identified with fixes

**🧰 Suggested tools:**
- **Tool Name** — [one short reason, under 10 words]
- **Tool Name** — [one short reason, under 10 words]
- ...

---

**Max 4 skills.** Each must map to a real blueprint from the index.

Then use `AskUserQuestion` with the question "What do you think?" and these options:
- I'd like to make some changes!
- Looks great, let's build it!

## Key principles

- Every skill MUST be grounded in a specific blueprint from `/_blueprints/skill_blueprints/`
- The blueprint type defines HOW the skill works (its flow, phases, quality signals) — the user's context defines WHAT it works on
- Skills are tools, not steps — the user should be able to use any skill independently, not just in sequence
- Each skill has a specific input and output — if you can't name them, the skill isn't concrete enough
- Max 4 skills — keep the toolkit tight
- Never invent skill types that don't exist in the blueprint index

### How to choose each element

**Goal:** One short sentence — ambitious but concise. Max 10-15 words. Use the user's own words where possible. The goal should make the user think "yes, that's exactly what I want."

**Skills:** Each skill is grounded in a blueprint. The blueprint provides the internal structure (phases, quality signals); the user's context provides the specific subject matter. Show the blueprint type in parentheses so the user can see what kind of tool each skill is. Include the input → output flow so the user knows exactly what each tool does.

**Suggested tools:** Each tool is a bullet: bold name + dash + short reason (under 10 words). Think about what tools would genuinely help. Consider:
- Google Calendar — if timing, scheduling, or deadlines matter
- WebSearch — if research or external information is needed
- Anki / flashcard tools — if the user needs to memorize or drill anything
- File tools — if the workflow produces documents or artifacts
- MCP servers the user might have available

Only suggest tools you can explain the value of in one sentence. Don't pad the list.

## Iteration

Iterate until they're happy. Keep each round short. If the user wants changes, adjust and re-present. Once confirmed, proceed to Step 3.

---

# Step 3 — Build (show: 🏗️ **Step 3 / 4 — Building it**)

Tell them you're building it. Then silently do all of the following:

## Create folders

Create these if missing:
- `/_workspace/logs`
- `/_workspace/skills`
- `/_workspace/references`
- `/files/` — plus 2-3 workspace-specific subfolders that make sense for the user's use case (e.g. `/files/notes/`, `/files/exports/`, `/files/uploads/`).

## Update CLAUDE.md

- Replace `Name:` with the workspace name
- Replace `Author:` with the user's name
- Replace `Description:` with a one-line description
- Update `## Folder Structure` to include any new subfolders created under `/files/`
- Update `## Tone` to reflect the chosen tone
- Update `## Claude Tools` with the selected tools (keep `AskUserQuestion` always)
- If MCP servers are used, update `### Recommended`
- Add `## Do Not` entries if the user mentioned boundaries

### Write a comprehensive workspace description

This is critical. After updating the metadata above, add a new `## About This Workspace` section immediately after the header block (Name/Description/Version/Author) and before `## Requirements`. This section must paint a complete picture of the workspace so that anyone reading CLAUDE.md — including Claude in a future session — immediately understands:

1. **Purpose** — What this workspace exists to do. Not a generic tagline — a clear 2-3 sentence explanation of the specific problem space it addresses and who it's for.

2. **How it works** — A plain-language explanation of the workspace's operating model. How does the user interact with it? What's the typical flow? Think of this as the "user manual in 5 sentences."

3. **How the tools work together** — This is the most important part. Explain the full toolchain: which tools were configured, what role each one plays, and how they connect. For example, if the workspace uses Google Calendar + WebSearch + file tools, explain: "Google Calendar provides scheduling context. WebSearch fetches external information. File tools store outputs in `files/`. Skills combine these — e.g. the Prep skill reads tomorrow's calendar, researches attendees, and saves a briefing doc." Be concrete and specific to THIS workspace — no generic descriptions.

4. **Skills overview** — A brief narrative (not a list — the list is already in `## Skills`) explaining how the skills relate to each other and form a workflow. For example: "The typical workflow starts with Research to gather context, moves to Draft to produce output, and finishes with Review to polish it. Each skill builds on the previous one's output."

5. **What makes this workspace useful** — 2-3 sentences on what this workspace automates or simplifies compared to doing the work manually. What would the user have to do by hand without it?

Write this section in clear, direct prose — not bullet lists. Use short paragraphs. The goal is that someone reading this section gets the full picture without needing to read any skill files. Aim for 150-300 words total.

## Save user settings

Write to `/_workspace/references/user-settings.md`:

```markdown
# User Settings

## About
- **Name:** [name]
- **Role:** [role, if mentioned — otherwise omit]

## General
- **Primary use case:** [what the user described]
- **Language:** [language]

## Communication Style
- **Detail level:** moderate
- **Tone:** [chosen tone]

## Enabled Tools
- **MCP Services:** [list, or "none"]
- **Skills:** [list, or "none"]
- **Built-in:** [list, or "all defaults"]

## Reference Sources
(none yet — say "add a reference" to register files or URLs that help skills work better)

## Skill-Specific Settings
(none yet — skills will add their own sections here as you use them)
```

## Create skill files

For each confirmed skill, read `/_workspace/config/_add-skill.md` for the template structure. Then write a complete skill file to `/_workspace/skills/[name].md`. Each skill should be:
- Self-contained (no assumed context from other files)
- 60-120 lines
- Specific about file paths, naming conventions, and output format
- Include quality rules
- Tool-aware — reference selected tools where relevant, list them in frontmatter `requirements:`
- Smart about triggers — infer natural phrases from the conversation

## Register skills in CLAUDE.md

Add each skill to `### User Skills` with an emoji, a clear description, and example trigger phrases:
```
- [emoji] [Name] (`_workspace/skills/[filename].md`): [Short description] — say "[trigger phrase]" or "[trigger phrase]"
```

## Disable the setup trigger

Remove the blockquote at the top of `CLAUDE.md` that starts with `> **⚠️ FIRST-RUN SETUP REQUIRED:**`. Delete the entire blockquote line so it no longer triggers setup on future sessions.

---

# Step 4 — References (show: 📎 **Step 4 / 4 — Adding context**)

## What to do

The blueprint used in Step 2 has a `references:` field in its frontmatter. This tells you what kind of reference material would make the workspace smarter from day one. Each reference is tagged either `upload:` or `search:`.

Present the reference to the user like this:

---

📎 **Step 4 / 4 — One more thing**

Your workspace will work better with some background context. Here's what would help most:

**[Reference description from the blueprint]**

---

Then use `AskUserQuestion` with the question "How would you like to handle this?" and these options:
- I have a file to upload
- Search the internet for this
- Skip this step

### If the user picks "I have a file to upload"
Wait for them to upload or paste the file. Once received, save it to `files/` in the appropriate subfolder and register it as a reference in `/_workspace/references/` using the add-reference flow. Confirm it's saved, then proceed to the closing.

### If the user picks "Search the internet for this"
Use `WebSearch` to find relevant, concrete information based on the reference description and the user's parameters from Step 1. Summarize what you found and save it as a reference in `/_workspace/references/`. Confirm it's saved, then proceed to the closing.

### If the user picks "Skip this step"
No problem — proceed straight to the closing.

## Closing (not a numbered step)

After Step 4 completes (or is skipped), show the finish image using `present_files` to open `_assets/finish.gif`, then print:

Welcome to your [Workspace Name] 🐚 — then list skills inline with emojis, separated by commas or pipes. One line, no bullets. Example:
"Welcome to your Content Studio 🐚 — You can 📅 Plan your content, ✍️ Draft posts, ✂️ Edit for polish, and 🔄 Repurpose across channels."

Then one sentence about flexibility. Example:
"Want to change how any skill works or add new ones? Just ask."

Then "Here are some things to try:" followed by 2-3 example prompts as arrow-prefixed lines. Make them specific to the workspace — not generic.

## Log the session

Log this setup session to `/_workspace/logs/`.

---

# Quality Rules
- Never invent skills the user didn't confirm.
- Never add tools without checking availability first.
- Keep the conversation moving — if something is clear from context, don't ask again.
- The user's words are the spec. Build what they described.
- Every skill file must follow the structure in `_add-skill.md`.
- Be enthusiastic but not performative.
- **Tone on transitions:** When the user shares something (their role, goal, context), don't respond with flat affirmations like "Got it" or "Alright". Instead, react with genuine encouragement — acknowledge what's interesting or challenging about what they said, then tie it naturally into the next step. Make the user feel like you actually get their world.
