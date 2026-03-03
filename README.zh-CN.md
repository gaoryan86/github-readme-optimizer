<!-- SEO: github-readme-optimizer – README 审计，AI 智能体可发现性，LLM 索引优化，README SEO，GitHub README 重写 -->

<div align="center">

# github-readme-optimizer

**审计并重写 GitHub README，让 AI 智能体、LLM 和人类开发者都能找到并读懂你的项目。**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/平台-任意%20AI%20智能体-blue)](#安装)
[![Works with](https://img.shields.io/badge/适配-OpenClaw%20%7C%20Claude%20Code%20%7C%20Codex%20%7C%20Antigravity-green)](#使用方式)

[English](./README.md) | 简体中文

</div>

---

## 为什么需要 github-readme-optimizer？

大多数 README 对 AI 智能体几乎是"隐形"的——不是项目不好，而是 README 没有为机器扫描而写。

| 问题 | 本工具做什么 |
|------|-------------|
| AI 智能体无法一次扫描就判断你的 repo 是做什么的 | 重写前 30 个词，将所有核心关键词前置 |
| LLM 对大段散文索引效果差 | 将散文转换为表格、FAQ 和结构化 section |
| 没有一行安装命令 → 没有采用率 | 生成单行复制粘贴命令 |
| 没有 FAQ → LLM 检索失败 | 添加针对 Q&A 提取优化的可折叠 `<details>` FAQ |
| 没有 Topics/badges → 爬虫元数据缺失 | 生成可直接粘贴到 GitHub 的 Topics 列表和 badge 行 |

> **TL;DR** — 给它一个 GitHub URL 或本地 README 路径，它运行 4 维度审计、重写 README（兼顾 AI 可发现性和人类阅读体验），并生成中文版 + GitHub 操作清单。

---

## 功能介绍

### 🔍 4 维度审计
每个维度评分 0–10，并列出具体问题：

| 维度 | 检查内容 |
|------|---------|
| **AI 智能体可发现性** | 前 30 词关键词密度、触发短语、SEO 注释 |
| **LLM 索引友好度** | FAQ section、表格、badges、标题层级、代码块 |
| **人类吸引力** | 一行安装命令、示例输出、视觉层次、tagline |
| **结构完整性** | Why / Features / Install / Usage / FAQ / License 等必要 section |

### ✏️ 完整 README 重写
按照经过验证的模板生成完整优化后的 README：
- 顶部 SEO HTML 注释
- 居中 header + badges 行
- 问题 → 解决方案表格
- 带 emoji 的功能分组
- Quick Start 一行命令
- 示例输出代码块
- Use Cases section
- 可折叠 FAQ（LLM 优化）
- 令人印象深刻的结尾 tagline

### 🌐 中文版（README.zh-CN.md）
完整本地化——不是机器翻译——结构与英文版完全一致，SEO 注释同步翻译。

### ✅ GitHub 操作清单
提供精确的复制粘贴文字，包括：
- Repository About 描述
- 10–15 个推荐 Topics
- Social preview image 建议
- Releases 建议

---

## 示例输出

```
## 4 维度审计

| 维度                | 评分  | 主要问题                          |
|---------------------|-------|-----------------------------------|
| AI 可发现性         | 3/10  | 前 30 词缺少核心关键词            |
| LLM 索引友好度      | 2/10  | 无 FAQ、无表格、无 badges         |
| 人类吸引力          | 4/10  | 无示例输出或截图                  |
| 结构完整性          | 3/10  | 缺少 Why、Use Cases、License      |

[优化后的 README 随后输出...]
```

---

## 安装

**方式 A — clone 到智能体的 skills 文件夹（推荐）**

```bash
mkdir -p ~/.openclaw/skills
cd ~/.openclaw/skills
git clone https://github.com/gaoryan86/github-readme-optimizer github-readme-optimizer
```

**方式 B — 将 SKILL.md 复制到任何读取 skill 文件的智能体中**

```bash
curl -O https://raw.githubusercontent.com/gaoryan86/github-readme-optimizer/main/SKILL.md
```

无依赖，无需配置，仅一个 `SKILL.md` prompt/workflow 定义文件。

---

## 使用方式

智能体识别的触发短语：

- `optimize README for https://github.com/OWNER/REPO`
- `review readme` / `README SEO` / `readme audit`
- `让 AI 找得到：帮我优化这个项目的 README`
- `优化 README` / `review my GitHub repo`

适配：**OpenClaw、Claude Code、Codex、Antigravity 及任何读取 SKILL.md 文件的智能体。**

---

## 适用场景

- 🚀 刚发布了一个 side project，想让它出现在 AI 辅助搜索结果中
- 🤖 希望 Claude / ChatGPT 被问到时能正确描述你的 repo
- 📈 准备投 HN / Product Hunt，需要一个 10 秒内能读完的 README
- 🌏 想要中文 README，但不想用 Google 翻译对付了事
- 🔍 你的 repo 有 star 但 clone 少——README 体验差可能是瓶颈
- 📦 维护多个 repo，想统一 README 标准

---

## FAQ

<details>
<summary>支持任意 GitHub repo 吗？</summary>

支持。给它一个 GitHub URL，它会自动获取 README、repo 描述、Topics 和文件结构。也可以指向本地 README.md 文件。

</details>

<details>
<summary>必须用 OpenClaw 吗？</summary>

不需要。工作流定义在 `SKILL.md`——一个纯 Markdown 文件。任何能读取 skill/instruction 文件的 AI 智能体都可以使用：Claude、Codex、Gemini、ChatGPT 等。

</details>

<details>
<summary>会自动覆盖我的 README 吗？</summary>

不会。新 README 作为输出内容在对话中生成——由你决定是否应用。未经你明确指令，不会改动任何文件。

</details>

<details>
<summary>为什么要生成中文版？</summary>

大量开源用户和 AI 索引系统以中文为主。一个规范的 README.zh-CN.md 以极低的额外成本将你的可发现性覆盖面翻倍。

</details>

<details>
<summary>和直接让 ChatGPT「改进我的 README」有什么区别？</summary>

本工具运行结构化的 4 维度审计并给出具体评分，遵循针对 LLM 提取优化的成熟模板（表格、FAQ、SEO 注释），并输出 GitHub 操作清单。这是一套可重复的工作流，而非一次性重写。

</details>

---

## 贡献

欢迎 PR。如果发现应被捕捉到的反模式，请开 issue 并附上修改前后的对比示例。

## License

MIT

---

<div align="center">

**github-readme-optimizer** — 没人能找到的 README，等于不存在的 README。

</div>
