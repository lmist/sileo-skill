---
name: sileo
description: |
  Install and use Sileo, a toast notification component for React with SVG morphing
  and spring physics. Use this skill whenever the user wants to add toast notifications,
  snackbars, or alert popups to a React app — even if they don't say "sileo" by name.
  Also use when they mention "sileo" directly, want to customize toast styling, or
  need promise-based loading/success/error notification flows.
---

# Sileo

A tiny, opinionated toast component for React. SVG morphing, spring physics, beautiful by default.

## Install

```bash
npm install sileo
```

## Setup

Add `Toaster` to your root layout once. Call `sileo` from anywhere.

```tsx
import { sileo, Toaster } from "sileo";

export default function App() {
  return (
    <>
      <Toaster position="top-right" />
      <YourApp />
    </>
  );
}
```

## Basic Usage

```tsx
// Success
sileo.success({ title: "Saved!" });

// Error
sileo.error({ title: "Something went wrong" });

// Warning
sileo.warning({ title: "Check your input" });

// Info
sileo.info({ title: "New version available" });
```

All methods return a toast `id` string you can use to dismiss later.

## Action Toast

```tsx
sileo.action({
  title: "File deleted",
  button: { title: "Undo", onClick: () => restoreFile() },
});
```

## Promise Toast

Chain loading, success, and error states from a single promise:

```tsx
sileo.promise(saveData(), {
  loading: { title: "Saving..." },
  success: (data) => ({ title: `Saved ${data.name}` }),
  error: (err) => ({ title: "Failed", description: err.message }),
});
```

Returns the original promise so you can chain further.

## Positions

Six positions available: `top-left`, `top-center`, `top-right`, `bottom-left`, `bottom-center`, `bottom-right`.

Set default on `Toaster`, override per-toast:

```tsx
<Toaster position="top-right" />

sileo.success({ title: "Done", position: "bottom-center" });
```

## Dismissing

```tsx
const id = sileo.success({ title: "Hello" });
sileo.dismiss(id);    // dismiss one
sileo.clear();        // clear all
sileo.clear("top-right"); // clear by position
```

## What's Next

Sileo works beautifully out of the box. When you need to go deeper:

- **Full API reference** (all methods, option types, interfaces): Read `references/api.md`
- **Toaster component props** (offset, theme, default options): Read `references/toaster.md`
- **Styling & customization** (fill colors, dark theme, CSS variables, autopilot, custom icons): Read `references/styling.md`
