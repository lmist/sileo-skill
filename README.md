# sileo-skill

An [Agent Skill](https://agentskills.io) for installing and using [Sileo](https://sileo.aaryan.design) — toast notifications for React with SVG morphing and spring physics.

Works with any agent that supports the [Agent Skills](https://agentskills.io) format — Claude Code, Cursor, GitHub Copilot, Gemini CLI, OpenAI Codex, Goose, Roo Code, and [many more](https://agentskills.io/home).

## Install

Depends on your agent. Examples:

```bash
# Claude Code
claude skill install --from https://github.com/lmist/sileo-skill

# Cursor — add to .cursor/skills/

# Copilot — add to .github/skills/

# Or just clone into your project's skills directory
git clone https://github.com/lmist/sileo-skill .skills/sileo
```

## What it does

When you mention toasts, notifications, snackbars, or sileo by name, your agent loads this skill and knows how to:

- Install and set up Sileo in your React app
- Fire success/error/warning/info/action/promise toasts
- Customize styling, positioning, themes, and CSS variables
- Use the full Toaster and sileo API

## Structure

```
SKILL.md              <- install, setup, common usage (~80 lines, always loaded)
references/
├── api.md            <- full API reference (loaded on demand)
├── toaster.md        <- Toaster component props (loaded on demand)
└── styling.md        <- styling, dark theme, CSS variables (loaded on demand)
```

Uses progressive disclosure — only loads what's needed for the task at hand.

## License

MIT
