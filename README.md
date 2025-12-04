# Breakpoint Indicator

A browser extension built with WXT + React + UnoCSS + shadcn/ui.

## Tech Stack

- **Framework**: [WXT](https://wxt.dev) - Browser extension framework
- **UI**: React 19 + [shadcn/ui](https://ui.shadcn.com)
- **Styling**: [UnoCSS](https://unocss.dev) with [unocss-preset-shadcn](https://github.com/unocss-community/unocss-preset-shadcn)

## Getting Started

```bash
# Install dependencies
pnpm install

# Development (Chrome)
pnpm dev

# Development (Firefox)
pnpm dev:firefox

# Build for production
pnpm build

# Package extension
pnpm zip
```

## Adding shadcn Components

```bash
pnpm dlx shadcn@latest add <component-name>
```

## Project Structure

```
├── app/              # WXT entrypoints (popup, content, background)
├── components/ui/    # shadcn/ui components
├── lib/              # Utilities (cn function)
├── style/            # Global CSS with theme variables
└── uno.config.ts     # UnoCSS configuration
```
