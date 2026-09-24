# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal website for Øyvind Sandåker (oyvindbs.no; older pages and sources use Øyvind Brekkhus Sandåker). Plain HTML and CSS: no framework, no build step, no JavaScript and no external fonts. The homepage is an about page (who he is, what he does now, where he has been on stage, contact) and writing has its own page.

## Development Commands

```bash
# Serve the site locally
python3 -m http.server 8000
# Then visit http://localhost:8000
```

`404.html` uses root-absolute paths and is served by Vercel for missing pages; the Python server does not use it, so open `/404.html` directly to check it.

### Deploy

Vercel's Git integration deploys the repo as-is. A push to `main` is the production deploy; every other branch gets a preview deployment. Do not run `vercel --prod`.

## Structure

- `index.html`: about page (hero, status line, about + career, stage, contact)
- `skriving/index.html`: writing (own articles, Day of Week posts in NO and EN, notes elsewhere)
- `articles/`: the site's own articles
- `homborsund/`: a public page that also uses `style.css`
- `ean/`, `tekster/`: unlisted pages with their own inline styles; leave them alone unless asked
- `404.html`, `img/`, `favicon.svg`, `robots.txt`, `sitemap.xml`, `llms.txt`
- `style.css`: the one stylesheet, with design tokens in `:root`

## Design

- Light theme only (`color-scheme: light`), no dark-mode variant. Paper background, ink text, hairlines instead of cards, one accent colour (`--accent`).
- Tech touches: monospace kickers and metadata (`// scene`, `$ whoami`), a dot grid behind the page heads, a timeline styled like a git log.
- System fonts: Helvetica stack for text, `ui-monospace` stack for metadata.
- Mobile first. Must work at 375 px without horizontal scroll. Visible focus, skip link, one `h1` per page, `prefers-reduced-motion` respected.

## Content conventions

- Norwegian first (`lang="nb"`). English content keeps `lang="en"`. Day of Week articles are linked in both languages (NO and EN).
- Credit correctly: Techpoint, Arendalsuka and Egderøre happened while he worked at Egde (2020–2026). Homborsund AI is a non-profit he runs on the side. Day of Week is the current job.
- New copy avoids em-dash chains. Commas, colons and full stops instead.
- No e-mail address on the site (it only attracts spam). Contact goes through LinkedIn, X and GitHub.
- The status line under the hero shows what he does now and on the side. Egde is not listed there; it stays in the career list and the stage credits.
- A speaker version with a talks page exists on the branch `redesign/foredrag`, parked until the speaker profile is ready.
- Adding or removing a public page or article: update `skriving/index.html`, `sitemap.xml` and `llms.txt`.

## Technical Conventions

- HTML: 2-space indentation, semantic elements (`<main>`, `<article>`, `<section>`, `<nav>`, `<time>`)
- CSS: rem units, grid, section comments
- File naming: kebab-case
- SEO: meta description, Open Graph, Twitter card (text-only previews), JSON-LD (`Person` with `@id` `https://oyvindbs.no/#person` on the homepage; other pages refer to it)
