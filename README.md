<!-- SEO: github-readme-optimizer – README audit, AI agent discoverability, LLM indexing optimization, README SEO, GitHub README rewrite -->

<div align="center">

# github-readme-optimizer

**Audit and rewrite GitHub README files so AI agents, LLMs, and humans can all find and understand your project.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-any%20AI%20agent-blue)](#install)
[![Works with](https://img.shields.io/badge/works%20with-Claude%20%7C%20Codex%20%7C%20Gemini%20%7C%20ChatGPT%20%7C%20OpenClaw-green)](#usage)

English | [简体中文](./README.zh-CN.md)

</div>

---

## Why github-readme-optimizer?

Most README files are invisible to AI agents — not because the project is bad, but because the README wasn't written for machine scanning.

| Problem | What this tool does |
|---------|---------------------|
| AI agent can't determine what your repo does in one scan | Rewrites the first 30 words to front-load all core keywords |
| LLMs index prose poorly | Converts walls of text into tables, FAQs, and structured sections |
| No one-liner install → no adoption | Generates a single copy-paste command |
| Missing FAQ → LLM retrieval fails | Adds collapsible `<details>` FAQ section optimized for Q&A extraction |
| No topics/badges → poor crawler metadata | Generates exact topics list and badge row to paste into GitHub |

> **TL;DR** — Give it a GitHub URL or local README path. It runs a 4-dimension audit, rewrites the README for AI discoverability + human appeal, and generates a Chinese version + GitHub action checklist.

---

## What It Does

### 🔍 4-Dimension Audit
Each dimension scored 0–10 with specific findings:

| Dimension | What's checked |
|-----------|---------------|
| **AI Agent Discoverability** | First-30-words keyword density, trigger phrases, SEO comment |
| **LLM Indexing Friendliness** | FAQ section, tables, badges, heading hierarchy, code blocks |
| **Human Attractiveness** | One-liner install, example output, visual hierarchy, tagline |
| **Structural Completeness** | Presence of Why / Features / Install / Usage / FAQ / License |

### ✏️ Full README Rewrite
Generates a complete optimized README following a proven template:
- SEO HTML comment at top
- Centered header with badges
- Problem → Solution table
- Feature groups with emoji headers
- Quick Start one-liner
- Example output block
- Use Cases section
- Collapsible FAQ (LLM-optimized)
- Memorable closing tagline

### 🌐 Chinese Version (README.zh-CN.md)
Full localization — not machine translation — with identical structure and translated SEO comment.

### ✅ GitHub Action Checklist
Exact copy-paste text for:
- Repository About description
- 10–15 recommended Topics
- Social preview image recommendation
- Releases recommendation

---

## Example Output

```
## 4-Dimension Audit

| Dimension              | Score | Top Finding                          |
|------------------------|-------|--------------------------------------|
| AI Discoverability     |  3/10 | First 30 words lack core keywords    |
| LLM Indexing           |  2/10 | No FAQ, no tables, no badges         |
| Human Attractiveness   |  4/10 | No example output or screenshot      |
| Structural Completeness|  3/10 | Missing Why, Use Cases, License      |

[Optimized README follows...]
```

---

## Install

**Option A — clone into your agent's skills folder (recommended)**

```bash
mkdir -p ~/.openclaw/skills
cd ~/.openclaw/skills
git clone https://github.com/gaoryan86/github-readme-optimizer github-readme-optimizer
```

**Option B — copy SKILL.md into any agent that reads skill files**

```bash
curl -O https://raw.githubusercontent.com/gaoryan86/github-readme-optimizer/main/SKILL.md
```

No dependencies. No config. Just a prompt/workflow definition in `SKILL.md`.

---

## Usage

Trigger phrases your agent will recognize:

- `optimize README for https://github.com/OWNER/REPO`
- `review readme` / `README SEO` / `readme audit`
- `让 AI 找得到：帮我优化这个项目的 README`
- `优化 README` / `review my GitHub repo`

Works with: **OpenClaw, Claude, Codex, Gemini, ChatGPT, and any agent that reads SKILL.md files.**

---

## Use Cases

- 🚀 You just shipped a side project and want it to surface in AI-assisted search
- 🤖 You want Claude / ChatGPT to correctly describe your repo when asked
- 📈 You're applying to HN / Product Hunt and need a README that reads in 10 seconds
- 🌏 You want a Chinese README without running everything through Google Translate
- 🔍 Your repo has stars but low clones — bad README UX is the bottleneck
- 📦 You maintain multiple repos and want a consistent README standard

---

## FAQ

<details>
<summary>Does this work on any GitHub repo?</summary>

Yes. Give it a GitHub URL and it fetches the README, repo description, topics, and file structure automatically. Or point it at a local README.md file.

</details>

<details>
<summary>Do I need OpenClaw to use this?</summary>

No. The workflow is defined in `SKILL.md` — a plain Markdown file. Any AI agent that reads skill/instruction files can follow it: Claude, Codex, Gemini, ChatGPT, etc.

</details>

<details>
<summary>Will it overwrite my existing README?</summary>

It generates the new README as output in chat — you decide whether to apply it. It won't touch your files without your explicit instruction.

</details>

<details>
<summary>Why a Chinese version?</summary>

A large share of open-source users and AI indexers operate in Chinese. A proper README.zh-CN.md doubles your discoverability surface with minimal extra effort.

</details>

<details>
<summary>How is this different from just asking ChatGPT to "improve my README"?</summary>

This runs a structured 4-dimension audit with specific scoring, follows a proven template optimized for LLM extraction (tables, FAQ, SEO comment), and outputs a GitHub action checklist. It's a repeatable workflow, not a one-shot rewrite.

</details>

---

## Contributing

PRs welcome. If you find an anti-pattern that should be caught, open an issue with a before/after example.

## License

MIT

---

<div align="center">

**github-readme-optimizer** — because a README no one can find is a README that doesn't exist.

</div>
