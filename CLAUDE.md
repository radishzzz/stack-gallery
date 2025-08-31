# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Interactive image stack gallery showcasing advanced CSS transforms and JavaScript interactions. Built with modern web technologies focusing on performance optimization. Contains complete implementation steps from development process.

## Development Commands

```bash
pnpm dev      # Start development server
pnpm build    # Build for production
pnpm preview  # Preview production build
pnpm lint     # Check code quality
pnpm lint:fix # Fix linting issues
```

## Technology Stack

- **Astro**: Modern web framework
- **TypeScript**: Strict mode enabled
- **pnpm**: Package manager

## Project Structure

```
src/
├── layouts/          # Global layout with meta tags
├── pages/
│   ├── drafts/          # Development drafts (ignore)
│   ├── index.astro      # Main navigation hub
│   └── steps/          # Core implementation steps
│       ├── 1-single.astro    # Single image with 3D perspective
│       ├── 2-group.astro    # Stack layout with group expansion
│       ├── 3-scroll.astro    # Scrolling functionality
│       └── ...    # More steps to come
└── style/          # Reset CSS only
```

## Core Architecture

### Image Stack Implementation

- **3D Perspective**: `perspective()` and `rotateX/Y()` transforms
- **Responsive Design**: Dynamic viewport-based calculations
- **Performance**: CSS transforms, `will-change`, CSS containment
- **Caching**: Layout metrics cached to prevent redundant calculations

## Configuration

### TypeScript
- Strict mode enabled
- Path aliases: `@/*` → `src/*`
- Astro integration with type checking via `@astrojs/check`

### ESLint
- Uses @antfu/eslint-config
- Astro-specific rules enabled via `eslint-plugin-astro`
- Auto-fix available with `pnpm lint:fix`

## Engineering Practices

- **Modules**: ES modules with proper import/export
- **CSS**: Custom properties for dynamic styling
- **Performance**: Optimized image loading and CSS transforms

## Development Tools

### VS Code
- **Extensions**: Astro, TypeScript ESLint
- **Settings**: ESLint auto-fix on save
- **Debug**: Astro dev server configuration available
