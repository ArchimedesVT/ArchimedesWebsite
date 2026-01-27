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

- **Header.svelte**: Sticky nav with responsive hamburger menu, uses `$page.url` for active state. Nav switches from hamburger to full menu at 900px.
- **Footer.svelte**: Multi-column footer with social links
- **Hero.svelte**: Reusable hero section accepting `title`, `subtitle`, `image`, `dark` props; supports slot content for CTA buttons
- **TeamCard.svelte**: Card for displaying design team info with props: `name`, `competition`, `description`, `members`, `duration`, `travel`, `link`, `linkText`

### Styling

- Tailwind CSS 4 with `@tailwindcss/forms` and `@tailwindcss/typography` plugins
- Global CSS variables in `src/lib/styles/global.css` for brand colors and design tokens
- Brand colors: `--archimedes-yellow` (#ffb800), `--archimedes-yellow-bright` (#ffd000), `--steel` (#192b2e), `--halogen-haze` (#fffcf2)
- Utility classes in global.css: `.section`, `.section--light`, `.section--dark`, `.container`, `.card`, `.btn`, `.btn--primary`, `.btn--outline`, `.overline`
- Responsive breakpoints: 768px (mobile layout), 900px (desktop nav)
- Scoped styles in components use BEM-like naming (e.g. `.nav__inner`, `.faq-item`)

### External Integrations

- **EmailJS**: Contact and sponsor forms submit via fetch POST to EmailJS API (credentials in client code)
- **Google Forms**: Apply page redirects to external Google Form
- No backend/database - all content is static

### Key Patterns

- SSR-safe code: Use `if (browser)` guards from `$app/environment` for browser-only logic
- Page data: Content arrays (officers, teams, FAQs) are hardcoded in page components
- mdsvex configured for Markdown-in-Svelte (`.svx` files)
- Forms use `preventDefault`, build `FormData`, and use `alert()` for user feedback

## Code Style

- Tabs for indentation, single quotes, no trailing commas, 100 char print width (see `.prettierrc`)
- Prettier plugins: `prettier-plugin-svelte`, `prettier-plugin-tailwindcss`
