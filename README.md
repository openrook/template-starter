# Openrook Starter Template

This is the official starter template for [Openrook](https://github.com/openrook/openrook).

## Quick Start

```bash
# 1. Configure your API key
cp .env.example .env
# Edit .env and add your ANTHROPIC_API_KEY

# 2. Start the bot
openrook start --cli-mode
```

## Project Structure

```
├── config.yml          # Bot configuration
├── .env.example        # Environment variables template
├── .env                # Your API keys (create from .env.example)
├── skills/             # Skill definitions
│   └── example/
│       └── SKILL.md    # Example greeting skill
├── memory/             # Conversation memory (auto-generated)
├── media/              # Uploaded files (auto-generated)
├── db/                 # SQLite database (auto-generated)
└── logs/               # Log files (auto-generated)
```

## Configuration

Edit `config.yml` to customize your bot:

```yaml
bot:
  name: "My Assistant"
  description: "AI Assistant powered by Openrook"

llm:
  provider: "anthropic"
  model: "claude-sonnet-4-20250514"

gateways:
  cli:
    enabled: true
  websocket:
    enabled: true
    port: 8765
  telegram:
    enabled: false
    token: "${TELEGRAM_BOT_TOKEN}"
```

## Creating Skills

Add new skills in the `skills/` directory. Each skill is a Markdown file with YAML frontmatter:

```markdown
---
name: my-skill
description: What this skill does
version: "1.0.0"
triggers:
  - keyword1
  - keyword2
tools: []
---

# My Skill

## Steps
1. First step
2. Second step

## Guidelines
- Be helpful
- Be concise
```

## Commands

```bash
openrook start              # Start API server
openrook start --cli-mode   # Start in CLI mode
openrook status             # Show status
openrook skills list        # List skills
openrook config             # Show configuration
```

## Learn More

- [Openrook Documentation](https://openrook.io/docs)
- [GitHub Repository](https://github.com/openrook/openrook)
- [Creating Skills](https://github.com/openrook/openrook/blob/main/docs/skills.md)
- [Creating Tools](https://github.com/openrook/openrook/blob/main/docs/tools.md)
