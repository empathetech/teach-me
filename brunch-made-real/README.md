# Brunch Made Real 🍳

A personal teach-me curriculum on perfect scrambled eggs and a complete brunch.

**Objective:** Make perfect scrambled eggs and serve a complete, reasonably-priced brunch to your family this weekend.

## Start here

Double-click `dashboard.html` to open it in your browser. That's the whole curriculum.

No server, no install, no accounts. Works under `file://`.

## What's inside

The dashboard is a single-page app with four tabs:

| Tab | What you do there |
|---|---|
| **📚 Learn** | Eight lessons across four modules. The why behind the technique. Magazine-style prose with embedded interactive widgets. Read on the couch. |
| **🍳 Pick** | Browse 12 recipes (8 egg styles + 4 sides) with filter chips. Pin everything you want to serve. Expand any card to see and edit ingredient prices inline. |
| **🛒 Shop** | Aggregated grocery list pulled from your pinned recipes, scaled to your servings, grouped by store section. Check items off as you shop. Print-friendly. |
| **🔥 Cook** | The doing mode. A smart-parallel timeline that schedules each pinned recipe so everything lands warm at T-0. Step timers with ambient kitchen music. Completion toasts. |

A **Style Guide** lives at `style-guide.html` for dev reference (every color, font, component, tone choice). It's not linked from the user-facing nav — open it directly when you're editing the theme.

## Curriculum at a glance

1. **The science of scrambled eggs** — Why low heat wins · Salt timing · Three styles compared
2. **Composing a brunch** — What makes a brunch feel complete · Timing the menu so everything lands warm
3. **Sides & accompaniments** — Carbs (bread, potatoes, hash) · Fresh things (salads, fruit, sauces)
4. **Stretching the budget** — Where to splurge, where to save

About an hour of reading total. Or you can skip the lessons entirely and go straight to **Pick → Shop → Cook**.

## How the tools work

### Edit prices once, they propagate everywhere
Per-unit prices live in `localStorage['brunch_prices']`. Edit any ingredient or upgrade price in the **Pick** tab and it flows automatically to:
- That recipe card's per-person cost
- The Pick summary bar
- The Shop list totals
- The Cook tab summary

Edit either the `$/unit` field (e.g. `$0.30 per egg`) OR the `Total $` field (e.g. `$1.80 for the eggs in this recipe`) — the other recalculates.

### Pin once, plan everything
Pin recipes in **Pick**. The Shop tab builds your grocery list from the pinned set. The Cook tab schedules them all to land warm together. Servings is a single shared value across all three tabs.

### Pan inventory drives batching
Tell the dashboard what pans you actually own (in Pick → 🍳 Your pans). The Cook tab will schedule single-batch, parallel multi-pan, or sequential-batches depending on what fits.

## Pick up where you left off

Open this directory in Claude Code and say "let's continue" — Claude will read `TUTOR_CONTEXT.md` and `curriculum.json` and pick up as your tutor.

## Files

```
brunch-made-real/
├── dashboard.html              # The SPA — every interactive flow
├── style-guide.html            # Design bible
├── curriculum.json             # State of the curriculum
├── TUTOR_CONTEXT.md            # For Claude in Tutor Mode
├── README.md                   # This file
├── assets/
│   └── theme.css               # Single source of truth for all visual tokens
├── module-01-science/
│   ├── lesson-01-low-heat.html
│   ├── lesson-02-salt-timing.html
│   └── lesson-03-three-styles.html
├── module-02-composing/
│   ├── lesson-01-complete-brunch.html
│   └── lesson-02-timing.html
├── module-03-sides/
│   ├── lesson-01-carbs.html
│   └── lesson-02-fresh-things.html
├── module-04-budget/
│   └── lesson-01-splurge-save.html
└── progress/                   # Your personal notes (empty by default)
```

## Budget & timeline

🎯 **Objective:** Make perfect scrambled eggs and serve a complete, reasonably-priced brunch to your family this weekend.
📅 **Timeline:** ~5 days reading + cooking, or 1–2 hours of focused study + a Sunday morning to execute.
💰 **Cost:** Free. Everything runs in your browser, no accounts. Curriculum cost was ~$0.30 to generate.
🍳 **Target meal cost:** ~$5/person baseline. Upgrade tiers shown inline (+$0.30 to +$3.50/p depending on which knobs you flip).

## Credits

Designed by [Chris Ling](https://github.com/bjamba) with [Claude Code](https://claude.com/claude-code).

See `credits.html` for the full attribution page (Tone.js, Chart.js, Google Fonts — Fraunces, Inter, JetBrains Mono).

🍳 Brunch made real.
