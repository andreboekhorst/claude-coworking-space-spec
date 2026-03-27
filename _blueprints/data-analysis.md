---
name: data-analysis
type: playbook
description: Collect data, find patterns, and present insights that drive decisions.
parameters:
  - data_domain: What domain is the data from — sales, operations, user behavior?
  - key_question: What's the main question you're trying to answer?
references:
  - upload: The raw dataset or data dictionary
---

# Data Analysis (data_domain, key_question)

A workspace for turning raw data into clear insights. Covers the full arc
from data collection and cleaning through pattern recognition, visualization,
and narrative reporting.


## Follow-up question
What data are you working with, and what are you trying to find out?

## Core problems this workspace solves

- Data lives in scattered files and formats with no single source of truth.
- Analysis is ad hoc — one-off scripts, no repeatable process.
- Insights get buried in spreadsheets where nobody reads them.
- There is no storytelling around findings, so stakeholders miss the point.
- Past analyses are not documented, leading to duplicate work.


## Skill blueprints to use

- **Research** — Understand the domain and context before diving into data.
- **Synthesize** — Combine data from multiple sources and identify patterns.
- **Summarize** — Condense complex analysis into executive-level takeaways.
- **Explain** — Break down technical findings for non-technical audiences.
- **Draft** — Produce polished reports with narrative, charts, and recommendations.


## Skill outputs

| Skill | Output | Format | Folder |
|--------|--------|--------|--------|
| Research | Domain context and background summary | Markdown | `files/analysis/` |
| Synthesize | Combined data patterns and identified trends | Markdown | `files/analysis/` |
| Summarize | Executive-level takeaways | Markdown | `files/reports/` |
| Explain | Non-technical breakdown of findings | Markdown | `files/reports/` |
| Draft | Polished report with narrative and recommendations | Markdown | `files/reports/` |

## Required tools & skills

- **Bash** — Run data processing scripts, transformations, and quick calculations.


## Useful references

- Data dictionaries describing fields, types, and relationships.
- Analysis frameworks or methodologies relevant to your domain.
- Past reports or dashboards for consistency and comparison.
- Statistical reference guides for choosing the right methods.


## Folder structure

```
files/
  data/        # Raw and cleaned datasets — CSVs, exports, database dumps
  analysis/    # Scripts, notebooks, intermediate calculations
  reports/     # Final deliverables — written reports, chart exports, slide decks
```
