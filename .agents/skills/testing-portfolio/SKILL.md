# Testing the Portfolio Site

## Overview
This is a static HTML portfolio site deployed via GitHub Pages. No backend, no build step — just `index.html`.

## How to Test Locally

1. The Chrome wrapper at `~/.local/bin/google-chrome` only opens tabs in an existing Chrome instance via CDP on port 29229. If Chrome isn't already running, launch it directly:
   ```bash
   /opt/.devin/chrome/chrome/linux-133.0.6943.126/chrome-linux64/chrome \
     --no-first-run --no-default-browser-check \
     --remote-debugging-port=29229 \
     --user-data-dir=/tmp/chrome-portfolio \
     "file:///home/ubuntu/repos/Portfolio/index.html" &
   ```
   Note: The exact Chrome version path may change over time. Check `/opt/.devin/chrome/chrome/` for available versions.

2. Maximize the browser window for recording:
   ```bash
   sudo apt-get install -y wmctrl
   wmctrl -r "Paul Inyangala" -b add,maximized_vert,maximized_horz
   ```

## Key Sections to Verify

- **Hero**: Gradient heading "Paul Inyangala", "Available for Opportunities" badge, "View My Work" and "GitHub Profile" buttons
- **About**: PI initials placeholder, Name, Email, GitHub link (Thorium234), Location (Kenya)
- **Skills**: 4 category cards — Frontend (6 tags), Backend (6 tags), Frameworks (5 tags), Tools (5 tags)
- **Projects**: 12 project cards in a 3-column grid, each with title, description, tech-dot indicator, and "View Repo" link to GitHub
- **Stats Bar**: 55+ Repositories, 10+ Languages, 5+ Frameworks, 2+ Years Coding (hardcoded)
- **Contact**: Email, GitHub, Phone links + message form (form has no backend)
- **Navigation**: Smooth-scroll from nav links and hero CTA buttons

## Known Limitations

- Contact form has no `action` attribute — it won't send messages
- GitHub stats are hardcoded and need manual updates
- Profile image is a "PI" text placeholder (no actual photo)
- GitHub Pages deploy CI only triggers on pushes to `main`, not on PR branches

## Devin Secrets Needed
None — this is a fully static site with no authentication or API keys required.
