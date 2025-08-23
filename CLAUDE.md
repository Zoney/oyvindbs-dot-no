# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal website for Øyvind Brekkhus Sandåker (oyvindbs.no) - a static HTML site with articles about DevOps, software development, and learning resources. The site is built with vanilla HTML/CSS and focuses on simplicity, performance, and accessibility.

## Development Commands

### Local Development
```bash
# Serve the site locally using Python's built-in server
python3 -m http.server 8000
# Then visit http://localhost:8000
```

### Testing & Validation
- Manual testing: Check keyboard navigation, focus states, zoom at 200%, and dark mode compatibility
- Optional: Use W3C HTML/CSS validators before commits
- Ensure pages remain under 14KB for critical HTML/CSS when feasible

## Architecture & Structure

### File Organization
- `index.html`: Main homepage with personal profile and article previews
- `articles/`: Standalone HTML pages for individual posts
- `style.css`: Global stylesheet with responsive design and dark theme
- `AGENTS.md`: Repository development guidelines (existing)

### Content Pattern
- **Home page structure**: Two-column grid layout with profile sidebar and main content area
- **Article pages**: Mirror the home page styling with article-specific layout classes
- **Styling approach**: Single CSS file with mobile-first responsive design
- **Language**: Mixed Norwegian/English content (articles primarily in Norwegian)

### Technical Conventions
- **HTML**: 2-space indentation, semantic HTML5 elements (`<main>`, `<article>`, `<section>`)
- **CSS**: Uses CSS Grid for layout, rem units for sizing, supports `prefers-color-scheme: dark`
- **Accessibility**: Proper heading hierarchy, sufficient color contrast, focus-visible outlines
- **File naming**: kebab-case for new files (`new-article.html`)
- **SEO**: Comprehensive meta tags, Open Graph, Twitter Cards, JSON-LD structured data

### Content Strategy
- Articles focus on software engineering, DevOps practices, and learning resources
- Each article has rich metadata for social sharing and SEO
- Inline CSS for critical styles, minimal external dependencies
- No JavaScript by default - pure HTML/CSS approach

## Quality Standards

- Maintain semantic HTML structure
- Keep CSS organized with clear section comments
- Ensure responsive design works across mobile/tablet/desktop
- Test accessibility features (keyboard nav, screen readers)
- Follow the existing content and styling patterns when adding new articles