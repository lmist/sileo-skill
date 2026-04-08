# Styling & Customization

Sileo looks great out of the box. Here are the escape hatches when you need them.

## Fill Color

The `fill` prop sets the SVG background color. Default is `"#FFFFFF"`. Use a dark value for dark toasts — pair with light text via `styles`.

```tsx
// Dark accent badge only
sileo.success({ title: "Saved", fill: "#171717" });

// Full dark toast
sileo.success({
  title: "Saved",
  fill: "#171717",
  styles: {
    title: "text-white!",
    description: "text-white/75!",
    badge: "bg-white/10!",
    button: "bg-white/10! hover:bg-white/15!",
  },
});
```

## Style Overrides

The `styles` prop overrides classes on sub-elements. Use Tailwind's `!` modifier for specificity.

| Key         | Element                   | CSS Selector               |
| ----------- | ------------------------- | -------------------------- |
| title       | The heading text          | [data-sileo-title]         |
| description | The body/description area | [data-sileo-description]   |
| badge       | The icon badge circle     | [data-sileo-badge]         |
| button      | The action button         | [data-sileo-button]        |

## Custom Icons

Pass any React node as the `icon` prop to replace the default state icon:

```tsx
sileo.success({
  title: "Deployed",
  icon: <RocketIcon className="size-4" />,
});
```

## Custom Description (JSX)

The `description` prop accepts JSX for rich content:

```tsx
sileo.info({
  title: "Update available",
  description: (
    <div className="flex flex-col gap-1">
      <span>v2.0 is ready</span>
      <a href="/changelog" className="underline">View changelog</a>
    </div>
  ),
});
```

## Roundness

Control border radius with the `roundness` prop (default `16`). Lower = sharper, higher = rounder pill.

```tsx
<Toaster options={{ roundness: 12 }} />
```

> **Performance note:** Higher `roundness` increases the SVG blur radius for the gooey morph effect, which is more expensive to render. `16` is the recommended balance.

## Autopilot

Toasts auto-expand after a short delay and collapse before dismissing. Control with `autopilot`:

- `autopilot: false` — disable auto expand/collapse (hover to expand)
- `autopilot: { expand: 300, collapse: 500 }` — custom timing in ms

## Global Dark Theme

Apply a consistent dark theme app-wide via `Toaster` options:

```tsx
<Toaster
  position="top-right"
  options={{
    fill: "#171717",
    roundness: 16,
    styles: {
      title: "text-white!",
      description: "text-white/75!",
      badge: "bg-white/10!",
      button: "bg-white/10! hover:bg-white/15!",
    },
  }}
/>
```

## CSS Variables

Override these custom properties globally to change state colors, dimensions, or timing:

```css
:root {
  /* State colors (oklch) */
  --sileo-state-success: oklch(0.723 0.219 142.136);
  --sileo-state-loading: oklch(0.556 0 0);
  --sileo-state-error: oklch(0.637 0.237 25.331);
  --sileo-state-warning: oklch(0.795 0.184 86.047);
  --sileo-state-info: oklch(0.685 0.169 237.323);
  --sileo-state-action: oklch(0.623 0.214 259.815);

  /* Dimensions */
  --sileo-width: 350px;
  --sileo-height: 40px;

  /* Animation */
  --sileo-duration: 600ms;
}
```

Custom brand color example:

```css
:root {
  --sileo-state-success: oklch(0.7 0.2 200);
}
```
