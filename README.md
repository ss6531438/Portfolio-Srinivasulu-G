# Srinivasulu G — Portfolio

Single-file, zero-build personal portfolio. Everything lives in `index.html`
(HTML + Tailwind CDN + vanilla JS). Images and the résumé are served from CDN
URLs already embedded in the file.

## Run locally

Just open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8000
# http://localhost:8000
```

## Deploy

Push this folder to a Git repo, then pick one:

**GitHub Pages**
1. Push to `main`.
2. Settings → Pages → Source: `Deploy from a branch` → `main` / `/ (root)`.
3. Done — the site is served at `https://<user>.github.io/<repo>/`.

Alternatively the included workflow `.github/workflows/deploy.yml` publishes
Pages automatically on every push to `main` (Settings → Pages → Source:
`GitHub Actions`).

**Vercel** — Import the repo. Framework preset: `Other`. Build command: none.
Output directory: `.` (`vercel.json` already sets this.)

**Netlify** — Import the repo. Build command: none. Publish directory: `.`
(`netlify.toml` already sets this.)

**Cloudflare Pages** — Build command: none. Output directory: `/`.

## Structure

```
.
├── index.html              # the entire site
├── assets/                 # profile photo, screenshots, certificates, resume
├── robots.txt
├── vercel.json             # Vercel static config
├── netlify.toml            # Netlify static config
├── .nojekyll               # let GitHub Pages serve files starting with _
├── .gitignore
└── .github/workflows/deploy.yml
```

## Updating content

All data (projects, stack, certificates, repos, quotes) lives in JS arrays near
the bottom of `index.html` — edit those arrays, no rebuild needed.
