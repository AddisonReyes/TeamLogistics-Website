# Team Logistics Website

Marketing website built with Astro (v6) + Tailwind (v4) and deployed via the Cloudflare adapter.

## Development

Install dependencies (repo uses npm + `package-lock.json`):

```sh
npm ci
```

Run the dev server (Astro default: `http://localhost:4321`):

```sh
npm run dev
```

Optional project check (Astro `check`):

```sh
npm run astro -- check
```

## Build / Preview

Build production output to `dist/`:

```sh
npm run build
```

Preview the production build locally:

```sh
npm run preview
```

## Cloudflare / Wrangler

This project uses `@astrojs/cloudflare` (see `astro.config.mjs`). Wrangler is configured in `wrangler.jsonc` and expects the Worker entrypoint at `dist/_worker.js/index.js`.

If you use Wrangler locally or for deploys, build first:

```sh
npm run build
```

Then run Wrangler commands (example):

```sh
npx wrangler dev
```

## Code Structure

- Routes: `src/pages/`
- Main page: `src/pages/index.astro`
- Layout: `src/layout/MainLayout.astro`
- Global Tailwind directives: `src/styles/global.css` (imported by `MainLayout.astro`)
