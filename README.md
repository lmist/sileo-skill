# sileo-skill

A [Claude Code](https://claude.ai/claude-code) skill for installing and using [Sileo](https://sileo.aaryan.design) — toast notifications for React with SVG morphing and spring physics.

## Install

```bash
claude skill install --from https://github.com/lmist/sileo-skill
```

## What it does

When you mention toasts, notifications, snackbars, or sileo by name, Claude loads this skill and knows how to:

- Install and set up Sileo in your React app
- Fire success/error/warning/info/action/promise toasts
- Customize styling, positioning, themes, and CSS variables
- Use the full Toaster and sileo API

## Structure

```
SKILL.md              ← install, setup, common usage (~80 lines, always loaded)
references/
├── api.md            ← full API reference (loaded on demand)
├── toaster.md        ← Toaster component props (loaded on demand)
└── styling.md        ← styling, dark theme, CSS variables (loaded on demand)
```

Uses progressive disclosure — only loads what's needed for the task at hand.

## License

MIT
