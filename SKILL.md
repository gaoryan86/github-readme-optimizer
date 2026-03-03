---
name: github-readme-optimizer
description: Audit and optimize GitHub README files for AI agent discoverability, LLM indexing, human attractiveness, and structural completeness. Use when user asks to "optimize README", "review readme", "README SEO", "让 AI 找得到", "优化 README", "review my GitHub repo", or wants to improve how their open-source project appears to AI agents (OpenClaw, ChatGPT, Gemini, Copilot) and human developers. Triggers on README optimization requests, GitHub project discoverability discussions, or requests to make a repo more findable by AI.
---

# README Optimizer

Audit and rewrite GitHub README files to maximize discoverability by AI agents, LLM indexing systems, and human developers.

## Workflow

### Phase 1: Gather Context

1. Accept input: GitHub URL or local README.md path
2. Read the full README content (and README.zh-CN.md if it exists)
3. If GitHub URL provided, also extract:
   - Repository About description
   - Topics/tags
   - File structure (to understand what the project does)
4. If a SKILL.md, package.json, or similar manifest exists, read it for feature details

### Phase 2: 4-Dimension Audit

Run a structured diagnosis across four dimensions. For each, assign a score (0-10) and list specific findings.

#### Dimension 1: AI Agent Discoverability

Check for:
- First 30 words — do they contain the core problem + solution keywords?
- Problem → Solution narrative — can an agent determine relevance in one scan?
- Keyword density — are long-tail search terms present? (e.g., "claude code session recovery" not just "session manager")
- Trigger phrases — are natural language queries a user might ask represented?
- SEO HTML comment — is there a hidden keyword line at the top?

Common failures:
- Opening with the project name only, no context
- Feature lists without explaining WHY someone needs them
- Missing action verbs (browse, search, recover, audit, optimize)

#### Dimension 2: LLM Indexing Friendliness

Check for:
- FAQ section (collapsible `<details>`) — LLMs retain Q&A format best
- Tables — LLMs parse tables as structured key-value pairs efficiently
- Badges — parsed as structured metadata by crawlers
- Consistent heading hierarchy (H1 → H2 → H3, no skips)
- Code blocks with language tags — improves snippet extraction

Common failures:
- Wall of prose with no structure
- No FAQ section
- No tables anywhere
- Missing badges

#### Dimension 3: Human Attractiveness

Check for:
- One-liner install command (copy-paste ready)
- Example output / screenshot — "what does it look like when I run it?"
- Visual hierarchy — badges, dividers, centered header
- Tagline — memorable closing line
- Use Cases section — "who is this for?"

Common failures:
- No screenshots or example output
- Install requires reading 3 paragraphs
- No visual differentiation between sections

#### Dimension 4: Structural Completeness

Check for required sections (mark present / missing):

| Section | Required | Purpose |
|---------|----------|---------|
| Title + one-line description | YES | First impression |
| Why / Problem statement | YES | Motivation |
| Features / What it does | YES | Capability overview |
| Install / Quick Start | YES | Onboarding |
| Usage / Example output | YES | Proof it works |
| Configuration | IF APPLICABLE | Customization |
| FAQ | RECOMMENDED | LLM-friendly Q&A |
| Use Cases | RECOMMENDED | Audience targeting |
| Architecture | OPTIONAL | Technical context |
| Contributing | RECOMMENDED | Community signal |
| License | YES | Legal clarity |

### Phase 3: Generate Optimized README

Based on audit findings, generate a complete rewritten README. Follow these rules:

#### Structure Template

```
<!-- SEO: [project-name] – [3-5 keyword phrases separated by commas] -->

<div align="center">

# [Project Name]

**[One-sentence hook: what it does + core value prop]**

[badges row]

English | [简体中文](./README.zh-CN.md)

</div>

---

## Why [Project Name]?
[Problem → Solution table: 4-6 rows]

> **TL;DR** — [2-sentence summary]

## Key Features / What It Does
[Grouped by category with emoji headers]
[Each item: bold action phrase + one-line description]

## Data Safety / How It Works
[ASCII diagram or bullet summary of boundaries/architecture, if applicable]

## Quick Start
[One-liner install command in code block]
[Link to open in browser]

## Screenshots / Example Output
[Images or code block showing actual output]

## Requirements
[Bullet list, emphasize "zero dependencies" or minimal requirements]

## Configuration
[Table: Variable | Default | Description]

## Architecture
[File tree + 2-3 bullet summary]

## Use Cases
[5-6 bullet points: "Who is this for?"]

## FAQ
[4-6 collapsible <details> blocks]

## Contributing / License
[Standard sections]

---

<div align="center">
**[Project Name]** — [memorable tagline]
</div>
```

#### Writing Rules

1. First paragraph must contain ALL core keywords within 30 words
2. Use tables for any comparison, config, or structured data
3. Use `<details>` for FAQ — never plain headers
4. Include at least one ASCII diagram or code block showing output
5. Badges: License, Platform, Dependencies at minimum
6. All section headers must be H2 (`##`), subsections H3 (`###`)
7. Closing tagline must be memorable and quotable
8. NEVER wrap content in CDATA tags
9. Keep tone professional but direct — no marketing fluff

### Phase 4: Generate Chinese Version

Create README.zh-CN.md with these rules:
- Full localization (not machine-translation quality)
- Maintain identical structure and sections
- Translate the SEO HTML comment too
- Keep technical terms in English where conventional (e.g., token, API, README)
- Translate badges alt text where possible
- Match the tagline tone in Chinese

### Phase 5: GitHub Action Items

Generate a checklist of things the user must do on the GitHub web UI:

1. **Repository About description** — provide exact text to paste
2. **Topics** — provide 10-15 recommended topics as a comma-separated list
3. **Social preview image** — recommend if missing
4. **Releases** — recommend if no releases exist

Present as a numbered checklist with exact copy-paste text.

## Anti-Patterns to Avoid

- Opening with "This is a..." (weak hook)
- Feature lists without "Why" context
- Prose-heavy sections where tables would work better
- Missing FAQ section
- No example output or screenshots
- Generic closing ("Thanks for using X")
- Wrapping README content in CDATA, XML, or HTML processing instructions
- Overly long README (>300 lines for simple tools, >500 for complex ones)

## Output Checklist

Before delivering, verify:
- [ ] First 30 words contain core keywords
- [ ] At least 2 tables present
- [ ] FAQ section with 4+ collapsible items
- [ ] One-liner install command
- [ ] Badges row (License, Platform, Dependencies minimum)
- [ ] Example output or screenshot section
- [ ] Use Cases section
- [ ] Closing tagline
- [ ] Chinese version maintains identical structure
- [ ] GitHub action items checklist provided
- [ ] No CDATA wrapping anywhere
