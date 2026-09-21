# Hub — Route Map

One repo, multiple sites. Each site lives in its own folder = its own route.
All share the Apple-style design in `_assets/apple.css`.

## Live public URL
Root: `https://abdelrahmangasser555.github.io/hub/`

| Route | Folder | Site |
|-------|--------|------|
| `/` | `index.html` | Hub home (links to every site below) |
| `/university/` | `university/` | German Master's guide — 74 universities (list + drawer, filters) |
| `/university/uni-assist.html` | `university/` | uni-assist step-by-step (register, apply, costs) |
| `/university/documents.html` | `university/` | Global documents guide (what each doc needs) |
| `/reports/bbs-uat/` | `reports/bbs-uat/` | Bahri BBS UAT readiness report (readiness, findings, evidence screenshots, test suite) |
| `/herenow/` (section on `/`) | `herenow/` | Live here.now sites (thumbnails + descriptions; regenerated daily by herenow-daily-cleanup) |
| TBD | `portfolio/` | Personal portfolio (future) |
| TBD | `bahri/` | Bahri / maritime work (future) |

## Adding a new site
1. Create a folder in this repo (e.g. `portfolio/`).
2. Put an `index.html` inside it (link `../_assets/apple.css` for shared Apple design).
3. Add a row in the hub `index.html` under "Sites".
4. Append a row to this route map.
5. Commit + push → it appears at `https://abdelrahmangasser555.github.io/hub/<folder>/`.

## Updating an existing site
Edit the files, commit, push. Same URL every time — no new project needed.

## Notes
- Data source of truth for the German guide: `university/universities.json` (74 unis).
- Deployed from branch `main` at repo root via GitHub Pages (legacy, branch-based).