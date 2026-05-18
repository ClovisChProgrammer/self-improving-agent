# Self-Improvement Agent

[![OpenCode](https://img.shields.io/badge/OpenCode-compatible-blue)](https://opencode.ai)

> 🌐 **Other languages:**
> [🇧🇷 Português](README_pt-BR.md) ·
> [🇪🇸 Español](README_es.md)

A self-improvement skill for **OpenCode** that maintains your assistant's identity, learns from every interaction, and extracts reusable knowledge — all while respecting your privacy.

---

## 📋 Description

This skill transforms your AI coding agent into a continuously improving assistant with:

- **A defined identity** — principles, behavior rules, and memory that persist across sessions
- **Automatic language detection** — responds in your language (pt-BR, en, es, etc.) from the very first message
- **Continuous learning** — logs technical corrections, user preferences, project context, and communication adaptations
- **Pattern detection** — identifies recurring issues and promotes them to permanent memory
- **Skill extraction** — converts valuable learnings into reusable OpenCode skills

---

## 🚀 Quick Start

### 1. Install

Clone the skill to your OpenCode skills directory:

```bash
git clone https://github.com/ClovisChProgrammer/self-improving-agent.git ~/.config/opencode/skills/self-improving-agent
```

### 2. Load

In any OpenCode session, use the `skill` tool:

```
skill("self-improvement")
```

### 3. Use

Just start talking. The agent will:

1. Read your identity files (SOUL.md, USER.md, etc.)
2. Detect your language from your first message
3. Respond and learn throughout the session
4. Save your language preference locally for future sessions

---

## 📁 Structure

```
~/.config/opencode/skills/self-improving-agent/
├── SKILL.md              # Main instructions (loaded via skill tool)
├── SOUL.md               # Assistant identity & principles
├── USER.md               # Public profile template (no personal data)
├── USER.local.md         # 🔒 Private profile (created locally, in .gitignore)
├── AGENTS.md             # Operational rules & workflow
├── IDENTITY.md           # Identity template (name, creature, vibe, emoji)
├── .learnings/           # 📝 Per-project learning logs
│   ├── LEARNINGS.md
│   ├── ERRORS.md
│   └── FEATURE_REQUESTS.md
├── scripts/
│   ├── extract-skill.ps1  # Skill extraction (Windows PowerShell)
│   └── extract-skill.sh   # Skill extraction (Unix)
├── references/
│   ├── opencode-integration.md
│   ├── hooks-setup.md
│   └── examples.md
├── assets/
│   ├── SKILL-TEMPLATE.md
│   ├── LEARNINGS.md
│   ├── ERRORS.md
│   └── FEATURE_REQUESTS.md
├── README.md              # 🇬🇧 This file
├── README_pt-BR.md        # 🇧🇷 Portuguese
└── README_es.md           # 🇪🇸 Spanish
```

---

## 🌍 Language Support

The skill detects your language **automatically** from your first message:

| Your message starts with... | Language detected |
|---------------------------|-------------------|
| "Olá", "oi", "bom dia" | 🇧🇷 **pt-BR** (Portuguese) |
| "Hello", "hi", "good morning" | 🇬🇧 **en** (English) |
| "Hola", "buenos días" | 🇪🇸 **es** (Spanish) |
| Other or ambiguous | 🇬🇧 **en** (default, will ask) |

**Once detected**, your preference is saved in `USER.local.md` (local only, never committed).

> Technical content (code, commands, logs) stays in English regardless of your language.

---

## 🧠 Features

| Feature | Description |
|---------|-------------|
| **🧠 Identity** | SOUL.md defines who you are; USER.md remembers who you're helping |
| **📝 Learning** | Log technical corrections, personal preferences, project context |
| **🔄 Patterns** | Track recurring issues and promote them to permanent memory |
| **📦 Extraction** | Convert valuable learnings into reusable skills via `scripts/extract-skill.ps1` |
| **🎯 Dual Mode** | Technical programming + conversational personal development |
| **🌐 Multi-language** | Auto-detects and responds in pt-BR, en, es, and more |
| **🔒 Privacy-first** | Personal data stays in `USER.local.md` (in `.gitignore`) |

---

## 🔄 How It Works — APR Methodology

Every interaction follows three steps:

1. **Aprender (Learn)** — Consult `.learnings/` and identity files before responding
2. **Praticar (Practice)** — Apply accumulated knowledge (technical + user context)
3. **Refinar (Refine)** — After the interaction, log new learnings

### Learning Entry Format

```
## [LRN-YYYYMMDD-XXX] category

**Area**: frontend | backend | user_preference | project_context | ...
**Priority**: low | medium | high | critical
**Status**: pending | resolved | promoted

### Summary | Details | Suggested Action
```

When a learning repeats (≥3 times, ≥2 tasks, 30-day window), it gets **promoted** to permanent memory (SOUL.md, USER.md, or AGENTS.md).

---

## 🔒 Privacy

**Your personal data never leaves your machine.**

| File | Content | Tracked by git? |
|------|---------|-----------------|
| `USER.md` | Public template (no real data) | ✅ Yes |
| `USER.local.md` | Your real name, credentials, preferences | ❌ **No** (in `.gitignore`) |
| `.learnings/` | Session logs and learnings | ❌ **No** (in `.gitignore`) |

### How it works

1. On first run, the agent detects your language and creates `USER.local.md`
2. You can fill in your profile (name, profession, preferences) — entirely optional
3. The file is protected by `.gitignore` and is never committed or pushed
4. Each project gets its own `.learnings/` directory (also in `.gitignore`)

---

## 🤝 Contributing

Contributions are welcome! Feel free to open issues or pull requests on [GitHub](https://github.com/ClovisChProgrammer/self-improving-agent).

---

## 📄 License

MIT

---

## Origin

Originally based on [pskoett/self-improving-agent](https://github.com/peterskoett/self-improving-agent), adapted from OpenClaw to OpenCode with expanded assistant identity, multi-language support, and privacy-first architecture.
