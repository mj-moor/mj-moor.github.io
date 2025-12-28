# CLAUDE.md

This file provides guidance to Claude Code when working with this repository.

## Overview

Personal portfolio/business card website for Mark Jan Moorman, hosted on GitHub Pages at **www.mjmoor.nl**.

## Technology Stack

| Component | Technology |
|-----------|------------|
| Static Site Generator | Jekyll |
| Templating | Liquid |
| Styling | SCSS/Sass (compiled to compressed CSS) |
| JavaScript | jQuery 3.4.1 + vanilla JS |
| Hosting | GitHub Pages |
| Custom Domain | www.mjmoor.nl |

## Project Structure

```
├── _config.yml          # Jekyll configuration
├── _data/
│   └── projects.yml     # Project entries for timeline
├── _includes/           # Template partials
│   ├── head.html        # Meta tags, CSS, analytics
│   ├── header.html      # Profile, navigation, social links
│   └── footer.html      # Copyright, scripts
├── _layouts/
│   └── default.html     # Main page layout
├── _sass/               # SCSS stylesheets
│   ├── animate.scss     # CSS animations
│   ├── uno.scss         # Base styles, typography
│   ├── timeline.scss    # Project timeline component
│   ├── monokai.scss     # Syntax highlighting
│   └── tables.scss      # Table styles
├── css/main.scss        # SCSS entry point
├── js/
│   ├── main.js          # UI interactions, responsive menu
│   └── github_api.js    # Fetches GitHub repo stats
├── images/              # Profile photos, backgrounds, favicons
├── fonts/               # Foundation Icons font
├── index.html           # Homepage
└── CNAME                # Custom domain config
```

## Key Commands

```bash
# Local development (requires Jekyll/Ruby)
bundle install
bundle exec jekyll serve

# Build for production
bundle exec jekyll build
```

## Configuration

Main settings in `_config.yml`:
- `title`: Site title
- `description`: Site description
- `profilepic`: Profile image path
- `bkimage`: Header background image
- `google_analytics`: Analytics tracking ID
- Author info: `name`, `github_username`, `linkedin_username`, `medium_username`

## Adding Projects

Edit `_data/projects.yml` with entries:
```yaml
- name: Project Name
  gh_user: github-username
  repo: repository-name
  img: /images/project-image.jpg
  desc: |
    Project description in **Markdown**.
```

## Key Files to Edit

| Task | File(s) |
|------|---------|
| Update job/employer | `_includes/header.html` |
| Change profile photo | Replace `images/me.jpeg`, update `_config.yml` |
| Add social links | `_includes/header.html` |
| Add projects | `_data/projects.yml` |
| Modify styles | `_sass/*.scss` |
| Update meta/SEO | `_includes/head.html`, `_config.yml` |

## Notes

- Background images are large (2.6-3.1 MB) - consider optimizing
- GitHub API calls in `github_api.js` fetch live repo stats
- Site is responsive with mobile menu toggle at <960px width
- Favicons support all platforms (Android, iOS, Windows tiles)
