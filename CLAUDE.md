# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based static site, forked from the Scriptor theme by Just Good Themes. It's customized for a personal blog at iterative.co.nz with simplified templates (comments and social media integrations removed).

## Development Commands

### Local Development
```bash
# Install dependencies
bundle install

# Run local development server (watches for changes)
jekyll serve

# Build the site (output goes to _site/)
jekyll build
```

The development server runs at http://localhost:4000 by default and auto-regenerates when files change.

## Architecture

### Jekyll Structure

**Layouts** (`_layouts/`):
- `default.html`: Base layout with header/footer, loads CSS/JS assets
- `post.html`: Individual blog post layout with author box
- `page.html`: Static page layout
- `tags.html`: Tag archive page layout

**Content**:
- Blog posts go in `_posts/` with format `YYYY-MM-DD-title.md`
- Posts use front matter with fields like `title`, `date`, `tags`, `categories`, `feature_image`
- Use `<!--more-->` in post content to create excerpts on index page

**Styling**:
- SASS files in `_sass/` (e.g., `_general.scss`, `_content.scss`, `_site-header.scss`)
- Main stylesheet at `assets/css/style.css`
- Syntax highlighting via `_prism.scss`

**Data Files** (`_data/`):
- `author.json`: Author bio, location, and image
- `social.json`: Social media links (used in includes)

**Includes** (`_includes/`):
- `header.html`, `footer.html`: Site chrome
- `google_analytics.html`: Analytics (production only)
- `image_caption.html`, `image_full.html`: Image helpers
- `social.html`: Social media icons

### Configuration

**_config.yml**:
- Site metadata (title, description, URL)
- Navigation menu items
- Pagination settings (5 posts per page)
- Color scheme (accent color)
- Jekyll plugins: `jekyll-paginate`, `jekyll-sitemap`

**Special Behavior**:
- Google Analytics only loads in production environment
- Title tag uses `longtitle` variable for homepage, appends site title for other pages
- Permalinks use `/:title` format (no date in URL)

## Key Files

- `index.html`: Homepage with paginated post list
- `tags.md`: Tag archive page
- `about.md`: About page
- `feed.xml`: RSS feed template
