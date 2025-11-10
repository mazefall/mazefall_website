# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is a static portfolio website for Housseynou Fall (mazefall.com), originally built with Webflow and exported as a static site. The site is hosted on GitHub Pages and showcases UX design work and case studies.

## Repository Structure

```
.
├── docs/                    # GitHub Pages root directory
│   ├── index.html          # Main portfolio landing page
│   ├── alexa---case-study.html  # Alexa Plus case study page
│   └── robots.txt
└── assets/                  # Static assets (CSS, JS, images)
    ├── css/                # Webflow CSS files
    ├── js/                 # JavaScript including jQuery, Webflow scripts, typer.js
    └── img/                # Image assets
```

## Common Commands

### Local Development

**Serve the site locally:**
```bash
python3 -m http.server 8000 --directory docs/
```
Then visit `http://localhost:8000`

**Alternative using Python 2:**
```bash
cd docs && python -m SimpleHTTPServer 8000
```

### Version Control

**Check site status:**
```bash
git status
```

**View recent changes:**
```bash
git --no-pager log --oneline -10
```

**Push changes to GitHub Pages:**
```bash
git add .
git commit -m "Your commit message"
git push origin main
```

The site will automatically deploy to GitHub Pages from the `docs/` directory.

## Architecture Notes

### Static Site Export
- This is a **Webflow export** - the HTML/CSS/JS structure reflects Webflow's build system
- External CDN resources are referenced for Webflow core functionality
- Local copies of key scripts are in `assets/js/`

### Key Components

**Typer.js Animation:**
- Custom typing animation library in `assets/js/typer.js`
- Implements character-by-character typing effects with configurable delays and colors
- Used for dynamic text animations on the landing page

**Webflow Dependencies:**
- jQuery 3.5.1 for DOM manipulation
- Multiple Webflow runtime scripts (`webflow-1.js`, `webflow-2.js`, `webflow-3.js`)
- Shared CSS files for Webflow component styling

**Video Embeds:**
- Case study pages use embedded videos from Dropbox for project demonstrations
- Videos use autoplay, muted, loop, and playsinline attributes

### Content Structure

**Portfolio Pages:**
- `index.html`: Main landing with project thumbnails and descriptions
- `alexa---case-study.html`: Detailed Amazon Alexa Plus UX case study

**Projects Featured:**
1. Amazon - Alexa Plus (onboarding experience)
2. ClosetMatch (AI wardrobe recommendations) - Coming soon
3. Otter - Cloudkitchens (design system convergence)
4. Sotheby's (registration flow simplification)

## GitHub Pages Deployment

The site deploys from the `docs/` directory on the `main` branch. Any changes pushed to `main` will automatically update the live site at the configured GitHub Pages URL.

**Deployment checklist:**
1. Test changes locally using Python's HTTP server
2. Verify all asset paths are relative to `docs/`
3. Commit and push to `main` branch
4. Check GitHub Pages deployment status in repository settings

## Important Notes

- **Do not modify Webflow CDN references** - these are required for proper styling
- **Asset paths must be relative** to the `docs/` directory for GitHub Pages
- **Video embeds use Dropbox links** - ensure links remain valid
- The site uses inline styles and Webflow's class naming conventions
