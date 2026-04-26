# AGENTS.md

## Stack / Deploy Target

- Astro site (Astro v6) with Tailwind v4 via `@tailwindcss/vite`.
- `@astrojs/react` is installed and enabled in `astro.config.mjs`, but the current site is built with `.astro` components.
- Deployment target is Cloudflare Pages using static output.
- Pages configuration lives in `wrangler.jsonc` with `pages_build_output_dir: "./dist"`.

## Commands

- Install dependencies: `npm ci`
- Start local dev server: `npm run dev`
- Run Astro checks: `npm run astro -- check`
- Build production output: `npm run build`
- Preview the built site locally: `npm run preview`

## Project Entry Points

- Main route: `src/pages/index.astro`
- Main layout: `src/layout/MainLayout.astro`
- Global Tailwind directives: `src/styles/global.css`
- Static assets: `public/`

## Current Page Composition

- `src/pages/index.astro` composes the landing page from:
- `src/components/common/Navbar.astro`
- `src/components/Hero.astro`
- `src/components/Services.astro`
- `src/components/Features.astro`
- `src/components/Data.astro`
- `src/components/FAQ.astro`
- `src/components/QuoteForm.astro`
- `src/components/common/Footer.astro`

## Styling Conventions

- Most visual styling is defined in component-local `<style>` blocks.
- Shared design tokens and global resets live in `MainLayout.astro`.
- The current brand palette uses CSS variables such as `--brand-navy`, `--brand-blue`, `--brand-red`, `--brand-sand`, and related surface, border, and shadow tokens.
- Typography is loaded from Google Fonts in `MainLayout.astro` and currently uses `Sora` plus `Barlow Condensed`.
- `src/styles/global.css` should remain imported by `MainLayout.astro` because it wires Tailwind into the app.

## Cloudflare Notes

- This repo is configured for Cloudflare Pages, not a Cloudflare Worker entrypoint.
- `wrangler.jsonc` is used for Pages metadata only; the production output that matters is `dist/`.
- Do not commit `.wrangler/` artifacts. They are local/generated files and are ignored by `.gitignore`.

## Repo Hygiene

- Scope searches to `src/` or exclude `node_modules/` for faster, cleaner results.
- `dist/` is generated build output and should not be edited manually.
