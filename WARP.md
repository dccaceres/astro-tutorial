# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is an Astro 5.x static site generator project using the "basics" starter template. It's a minimal setup designed for learning and experimentation with Astro's core features.

## Common Development Commands

### Development Server
```bash
npm run dev
```
Starts the development server at `http://localhost:4321` with hot module replacement.

### Build and Production
```bash
npm run build        # Build production site to ./dist/
npm run preview      # Preview production build locally
```

### Astro CLI
```bash
npm run astro --help                    # Show Astro CLI help
npm run astro add                       # Add integrations interactively
npm run astro add <integration>         # Add specific integration (e.g., tailwind, react)
npm run astro check                     # Run type checking
npm run astro sync                      # Generate TypeScript types
```

## Project Architecture

### Directory Structure
- `src/pages/` - File-based routing system. Each `.astro` file becomes a route
- `src/components/` - Reusable Astro components (`.astro` files)  
- `src/layouts/` - Layout components that wrap page content
- `src/assets/` - Static assets (images, fonts) processed by Vite
- `public/` - Static files served directly (favicon, robots.txt, etc.)
- `dist/` - Build output directory (generated, not committed)

### Core Files
- `astro.config.mjs` - Main Astro configuration file
- `tsconfig.json` - TypeScript configuration extending Astro's strict preset
- `.astro/types.d.ts` - Auto-generated TypeScript types (created after running dev/build)

### Component Architecture
- **Layout Pattern**: Uses a base `Layout.astro` component that provides the HTML document structure
- **Component-First**: Astro components (`.astro` files) support frontmatter for JavaScript/TypeScript logic and HTML-like templating
- **Scoped Styles**: Each component can include `<style>` blocks that are automatically scoped
- **Asset Import**: Images and other assets are imported as ES modules for optimization

## Development Notes

- Astro uses **file-based routing** - create `.astro` files in `src/pages/` to add new routes
- Components support **frontmatter** (between `---` fences) for server-side logic
- Built-in **TypeScript support** with strict configuration
- **Zero runtime JavaScript** by default - Astro renders to static HTML
- Use `astro add` to integrate with frameworks like React, Vue, Svelte, or add features like Tailwind CSS

## TypeScript

The project uses Astro's strict TypeScript configuration. Types are automatically generated in `.astro/types.d.ts` when you run development or build commands.

## Build System

- **Astro 5.x** as the static site generator
- **Vite** as the underlying build tool and dev server
- **ESbuild** for fast compilation and bundling
- Automatic **asset optimization** and **code splitting**
