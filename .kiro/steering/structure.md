# Project Structure

## Directory Organization

### `/app` (Custom Entrypoints Directory)

Contains all extension entry points. WXT automatically detects and processes files in this directory (configured via `entrypointsDir: "app"` in wxt.config.ts).

- `background.ts`: Background service worker using `defineBackground()` helper
- `content/`: Content scripts injected into web pages
  - `index.tsx`: Main content script entry point with Shadow DOM UI mounting
  - `dev-tool.tsx`: DevTool component showing responsive breakpoint indicator
- `popup/`: Popup UI shown when clicking the extension icon
  - `index.html`: HTML entry point
  - `main.tsx`: React app initialization with StrictMode
  - `App.tsx`: Main React component (WXT + React demo)

### `/components`

Reusable React components following shadcn/ui structure.

- `/ui`: shadcn/ui components (button, card, input, popover)
  - Components use UnoCSS classes and `class-variance-authority` for variants
  - Built on Radix UI primitives for accessibility

### `/lib`

Utility functions and shared logic.

- `utils.ts`: Contains `cn()` helper for merging className strings using `clsx` and `tailwind-merge`

### `/style`

Global styles and CSS variables.

- `global.css`: CSS custom properties for theming (background, foreground, primary, etc.) using OKLCH color space

### `/assets`

Static assets like images and SVGs used in the extension UI (e.g., `react.svg`).

### `/public`

Public assets that are copied directly to the build output.

- `/icon`: Extension icons in various sizes (16, 32, 48, 96, 128px)
- `wxt.svg`: WXT logo

### `/.wxt`

Auto-generated directory by WXT containing TypeScript definitions and build artifacts. Do not edit manually.

## Code Conventions

### Imports

- Use `@/` path alias for importing from project root (assets, components, lib)
- Use `/` for public directory assets (e.g., `/wxt.svg`)
- Import UnoCSS styles with `import "virtual:uno.css"`

### Extension APIs

- Use `browser` namespace for cross-browser extension APIs (provided by WXT)
- Use `defineBackground()` helper for background scripts
- Use `defineContentScript()` helper for content scripts
- Use `createShadowRootUi()` for isolated UI injection in content scripts

### React Components

- Functional components with hooks
- TypeScript interfaces for component props
- UnoCSS utility classes for styling (Tailwind-compatible syntax)
- Use `cn()` utility from `@/lib/utils` for conditional className merging

### Content Script UI Pattern

Content scripts use Shadow DOM for style isolation:
1. Define content script with `defineContentScript()`
2. Create Shadow Root UI with `createShadowRootUi()`
3. Mount React components using `ReactDOM.createRoot()`
4. Apply fixed positioning for overlay elements
