# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Stack Gallery is an Astro-based web application that demonstrates progressive implementation steps for a 3D interactive image stack gallery. The project focuses on creating visually appealing image stacking effects with smooth transitions and responsive design.

## Development Commands

### Core Commands
- `pnpm dev` - Start development server with TypeScript checking
- `pnpm build` - Build for production with TypeScript checking
- `pnpm preview` - Preview production build locally
- `pnpm lint` - Run ESLint to check code quality
- `pnpm lint:fix` - Run ESLint and automatically fix issues

## Technology Stack

- **Framework**: Astro 5.13.5 with client-side transitions
- **Language**: TypeScript with strict type checking
- **Styling**: CSS with custom properties and responsive design
- **Linting**: ESLint with @antfu/eslint-config
- **Package Manager**: pnpm 10.15.0

## Project Structure

## Project Structure

- `src/layouts/Layout.astro` - Main layout with ClientRouter
- `src/pages/index.astro` - Navigation hub
- `src/pages/steps/` - Core progressive implementations
- `src/pages/steps/1-single.astro` - Single 3D image
- `src/pages/steps/2-group.astro` - Multiple images with stack layout
- `src/pages/steps/3-scroll.astro` - Scrollable image stack
- `src/pages/drafts/` - Experimental features
- `src/style/reset.css` - CSS reset
- `public/` - 200 sample images (01.webp-200.webp)

## Key Architecture Patterns

### Image Stack Implementation
The main feature in `src/pages/steps/3-scroll.astro` implements:
- Responsive image sizing and scaling based on viewport width
- 3D perspective transforms with rotation and scaling
- Interactive click-to-zoom functionality
- Smooth CSS transitions with cubic-bezier easing
- Performance optimizations using `will-change` and `backface-visibility`

### Responsive Design System
- Mobile-first approach with breakpoints at 480px and 1600px
- Dynamic CSS custom properties for image dimensions and offsets
- Cached layout calculations for performance
- Viewport-based sizing constraints (max 80dvh)

### State Management
- Client-side JavaScript for interactivity
- Cached DOM queries and layout metrics
- Event-driven updates for resize and user interactions
- Astro's `astro:after-swap` event for page transition handling

## Code Conventions

- Use `@/*` path aliases for imports (configured in tsconfig.json)
- Follow Astro's component structure with frontmatter scripts
- Implement responsive designs with CSS custom properties
- Use TypeScript strict mode for type safety
- Apply performance optimizations for image-heavy interfaces
- Follow ESLint configuration for consistent code style
