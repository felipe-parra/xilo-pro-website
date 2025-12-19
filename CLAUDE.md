# CLAUDE.md - AI Assistant Guide for Xilo Pro Website

This document provides comprehensive guidance for AI assistants working with the Xilo Pro website codebase.

## Project Overview

**Project Name:** Xilo Pro Website
**Type:** Next.js Web Application
**Status:** In Development (Coming Soon page)
**Framework:** Next.js 13.5.4 with App Router
**Language:** TypeScript 5.2.2
**Styling:** Tailwind CSS 3.3.3

This is a modern Next.js application using the App Router architecture, bootstrapped with `create-next-app`. The project is currently in its initial stages with a placeholder landing page.

## Tech Stack

### Core Technologies
- **Next.js 13.5.4** - React framework with App Router
- **React 18.2.0** - UI library
- **TypeScript 5.2.2** - Type-safe JavaScript
- **Tailwind CSS 3.3.3** - Utility-first CSS framework

### Development Tools
- **ESLint** - Code linting with `next/core-web-vitals` config
- **PostCSS** - CSS processing with Autoprefixer
- **Inter Font** - Google Font optimization via `next/font`

### Package Manager
- Supports `npm`, `yarn`, or `pnpm`
- Lock files present: `package-lock.json` and `yarn.lock`

## Codebase Structure

```
xilo-pro-website/
├── app/                      # Next.js App Router directory
│   ├── layout.tsx           # Root layout component
│   ├── page.tsx             # Homepage (root route)
│   ├── globals.css          # Global styles with Tailwind
│   └── favicon.ico          # Site favicon
├── public/                   # Static assets
│   ├── next.svg             # Next.js logo
│   └── vercel.svg           # Vercel logo
├── .codesandbox/            # CodeSandbox configuration
├── .devcontainer/           # Development container config
├── next.config.js           # Next.js configuration
├── tailwind.config.js       # Tailwind CSS configuration
├── tsconfig.json            # TypeScript configuration
├── postcss.config.js        # PostCSS configuration
├── .eslintrc.json           # ESLint configuration
├── .gitignore               # Git ignore rules
├── package.json             # Project dependencies
└── README.md                # Project documentation
```

## Development Workflows

### Setup and Installation
```bash
# Install dependencies
npm install
# or
yarn install
```

### Development
```bash
# Start development server on http://localhost:3000
npm run dev
# or
yarn dev
```

The development server includes:
- Hot module replacement (HMR)
- Fast refresh for React components
- Auto-updating on file changes

### Building
```bash
# Create production build
npm run build

# Start production server
npm run start
```

### Linting
```bash
# Run ESLint
npm run lint
```

## Key Conventions

### File Naming
- **Components:** Use PascalCase with `.tsx` extension (e.g., `MyComponent.tsx`)
- **Pages:** Use lowercase with `.tsx` extension in `app/` directory
- **Styles:** Use lowercase with `.css` extension

### Code Style
- **TypeScript:** Strict mode enabled
- **Linting:** Follow `next/core-web-vitals` ESLint rules
- **Formatting:** Consistent casing enforced via `forceConsistentCasingInFileNames`

### Import Patterns
- Path alias `@/*` maps to project root (configured in `tsconfig.json`)
- Example: `import Component from '@/components/Component'`

### Styling Approach
- **Primary:** Tailwind CSS utility classes
- **Global Styles:** Defined in `app/globals.css`
- **Dark Mode:** CSS variables with `prefers-color-scheme` media query
- **Custom Colors:** RGB values via CSS custom properties

### Component Structure
- **Server Components:** Default in App Router (app directory)
- **Client Components:** Require `'use client'` directive when needed
- **Layout Pattern:** Root layout in `app/layout.tsx` wraps all pages

## TypeScript Configuration

### Compiler Options
- **Target:** ES5 for broad compatibility
- **Module:** ESNext with Node resolution
- **JSX:** Preserve (handled by Next.js)
- **Strict Mode:** Enabled
- **Path Mapping:** `@/*` → `./*`

