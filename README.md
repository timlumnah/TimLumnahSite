# timlumnahsite

Tim Lumnah's personal portfolio site, hosted on GitHub Pages.

## Stack

Single static `index.html`. No build step, no framework, no JS. Fonts (Space
Grotesk, JetBrains Mono) load from Google Fonts. The look (navy, blue-to-cyan
accent) matches the repo social-preview cards; those are rendered from
`portfolio_art/render_cards.py` one level up, which also writes `img/`. `_config.yml` sets
`theme: jekyll-theme-cayman` for GitHub Pages, but since `index.html` has no
Jekyll front matter, Pages serves it as a plain static file and the theme
never actually applies. That's expected, not a bug.

## Structure

One page, five sections:

- **Hero** — name, "AI Automation & Agent Developer · Cybersecurity" kicker (mirrors the LinkedIn headline), positioning line, three headline numbers, education/stack summary
- **Now** — short framing statement on where things stand currently
- **Build** — Open Otto, Context Wrangler, Test Phoenix, Otto Operator,
  Midi Repinator
- **Security** — AI security first (open_otto prompt-injection evals), then HTB Academy
  CPTS, Harvard Extension ethical hacking coursework, TryHackMe CTF work, CompTIA
  Security+. Kept in the nav but deliberately not in the hero headline: the job-search
  traction is AI and automation, and the AI-security work is the bridge between the two
- **Contact** — GitHub, LinkedIn, eBusiness card

Build rows are ordered by current relevance, AI agent work first. Each project's
copy stays tied to what that repo's README actually claims; never describe local
work that has not been pushed. All three AI repos are tagged "Public Release",
which needs each repo's LICENSE file (AGPL-3.0) to be pushed first.

Images live in `img/`: `og-card.png` (1200x630 share card, referenced by an
absolute `og:image` URL on timlumnah.github.io/TimLumnahSite, since timlumnah.com
forwards there) and one 960x480 `.webp` thumbnail per Build row. Every number on
the hero tiles, Build rows, and cards is copied from the matching repo README.

## Local preview

Either open the file directly:

```
xdg-open index.html
```

or serve it so relative paths behave exactly like production:

```
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Keeping content current

A few things on this page are point-in-time status and will go stale if not
revisited:

- HTB Academy CPTS and CompTIA Security+ are both marked "In Progress" in the
  Security section. Update the status badge (and wording, if either is
  finished) when that changes.
- Otto Operator is marked "Paused" in the Build section. Update if that
  changes.
- Project links (GitHub repos, ottooperator.com) should be
  spot-checked occasionally since dead links have been pruned from here
  before.

## Deployment

Pushes to `main` deploy automatically via GitHub Pages.

A Press section (real-estate mentions from the brokerage years) was removed 2026-11-22: it was off-lane for AI and security readers. It is in git history if it is ever wanted back.
