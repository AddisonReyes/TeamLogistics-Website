# Team Logistics Website

Marketing website for Team Logistics built with Astro v6 and Tailwind v4.

## Stack

- Astro
- Tailwind CSS v4 via `@tailwindcss/vite`
- Astro React integration enabled
- Cloudflare Pages for deployment

## Development

Install dependencies:

```sh
npm ci
```

Start the local development server:

```sh
npm run dev
```

Run Astro checks:

```sh
npm run astro -- check
```

## Build

Create the production build:

```sh
npm run build
```

Preview the built site locally:

```sh
npm run preview
```

The production output is generated in `dist/`.

## Deployment

This project is configured for Cloudflare Pages using `wrangler.jsonc`.

Current Pages config:

- Project name: `teamlogistics`
- Build output directory: `./dist`

If you deploy from the Cloudflare dashboard, make sure the build output directory matches `dist`.

## Project Structure

```text
src/
  components/
    common/
      Footer.astro
      Icon.astro
      Navbar.astro
    Data.astro
    FAQ.astro
    Features.astro
    Hero.astro
    QuoteForm.astro
    Services.astro
  layout/
    MainLayout.astro
  pages/
    index.astro
  styles/
    global.css
public/
  favicon.ico
  favicon.svg
  tl_logo.png
```

## Page Composition

The home page is assembled in `src/pages/index.astro` with these sections:

- Navbar
- Hero
- Services
- Features
- Data
- FAQ
- Quote form
- Footer

## Styling Notes

- Tailwind is available, but most of the current UI uses component-scoped CSS.
- Global CSS variables, base styles, and font imports are defined in `src/layout/MainLayout.astro`.
- Brand styling is built around navy, blue, red, sand, and soft surface tokens declared as CSS variables.
