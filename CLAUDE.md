# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Stack Gallery is an interactive image gallery application featuring 3D stack effects, built with Astro and TypeScript. It showcases multiple gallery demos including single image displays, grouped image stacks, and advanced archive views with momentum scrolling.

## Development Commands

```bash
# Development server with type checking
pnpm dev

# Production build with type checking
pnpm build

# Preview production build
pnpm preview

# Run ESLint
pnpm lint

# Run ESLint with auto-fix
pnpm lint:fix
```

## Architecture & Technologies

### Core Stack
- **Astro 5.13.4**: Modern web framework for content-focused sites
- **TypeScript**: Strict mode enabled for type safety
- **pnpm**: Package manager

### Key Features
- 3D perspective transformations and image stacking
- Momentum-based scrolling with touch support
- Responsive design with adaptive sizing
- Interactive zoom and navigation controls
- Performance optimizations (CSS containment, will-change)

### Page Structure
- `src/pages/index.astro`: Main navigation hub
- `src/pages/steps/1-single.astro`: Single image 3D demo
- `src/pages/steps/2-group.astro`: Multiple image stack layout
- `src/pages/steps/x-loading.astro`: Loading animation states
- `src/pages/archive.astro`: Advanced gallery with toggle/scroll

## Development Setup

### Prerequisites
- Node.js (version matching TypeScript ~5.9.2)
- pnpm package manager

### Initial Setup
```bash
pnpm install
```

### Code Quality
- ESLint with @antfu/eslint-config configuration
- TypeScript strict mode
- Auto-fix on save in VS Code
- No formal testing framework currently implemented

## Key Technical Details

### Assets
- 50+ WebP images in `/public/` directory (01.webp, 02.webp, etc.)
- Images referenced throughout gallery demos

### CSS Architecture
- Custom properties for dynamic values
- Complex 3D transforms with perspective
- Cubic-bezier easing for smooth animations
- Responsive sizing with calc() and clamp() functions

### JavaScript/TypeScript Patterns
- State management for gallery interactions
- Momentum scrolling algorithms
- Touch event handling for mobile devices
- RequestAnimationFrame for smooth animations
- Platform detection (MacOS vs others)

### Build Configuration
- Site URL: https://stack-gallery.vercel.app
- Trailing slash always enabled
- Client router enabled for page transitions
- Static site generation (no SSR requirements)

## VS Code Configuration

The project includes VS Code workspace settings for:
- ESLint integration with auto-fix on save
- Recommended extensions (ESLint, Astro)
- TypeScript workspace version enforcement

## Deployment

Built as a static site that can be deployed to any static hosting platform. Currently configured for Vercel deployment.
