# Product Overview

This is a browser extension built with WXT and React that provides a responsive design development tool. The extension helps developers monitor viewport information and responsive breakpoints in real-time while browsing.

## Features

### DevTool Content Script
A floating responsive breakpoint indicator injected into all web pages that displays:
- Current breakpoint (xs, sm, md, lg, xl, 2xl)
- Viewport dimensions (width × height)
- Screen resolution
- Device pixel ratio
- Orientation (portrait/landscape)
- Color scheme preference (light/dark)
- Touch capability detection

The tool appears as a fixed floating button in the bottom-right corner showing the current breakpoint. Clicking it opens a popover with detailed screen information.

### Popup Interface
A demo popup interface showcasing WXT + React integration with:
- Interactive counter example
- Links to WXT and React documentation
- Hot Module Reloading (HMR) support

### Background Script
Basic background service worker for extension lifecycle management.

## Technical Implementation

- **Shadow DOM Isolation**: Content script UI uses Shadow DOM to prevent style conflicts with host pages
- **Real-time Updates**: Screen info updates on window resize and color scheme changes
- **Responsive Design**: Uses Tailwind-compatible breakpoints (640, 768, 1024, 1280, 1536px)
- **Modern UI**: Built with shadcn/ui components (Popover) and UnoCSS styling
- **Cross-browser**: Supports both Chrome and Firefox browsers
