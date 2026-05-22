# teach-me 📚

A portfolio of personal learning curricula by [Chris Ling (@bjamba)](https://github.com/bjamba), designed with [Claude Code](https://claude.com/claude-code).

🌐 **Live site**: [https://empathetech.github.io/teach-me/](https://empathetech.github.io/teach-me/) *(once GitHub Pages is enabled)*

## What's inside

This repository is a **portfolio hub** — a landing page (`index.html`) that links out to fully self-contained learning curricula, each in its own subfolder.

| Course | Topic | Status |
|---|---|---|
| [`brunch-made-real/`](./brunch-made-real/) | Perfect scrambled eggs & a complete brunch | Active |

Each course is independently navigable — its own `dashboard.html`, its own theme, its own ingredient/recipe/lesson data — so you can extract a course wholesale and it'll still work.

## Run locally

```bash
# Hub landing page
open index.html

# Or any individual course
open brunch-made-real/dashboard.html
```

Everything works under `file://` except the hub's course-card rendering, which uses `fetch()` to load `portfolio.json`. That requires a local server *or* a hosted environment. Quickest fix:

```bash
# From the repo root
python3 -m http.server 8000
# then visit http://localhost:8000/
```

Or just use GitHub Pages (see below).

## Deploy to GitHub Pages

1. Push this repo to `github.com/empathetech/teach-me`.
2. In the repo's **Settings → Pages**:
   - **Source**: Deploy from a branch
   - **Branch**: `main` / root `/`
3. Wait ~30 seconds. Site lands at `https://empathetech.github.io/teach-me/`.

A `.nojekyll` file is included so GH Pages serves all files (no Jekyll preprocessing).

## Folder structure

```
teach-me/
├── index.html                  # Landing page (consumes portfolio.json)
├── portfolio.json              # Hub-level metadata + course catalog
├── credits.html                # Hub credits page
├── README.md                   # This file
├── .nojekyll                   # GH Pages: serve raw files
├── .gitignore
├── assets/
│   └── hub-theme.css           # Hub-only theme (separate from courses)
│
└── brunch-made-real/           # Course 1 — fully self-contained
    ├── dashboard.html
    ├── style-guide.html
    ├── curriculum.json
    ├── credits.html
    ├── README.md
    ├── TUTOR_CONTEXT.md
    ├── assets/theme.css
    └── module-XX/...
```

## How to add a new course

1. Create a new sibling directory (e.g. `learning-rust/`).
2. Build the course inside it as a complete self-contained curriculum (use the `teach-me` skill — `/teach-me` in Claude Code).
3. Add an entry to `portfolio.json` under `courses`.
4. Commit, push, the landing page auto-updates from the new JSON.

The hub theme (`assets/hub-theme.css`) stays separate from any course's own `assets/theme.css`. Courses are visually independent on purpose.

## Credits & attribution

See [`credits.html`](./credits.html) (and each course's own credits page) for full attribution. The short version:

- Hub fonts: Playfair Display, Inter, JetBrains Mono — all SIL Open Font License via Google Fonts.
- Hub hosting: GitHub Pages.
- Each course has its own libraries (Tone.js, Chart.js, etc.) listed in its own credits page.
- Every factual claim in any lesson is cited and linkable — see the **📚 Sources** section at the bottom of any lesson page.

Designed by **[Chris Ling](https://github.com/bjamba)** with **[Claude Code](https://claude.com/claude-code)**.
