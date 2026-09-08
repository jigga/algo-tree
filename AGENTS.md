# Repository Guidelines

AlgoTree is a web-app MVP built with Astro, React, Supabase, and Cloudflare Pages.

## Core Directives
- Prefer standard Astro features (`.astro` files) for routing and static content.
- Use React (`.tsx`) strictly for complex interactive components, placed in `src/components/`.
- Authentication uses Supabase SSR; read sessions using `supabase.auth.getSession()` exclusively in Astro server endpoints or `middleware.ts`.
- Avoid `any`. Types must pass `npm run lint` before committing.

## Project Structure & Module Organization
- `@src/pages/`: Astro file-based routing.
- `@src/components/`: Reusable UI elements (`.astro` or `.tsx`).
- `@src/layouts/`: Astro page wrapper layouts.
- `@src/lib/`: Shared utilities, types, and the Supabase client (`@src/lib/supabase.ts`).
- `@supabase/`: Supabase configuration and migration files.
- `@context/foundation/`: Product documentation (PRD, Tech Stack).

## Build, Test, and Development Commands
- Reference `@package.json` for all standard build, lint, format, and dev commands.

## Coding Style & Naming Conventions
- Component files should be `PascalCase` (`Banner.astro`, `SignInForm.tsx`).
- Utility files and API routes should be `kebab-case` (`middleware.ts`).
- Follow the formatting rules configured in `@eslint.config.js` and `@.prettierrc.json`.

## Security & Configuration Tips
- Environment variables are strictly managed through Astro's `env` schema in `@astro.config.mjs` (e.g., `SUPABASE_URL`, `SUPABASE_KEY`).
- Do not hardcode secrets or commit the `.env` file. Rely on `@.env.example` as a template for local development.
- The repository relies on `lint-staged` and Husky to automatically run linting and formatting on pre-commit.

## Commit & Pull Request Guidelines
- Use Conventional Commits formatting (e.g., `feat:`, `fix:`, `chore:`).
- `master` is the primary branch.
- CI workflows (`@.github/workflows/ci.yml`) enforce `npm run lint` and `npm run build`. Ensure both pass locally before pushing.
