# Toaster Component

The viewport component that renders toasts. Add it once to your root layout.

```tsx
import { Toaster } from "sileo";
```

## Props

| Prop     | Type                  | Default     | Description                                                      |
| -------- | --------------------- | ----------- | ---------------------------------------------------------------- |
| children | ReactNode             | —           | App content to render alongside toasts                           |
| position | SileoPosition         | "top-right" | Default position for all toasts                                  |
| offset   | number \| string \| object | —      | Distance from viewport edges                                     |
| options  | Partial\<SileoOptions\> | —         | Default options merged into every toast                          |
| theme    | "light" \| "dark" \| "system" | "system" | Sets fill based on color scheme. "system" follows OS preference |

## Offset

Accepts a number, string, or per-side config:

```tsx
<Toaster offset={20} />

<Toaster offset={{ top: 20, right: 16 }} />
```

## Default Options

Set global defaults that apply to every toast:

```tsx
<Toaster
  options={{
    fill: "#171717",
    styles: { description: "text-white/75!" },
  }}
/>
```

## SileoPosition

```tsx
type SileoPosition =
  | "top-left"
  | "top-center"
  | "top-right"
  | "bottom-left"
  | "bottom-center"
  | "bottom-right";
```
