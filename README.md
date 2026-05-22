# teach-me 📚

> An [Empathetech](https://www.empathetech.org/) community project: members design personal learning curricula with Claude Code, with full source attribution and an emphasis on doing it ethically.

🌐 **Live site**: [https://empathetech.github.io/teach-me/](https://empathetech.github.io/teach-me/)

## What this is

Empathetech ([empathetech.org](https://www.empathetech.org/)) is built around the idea that good software engineers are good humans. This repository is one of our community spaces — for what good humans do when they want to learn something new: they study it, build something around it, and share what they figured out.

Each course on this hub is the work of an individual community member who wanted to learn something specific and decided to design a curriculum around it. They used the [`/teach-me`](https://github.com/bjamba/bjamba-skills/tree/main/teach-me) Claude Code skill to scaffold the work and partnered with [Claude Code](https://claude.com/claude-code) to draft prose and build interactive components — with every meaningful design decision made by the human.

We have three non-negotiable values:

1. **Personal curiosity is a worthy reason to build.** No grades, no clients, no resale. Members teach themselves things that matter to them, and the artifact helps the next person who shows up curious about the same thing.
2. **Be honest about working with AI.** Every page footer reads *"Designed by [Name] with Claude Code"* — explicitly. That phrasing isn't decoration. We name both the human and the model because honesty about the collaboration is part of using AI responsibly.
3. **Cite every source.** Every factual claim in every lesson is traceable to a real, linkable source. Each lesson has a 📚 Sources section at the bottom; each course has a `credits.html` with the full bibliography. Libraries, fonts, content references, all listed.

## What's inside

The hub (`index.html`) is a landing page that consumes `portfolio.json` and renders cards for every course in the repo. Each course is a fully self-contained subdirectory with its own design, its own format, its own pace.

| Course | Designer | Topic | Status |
|---|---|---|---|
| [`brunch-made-real/`](./brunch-made-real/) | [Chris Ling](https://github.com/bjamba) | Perfect scrambled eggs & a complete brunch | Active |

**There's no single template for what a course looks like.** Some are interactive SPAs (Learn / Pick / Shop / Cook tabs, embedded widgets, timeline tools). Others might be long-form essays, gallery-style walkthroughs, notebook drivers, or formats we haven't seen yet. Each course's `format` is named in its `portfolio.json` entry; the `entry` field tells the hub which file to open. Design follows topic; topic follows curiosity.

## Run locally

```bash
# Hub landing page (uses fetch — needs a local server, see below)
open index.html

# Any individual course works directly under file://
open brunch-made-real/dashboard.html
```

Quickest way to view the hub locally:

```bash
# From the repo root
python3 -m http.server 8000
# then visit http://localhost:8000/
```

Or just visit the GH Pages deploy.

## Contributing a course

If you're an Empathetech community member with something you want to learn, you can add a course to this hub.

1. **Pick something specific you want to be *able to do*.** Not a topic — an outcome. *"Deploy a Lambda that checks this site every day"* beats *"learn AWS"*. *"Bake a fondant birthday cake by Sunday"* beats *"learn baking"*.

2. **Set up the tooling.**
   - [Install Claude Code](https://claude.com/claude-code).
   - Install the [`/teach-me`](https://github.com/bjamba/bjamba-skills/tree/main/teach-me) skill. (Open-source, lives in `bjamba/bjamba-skills`.)
   - Fork this repo and clone it locally.

3. **Run `/teach-me` from the repo root.** The skill detects the hub via `portfolio.json` and scaffolds your new course as a subdirectory. It walks you through framing the outcome, the design, and the build — front-loaded into one conversation, not a series of sessions.

4. **Design in whatever format fits your topic.** SPA, long-form, gallery, notebook — your call. The hub doesn't enforce a template; it enforces care.

5. **Hold the bar on the ethics.**
   - Every factual claim in a lesson must be cited and linkable. Inline links in the prose, per-lesson Sources section, aggregated in your course's `credits.html`.
   - Every page footer credits you as designer and Claude Code as the collaboration partner: *"Designed by [Your Name] with Claude Code."*
   - All libraries, fonts, and external dependencies listed with licenses.

6. **Add yourself to `portfolio.json`** under `contributors`, add your course under `courses`, and open a pull request.

7. **A community reviewer takes a look** — we're focused on whether you're meeting the three values above (personal curiosity + honest AI collaboration + sourced facts), not on the topic itself. If the topic matters to you, it qualifies.

We're still figuring out exactly how the contribution flow should work in practice — what gets reviewed, what we ask for in a PR template, how we keep the attribution bar high without being hostile to newcomers. Come talk to us in the [Empathetech community](https://www.empathetech.org/) if you have an idea you want to start building.

## Folder structure

```
teach-me/
├── index.html                  # Landing page (consumes portfolio.json)
├── portfolio.json              # Hub metadata + course catalog + contributors
├── credits.html                # Hub-level credits
├── README.md                   # This file
├── .nojekyll                   # GH Pages: serve raw files
├── .gitignore
├── assets/
│   └── hub-theme.css           # Hub-only theme (separate from courses)
│
└── brunch-made-real/           # Course 1 — fully self-contained
    ├── dashboard.html          # Or whatever the course's entry page is
    ├── style-guide.html
    ├── curriculum.json
    ├── credits.html
    ├── README.md
    ├── TUTOR_CONTEXT.md
    ├── assets/theme.css        # Each course's own theme
    └── module-XX/...
```

## Deploy to GitHub Pages

Already enabled at `empathetech.github.io/teach-me`. PRs merged to `main` deploy automatically (`.nojekyll` is in the repo so GH serves all files without Jekyll preprocessing).

## Credits & attribution

See [`credits.html`](./credits.html) for the hub-level attribution, and each course's own credits page for the bibliography of that course.

**The short version:** Hub fonts (Playfair Display, Inter, JetBrains Mono) via Google Fonts under the OFL. Hub hosted on GitHub Pages. Each course brings its own dependencies, listed transparently on its credits page.

---

🤗 An [Empathetech](https://www.empathetech.org/) community project. Empathy is central to our success as software engineers.
