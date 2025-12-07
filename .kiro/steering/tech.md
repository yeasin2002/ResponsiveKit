# Technology Stack

## Core Technologies

- **WXT**: Browser extension framework (v0.20.6)
- **React**: UI library (v19.1.1)
- **TypeScript**: Type-safe JavaScript (v5.9.2)
- **pnpm**: Package manager

## Styling & UI

- **UnoCSS**: Atomic CSS engine with Tailwind-compatible utilities (v66.5.10)
  - Uses `@unocss/preset-wind3` for Tailwind v3 compatibility
  - `unocss-preset-shadcn` for shadcn/ui component styling
  - `unocss-preset-animations` for animation utilities
- **shadcn/ui**: Component library (New York style)
  - Radix UI primitives (@radix-ui/react-popover, @radix-ui/react-slot)
  - Configured with neutral color scheme
  - Components use `class-variance-authority` for variant management
- **tw-animate-css**: Animation utilities
- **Utility Functions**: `clsx` and `tailwind-merge` for className management

## Build System

WXT is the build system that handles bundling, hot module reloading, and browser-specific builds. Configured with:
- `@wxt-dev/module-react`: React integration module
- `@wxt-dev/unocss`: UnoCSS integration module
- Custom entrypoints directory: `app/`

## Common Commands

### Development

```bash
pnpm dev              # Start development server (Chrome)
pnpm dev:firefox      # Start development server (Firefox)
```

### Building

```bash
pnpm build            # Build for production (Chrome)
pnpm build:firefox    # Build for production (Firefox)
pnpm zip              # Create distributable zip (Chrome)
pnpm zip:firefox      # Create distributable zip (Firefox)
```

### Type Checking

```bash
pnpm compile          # Run TypeScript type checking without emitting files
```

### Setup

```bash
pnpm install          # Install dependencies (runs wxt prepare automatically)
```

## Configuration Files

- `wxt.config.ts`: WXT configuration with React and UnoCSS modules, custom entrypoints directory
- `tsconfig.json`: Extends WXT's generated TypeScript config with React JSX support and `@/*` path alias
- `uno.config.ts`: UnoCSS configuration with Wind, Animations, and Shadcn presets
- `components.json`: shadcn/ui CLI configuration (New York style, neutral theme)
- `tailwind.config.js`: Empty file for shadcn CLI compatibility (actual styling via UnoCSS)
- TypeScript uses `react-jsx` transform for modern JSX handling
