# Repository Guidelines

## Project Structure & Organization
- Root `index.html`: about page. `skriving/index.html`: writing.
- `articles/`: standalone HTML pages for posts (shared header and footer).
- `style.css`: the single stylesheet. `img/`: images. See `CLAUDE.md` for design and content conventions.
- Keep pages fast: no JS by default; prefer semantic HTML5.

## Develop & Preview
- Serve locally: `python3 -m http.server 8000`, then visit `http://localhost:8000`.
- A pushed branch gets a Vercel preview deployment; a push to `main` deploys to production.

## Coding Style & Naming
- HTML: 2-space indentation, 80–100 char soft wrap, valid HTML5.
- Semantics: use `<main>`, `<article>`, `<section>`, `<nav>`, `<time>`.
- Accessibility: proper headings order, focus-visible outlines, sufficient contrast, `lang="nb"` (and `lang="en"` on English passages).
- CSS: prefer rem units, mobile-first, light theme only.
- Filenames/paths: kebab-case (`small-models.html`).

## Testing & Quality
- Manual checks: keyboard nav, focus states, zoom at 200%, 375 px width without horizontal scroll.
- Validate: W3C HTML/CSS validators (optional) before PR.
- Performance: keep pages <14KB critical HTML/CSS when feasible; avoid unneeded images.

## Commits & Pull Requests
- Commits: concise and scoped (e.g., `content: add small-models article`).
- PRs: clear description, screenshots for visual changes, link issues (e.g., `Closes #12`).
- CI not required; reviewers verify locally that pages render and navigate.

## Security & Hosting Tips
- Do not commit secrets. If adding analytics, document it in `CLAUDE.md` and keep JS minimal.
- Set static hosting headers if possible: `Content-Security-Policy` without `unsafe-inline` (except for this repo’s minimal inline CSS), and basic caching for immutable assets.