### Type Checking
- `skipLibCheck: true` for faster compilation
- `strict: true` for maximum type safety
- `isolatedModules: true` for better tooling support

## Tailwind CSS Setup

### Content Paths
Tailwind scans these paths for class usage:
- `./pages/**/*.{js,ts,jsx,tsx,mdx}`
- `./components/**/*.{js,ts,jsx,tsx,mdx}`
- `./app/**/*.{js,ts,jsx,tsx,mdx}`

### Custom Theme Extensions
- `gradient-radial`: Radial gradient background
- `gradient-conic`: Conic gradient background

## Current Implementation Status

### Completed
- ✅ Next.js 13 App Router setup
- ✅ TypeScript configuration
- ✅ Tailwind CSS integration
- ✅ Basic layout and page structure
- ✅ Inter font optimization
- ✅ Dark mode CSS variables

### In Development
- 🚧 Homepage content (currently shows "Xilo Pro - soon...")
- 🚧 Full website features and pages

## AI Assistant Guidelines

### When Working on This Codebase

1. **Always Use TypeScript**
   - All React components should use `.tsx` extension
   - Define proper types for props and state
   - Avoid `any` types; use specific type definitions

2. **Follow Next.js 13 App Router Patterns**
   - Place pages in `app/` directory as `page.tsx`
   - Use `layout.tsx` for shared layouts
   - Leverage Server Components by default
   - Only add `'use client'` when necessary (interactivity, hooks, browser APIs)

3. **Styling Guidelines**
   - Prefer Tailwind utility classes over custom CSS
   - Use CSS variables from `globals.css` for theming
   - Maintain dark mode support using CSS custom properties
   - Keep responsive design in mind (mobile-first approach)

4. **Component Development**
   - Keep components small and focused
   - Use semantic HTML elements
   - Ensure accessibility (ARIA attributes where needed)
   - Optimize images using Next.js `Image` component

5. **File Organization**
   - Routes go in `app/` directory
   - Static assets in `public/` directory
   - Consider creating `components/` directory for shared components
   - Consider creating `lib/` or `utils/` for utility functions

6. **Code Quality**
   - Run `npm run lint` before committing
   - Ensure no TypeScript errors (`strict` mode is enabled)
   - Test builds with `npm run build` for production readiness

7. **Performance Considerations**
   - Utilize Next.js Image optimization
   - Implement code splitting where appropriate
   - Use Server Components to reduce client-side JavaScript
   - Consider implementing loading and error states

8. **Avoid These Patterns**
   - Don't disable TypeScript strict checks
   - Don't use inline styles (use Tailwind classes)
   - Don't import from `node_modules` directly without adding to `package.json`
   - Don't modify `next.config.js` without understanding implications

### Recommended Project Expansions

When adding new features, consider creating:
- `components/` - Reusable UI components
- `lib/` - Utility functions and helpers
- `types/` - Shared TypeScript type definitions
- `hooks/` - Custom React hooks
- `app/api/` - API routes
- `app/[dynamic]/` - Dynamic routes
- `constants/` - Application constants

### Git Workflow
- Branch name pattern: `claude/feature-description-XXXXX`
- Commit messages should be clear and descriptive
- Push to feature branches, not main/master
- Follow existing project structure and conventions

### Environment Variables
- Store sensitive data in `.env.local` (already in `.gitignore`)
- Document required environment variables
- Never commit `.env` files with secrets

## Deployment

### Recommended Platform
- **Vercel** - Optimized for Next.js (from creators of Next.js)
- Zero-config deployment for Next.js apps
- Automatic HTTPS and global CDN

### Build Verification
Before deploying:
```bash
npm run build  # Verify production build succeeds
npm run start  # Test production build locally
```

## Additional Resources

- [Next.js Documentation](https://nextjs.org/docs)
- [Next.js App Router Guide](https://nextjs.org/docs/app)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [TypeScript Documentation](https://www.typescriptlang.org/docs)
- [React Documentation](https://react.dev)

---

**Last Updated:** 2025-12-19
**AI Assistant:** Claude
**Purpose:** Comprehensive codebase guide for AI-assisted development
