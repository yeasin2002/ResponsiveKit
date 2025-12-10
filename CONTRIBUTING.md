# Contributing

Thanks for your interest! Here's how to get started.

## Setup

```bash
git clone https://github.com/yeasin2002/ResponsiveKit.git
cd ResponsiveKit
pnpm install
pnpm dev
```

Load extension:
- Chrome: `chrome://extensions` → Load unpacked → `.output/chrome-mv3-dev`
- Firefox: `about:debugging` → Load Temporary Add-on → `.output/firefox-mv3-dev`

## Code Style

- TypeScript for all files
- Functional React components
- UnoCSS utility classes
- `cn()` for conditional classNames

```tsx
interface Props {
  title: string;
}

export function MyComponent({ title }: Props) {
  return <div className="p-4 rounded-lg">{title}</div>;
}
```

## Content Scripts

Use Shadow DOM for style isolation:

```tsx
const ui = await createShadowRootUi(ctx, {
  name: "my-ui",
  onMount: (container) => {
    const root = ReactDOM.createRoot(container);
    root.render(<Component />);
    return root;
  },
  onRemove: (root) => root?.unmount(),
});
```

## Before Submitting

```bash
pnpm compile    # Type check
pnpm check:fix  # Lint + format
```

Test in both Chrome and Firefox.

## Commits

Format: `type: description`

Types: `feat`, `fix`, `docs`, `refactor`, `chore`

```
feat: add keyboard shortcut
fix: breakpoint detection on resize
```

## Pull Requests

1. Create branch: `git checkout -b feat/my-feature`
2. Make changes and test
3. Commit with clear message
4. Push and open PR
5. Describe changes and link related issues

## Questions?

Open an issue with the `question` label.
