# 🧠 Text to Mind Map

> Transform text, Markdown, or text files into beautiful mind map images.

[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.com/claude-code)
[![Cursor Skill](https://img.shields.io/badge/Cursor-Skill-blueviolet)](https://cursor.com)
[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-blueviolet)](https://openclaw.dev)

## ✨ Features

- 📝 **Multiple Input Formats** — Supports raw text, `.md`, and `.txt` files
- 🎨 **Auto Hierarchy** — Intelligently extracts and structures content into hierarchical mind maps
- 🖼️ **Image Export** — Generates high-quality JPG images (configurable resolution)
- 🔗 **Rich Content** — Supports bold, code, links, and LaTeX formulas
- ⚡ **Fast Conversion** — Simple 3-step pipeline: Text → Markdown → HTML → Image

## 📦 Installation

This project is a **Claude Code Skill** (and compatible with other AI coding agents). Follow the instructions below for your specific tool.

### Claude Code

```bash
git clone https://github.com/NewToolAI/mindflow.git

cp -r mindflow <project>/.claude/skills/mindflow
```

### Cursor

```bash
git clone https://github.com/NewToolAI/mindflow.git

cp -r mindflow <project>/.cursor/skills/mindflow
```

### OpenClaw

```
npx clawhub@latest install mindflow
```

### Prerequisites

- **Node.js** 18+ (for CLI-based installations)
- **Claude Code / Cursor / OpenClaw** installed
- **Dependencies:** `markmap-cli`, `markmap-lib`, `markmap-render`, `node-html-to-image`
- **Puppeteer** or **Playwright** (for screenshot generation, installed automatically)

### Verify Installation

After installation, restart your AI coding agent and ask:
> "Use the text-to-mindmap skill to convert this text into a mind map: [your content]"