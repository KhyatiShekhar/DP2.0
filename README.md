# DataProtect 2.0 — Presentation Deck

A multi-deck HTML presentation walking through the DataProtect 2.0 story: from the vision down through Discover, Protect, Monitor, Recover, Examples, Additionals, and Closing.

Pure HTML / CSS / JS. No build step. Open any deck in a browser.

## Section order

The top "stitch-nav" tabs appear in this canonical order on every deck:

`Vision · Discover · Protect · Monitor · Recover · Examples · Additionals · Closing`

| # | Section     | File(s)                                                  | Notes                                       |
|---|-------------|----------------------------------------------------------|---------------------------------------------|
| 1 | Vision      | `vision-opening_1.html`                                  | 3 slides                                    |
| 2 | Discover    | `a0.html`                                                | 4 slides — onboarding + Cyera auto-discovery |
| 3 | Protect     | `0.html`                                                 | Assets, classification, AI insights         |
| 4 | Monitor     | `1.html`, `2.html`, `3.html`                             | 3 decks — heatmap, AI deep dive, mutation   |
| 5 | Recover     | `4.html`                                                 | Pre-checks, test recovery, recovery types   |
| 6 | Examples    | `sources-reimagined.html`                                | Source-system examples                      |
| 7 | Additionals | `5.html`, `6.html`                                       | AI agents, integration                      |
| 8 | Closing     | `conclusion.html`                                        |                                             |

## Navigation

- **Top tabs** — jump between sections.
- **Bottom-right arrows** (or `←` / `→` arrow keys) — step through slides within a deck. At the last slide of a deck, `→` jumps to the next deck. At the first slide, `←` jumps to the previous deck and lands on its last slide (via the `?last=1` query param).
- **Dots** — bottom-center, click to jump to a specific slide within the current deck.

## Repo layout

```
.
├── vision-opening_1.html      Vision
├── a0.html                    Discover
├── 0.html                     Protect
├── 1.html                     Monitor 1/3
├── 2.html                     Monitor 2/3
├── 3.html                     Monitor 3/3 (Mutation Ladder)
├── 4.html                     Recover
├── sources-reimagined.html    Examples
├── 5.html                     Additionals 1/2
├── 6.html                     Additionals 2/2
├── conclusion.html            Closing
├── whatchanged.html           Internal change-log page (not in nav)
├── 3-copy.html, 4-copy.html   Off-grid backups (not in nav)
└── README.md
```

## Hosting on GitHub Pages

Two options:

### Option A — drag-and-drop via the GitHub website

1. Create a new public repo on github.com.
2. On the repo page click **Add file → Upload files** and drop the entire folder contents in.
3. Open **Settings → Pages**, set **Source = Deploy from a branch**, **Branch = `main`**, **Folder = `/ (root)`**, then **Save**.
4. After ~1 min the site is live at `https://<username>.github.io/<repo-name>/vision-opening_1.html`.

To make the deck open without specifying a filename, either:
- duplicate `vision-opening_1.html` as `index.html`, **or**
- create a tiny `index.html` that redirects: `<meta http-equiv="refresh" content="0;url=vision-opening_1.html">`.

### Option B — push from terminal

```bash
git init
git add .
git commit -m "DataProtect 2.0 deck"
git branch -M main
git remote add origin https://github.com/<username>/<repo-name>.git
git push -u origin main
```

Then enable Pages as in step 3 above.

## Editing tips

- Each deck is a standalone HTML file with its own scoped `<style>` block. Changes in one deck do not affect others.
- The top stitch-nav block lives near the top of `<body>` in every deck — keep the tab order identical across files.
- Cross-deck arrow navigation is driven by `window.STITCH = {prev, next}` near the bottom of each file.
