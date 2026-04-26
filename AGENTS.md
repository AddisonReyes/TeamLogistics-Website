# AGENTS.md

## Stack / Deploy Target

- Astro site (Astro v6) with Tailwind (Tailwind v4 via `@tailwindcss/vite`) and optional React (`@astrojs/react` integration is enabled).
- Cloudflare deployment: `@astrojs/cloudflare` adapter is configured in `astro.config.mjs`.
- Cloudflare Worker entrypoint after build is `dist/_worker.js/index.js` (see `wrangler.jsonc`). Build before any `wrangler`-based deploy/dev.

## Commands (Repo Uses npm + package-lock)

- Install: `npm ci` (preferred because `package-lock.json` is present).
- Dev server: `npm run dev` (Astro dev, default `http://localhost:4321`).
- Typecheck/config check: `npm run astro -- check`.
- Production build: `npm run build` (outputs `dist/`).
- Preview build locally: `npm run preview` (use this when debugging Cloudflare adapter behavior).

## Project Entry Points

- Routes live in `src/pages/`.
- Main page composition is `src/pages/index.astro`.
- Global CSS is wired via `src/layout/MainLayout.astro` importing `src/styles/global.css`.

## Styling Conventions / Gotchas

- Tailwind is available, but most styling is component-local `<style>` blocks plus CSS variables defined in `MainLayout.astro` (`--brand-*`, `--blue`, `--red`, etc.).
- `src/styles/global.css` only contains Tailwind directives; don’t delete the import in `MainLayout.astro` unless you intend to remove Tailwind.

## Cloudflare Notes

- `public/.assetsignore` excludes `_worker.js` and `_routes.json` from static assets; keep this in mind when adding build artifacts.
- `wrangler` is available via dependencies (no top-level script); use `npx wrangler ...` if you need to interact with Cloudflare locally.

## Repo Hygiene

- When searching, scope to `src/` (or exclude `node_modules/`) to avoid huge, noisy results.
