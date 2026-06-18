---
name: gb-doc-writer
description: GrowthBook documentation writer. Use when writing or editing GrowthBook docs pages (Docusaurus/MDX). Applies GrowthBook's house voice, formatting, and page-structure conventions.
author: csbailey5t
GH link: https://gist.github.com/csbailey5t/da412cd90502af84833aa1af2b0dd98b
---

# Documentation Writer

Use this skill when writing or editing documentation pages. Apply these conventions to all doc content you produce. Adapt project-specific details (imports, components, slug patterns) to the repo you're working in.

## Voice

- **Second person, active voice.** "You can query the data" not "The data can be queried."
- **First person plural for the product/team.** "We use ClickHouse..." / "We enrich and store them..."
- **Present tense.** Describe what the product *does*, not *will do*.
- **Confident.** "This reduces query costs" not "This may potentially help reduce."
- **Conversational but not casual.** Friendly and direct, not slangy. Avoid phrases like "probably your best bet."
- **Lead with the point.** Open paragraphs with the conclusion, then context.
- Short paragraphs (1-3 sentences). One idea each.

## Page skeleton

```mdx
---
title: Full Page Title
description: One SEO sentence, plain text
sidebar_label: Short Label
slug: /page-name
---

# Page Title

Opening 1-2 sentences: what this page covers and who it's for.

## Major section

Brief explanation (1-2 sentences) → details (list/table/prose) → code/screenshot → tip/note.
```

- One H1 per page. H2s form the TOC. H3/H4 for subsections. Never skip levels.
- **Title case for the page title only** (H1 and frontmatter `title`).
- **Sentence case for all section headings (H2-H4).** Capitalize only the first word and proper nouns. "How it works" not "How It Works." Product names and acronyms stay capitalized.

## Formatting rules

**Bold** for:
- Key terms on first use: "metrics built on **Fact Tables**"
- UI elements: **Settings** → **Data Sources**
- Definition-list labels: "- **event_name**: The name of the event"
- Benefit labels: "- **Fully managed**: No infrastructure management."

`Backticks` for: code identifiers, SQL, field names, config values, API paths, string literals.

**Lists:**
- Bullets for unordered items. Numbers for steps/sequences.
- Setup guides use numbered H2 steps: `## 1. Step title`

**Code blocks:** Always specify language (`js`, `sql`, `html`, `bash`). Include comments. Show minimal working example first. Use `YOUR_CLIENT_KEY` style placeholders. Include import statements.

**Images:** Use the project's image component if available. Always include alt text.

**Admonitions (Docusaurus):**
```
:::note      supplemental info, clarifications, edge cases
:::tip       shortcuts, recommendations
:::info      prerequisites, availability, context
:::warning   naming rules, deprecations
:::caution   security implications, destructive actions
```

**Links:** Root-relative paths. Descriptive text, never "click here." UI navigation paths use **bold** with `→`.

## Punctuation

- **No em-dashes (`—`).** Use a period, colon, or semicolon instead. Two short sentences beat one long sentence split by an em-dash.
- **Colons for definition-style lists.** `- **Identifiers**: used to split traffic.` Not `— used to split traffic.`
- **Hyphens** only for compound modifiers ("read-only access", "pre-built fact table").
- **Periods on list items** if they're full sentences. No period if they're fragments or labels.
- **`→`** only for UI navigation paths.

## Page type patterns

**Setup guide:** Opening sentence, then numbered H2 steps with screenshots, then troubleshooting section.

**Concept/reference:** Opening paragraph, then H2 per sub-concept with examples (code, SQL, scenarios), comparison tables, "What's next" links.

**Feature page:** Opening paragraph, then "Benefits" (bold-label bullets), "How it works" (numbered list), detailed reference, advanced config.

**Decision guide:** Question opener, decision tree with bold questions, comparison table, detailed section per option.

## Avoid

- Passive voice, hedging ("may potentially"), over-explaining the obvious.
- Em-dashes. Use periods, colons, or semicolons.
- "Please" more than once per page.
- "Simply" or "just" (the step may not be simple for all readers).
- Emoji in running text.
- Undefined acronyms.
- Starting with "It is..." or "There are..." when a direct construction exists.
- Making claims not supported by the code or existing docs.
