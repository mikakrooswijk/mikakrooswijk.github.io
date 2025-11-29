# GitHub Pages Static Site - AI Coding Instructions

## Project Overview

This is a **developer blog for Mika Krooswijk**, hosted at `mikakrooswijk.github.io` using GitHub Pages. It consists of minimal HTML files without a build system, CSS framework, or JavaScript framework.

## Architecture

- **Pure static HTML**: No templating engine, build process, or bundler
- **Flat file structure**: HTML files placed directly in root and `posts/` directory
- **GitHub Pages deployment**: Automated via `.github/workflows/deploy-site.yml` on push to `main`

## File Structure & Conventions

```
/                    # Root serves as homepage (index.html)
├── index.html       # Main landing page
├── posts/           # Blog posts or content pages
│   └── *.html       # Individual post pages
└── .github/
    └── workflows/
        └── deploy-site.yml  # Auto-deploys entire repo root to GitHub Pages
```

## Development Workflow

### Local Development

- Open HTML files directly in browser (`open index.html`)
- No local server required, but can use: `python3 -m http.server 8000`

### Deployment

- **Automatic**: Push to `main` branch triggers GitHub Actions workflow
- **Manual**: Run workflow via GitHub Actions tab
- Entire repository root is deployed as-is (no build step)

## Code Patterns

### HTML Structure

- Standalone HTML files with inline or minimal external assets
- No shared layout system - each page is self-contained
- Example pattern from `index.html` and `posts/testpost.html`: Simple `<h1>` content structure

### Creating New Content

When adding pages:

1. Create `.html` files in root (for top-level pages) or `posts/` (for blog content)
2. Use full HTML document structure or minimal HTML as seen in existing files
3. No compilation needed - changes are live after commit/push

## Constraints & Considerations

- **No dependencies**: Site has zero npm packages, gems, or build dependencies
- **Static assets**: Place CSS/JS/images directly in repo; reference with relative paths
- **GitHub Pages limits**: 1GB size limit, static content only, no server-side processing
- **URL structure**: `posts/filename.html` becomes `mikakrooswijk.github.io/posts/filename.html`

## Common Tasks

**Add a new blog post**: Create `posts/new-post.html` with content, commit and push
**Update homepage**: Edit `index.html` directly
**Check deployment status**: View GitHub Actions tab after pushing changes
**Test locally**: `cd` to repo root and run `python3 -m http.server 8000`, visit `localhost:8000`
