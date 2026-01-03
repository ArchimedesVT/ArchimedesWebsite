# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static marketing website for the Archimedes Society at Virginia Tech. Built with SvelteKit 2 and Svelte 5, deployed to Vercel.

## Commands

```bash
npm run dev          # Start Vite dev server
npm run build        # Production build (vite build + svelte-package)
npm run preview      # Preview production build
npm run check        # TypeScript type checking
npm run lint         # ESLint + Prettier check
npm run format       # Auto-format with Prettier
```

## Architecture

### Routing

- File-based routing in `src/routes/` - each folder with `+page.svelte` becomes a route
- `+layout.svelte` wraps all pages with Header and Footer components
- Pages: Home, About, Design Teams, Apply, FAQ, Sponsor, Contact

### Components (`src/lib/components/`)

- **Header.svelte**: Sticky nav with responsive hamburger menu, uses `$page.url` for active state
- **Footer.svelte**: Multi-column footer with social links
- **Hero.svelte**: Reusable hero section accepting `title`, `subtitle`, `image`, `dark` props
- **TeamCard.svelte**: Card for displaying design team info

### Styling

- Tailwind CSS 4 with `@tailwindcss/forms` and `@tailwindcss/typography` plugins
- Global CSS variables in `src/lib/styles/global.css` for brand colors and design tokens
- Brand colors: Archimedes yellow (#ffb800, #ffd000), steel, halogen-haze
- Responsive breakpoints at 768px and 900px

### External Integrations

- **EmailJS**: Contact and sponsor forms submit to EmailJS API (credentials in client code)
- **Google Forms**: Apply page redirects to external form
- No backend/database - all content is static

### Key Patterns

- SSR-safe code: Use `if (browser)` guards for browser-only logic (see Header.svelte)
- Page data: Content arrays (officers, teams, FAQs) are hardcoded in page components
- mdsvex configured for Markdown-in-Svelte (`.svx` files)
