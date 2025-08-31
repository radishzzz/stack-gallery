# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an interactive image stack gallery project that showcases advanced CSS transforms and JavaScript interactions. The project includes every step and draft from the creation process for learning and research purposes. The project uses modern web technologies while focusing on performance optimization.

## Development Commands

```bash
pnpm dev      # Start development server
pnpm build    # Build for production
pnpm preview  # Preview production build
pnpm lint     # Check code quality
pnpm lint:fix # Fix linting issues
```

## Technology Stack

- **Astro**: Modern web framework for content-focused sites
- **TypeScript**: Strict mode enabled for type safety
- **pnpm**: Package manager

### Project Structure

```
src/
├── layouts/          # Global layout with base meta tags and Astro's client-side navigation
├── pages/
│   ├── drafts/          # All drafts from creation process, please ignore
│   ├── index.astro          # Main navigation hub with links to different steps or drafts
│   └── steps/          # All steps from creation process, the core of the project
│       ├── 1-single.astro          # Single image with 3D perspective and zoom
│       ├── 2-group.astro          # Add stack layout and group expansion effect to multiple images based on 1-single
│       │── 3-scroll.astro          # Add scrolling functionality based on 2-group
│       └── ...          # More steps to come
└── style/          # Only very simple reset.css is included
```

## Core Architecture

### Image Stack Implementation

The gallery uses sophisticated CSS transforms and JavaScript for image manipulation:

- **3D Perspective**: Images use `perspective()` and `rotateX/Y()` transforms
- **Responsive Scaling**: Dynamic size calculation based on viewport dimensions
- **Performance Optimizations**: `will-change`, `backface-visibility`, and CSS containment
- **Caching System**: Layout metrics are cached to prevent redundant calculations

### Responsive Design Strategy

The project use breakpoint-based responsive calculations:

- **Mobile (≤480px)**: Full viewport width, 0.5 scale factor
- **Desktop (480px-1600px)**: Linear interpolation between mobile and desktop values
- **Large (≥1600px)**: Fixed 800px max size, 0.33 scale factor

## Engineering Practices

### Code Standards

- **ESLint Configuration**: Uses @antfu/eslint-config
- **TypeScript**: TypeScript strict mode with path aliases (`@/*` maps to `src/*`)
- **Module System**: ES modules with proper import/export patterns
- **CSS Custom Properties**: Used for dynamic styling updates

### Performance optimization

- Images use CSS transforms and will-change for hardware acceleration
- Layout calculations are cached to prevent redundant computations
- Resize events are debounced to improve performance
- CSS containment is used to optimize rendering performance
