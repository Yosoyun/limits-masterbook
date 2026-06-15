# LIMITS · The Edge of Calculus

**The Ranker's Masterbook — 100 original, mind-bending limit problems** built for the very top of
JEE Advanced and the Mathematical Olympiad shortlist. Every problem is *short to state, brutal to
solve*, and worked **more than one way**.

> **📖 Live site:** https://yosoyun.github.io/limits-masterbook/
> **📄 PDFs:** [The Problem Set](LIMITS-Problems.pdf) · [Complete Solutions](LIMITS-Solutions.pdf)

The ten chapters are organised by the instrument that powers the limit:

| # | Chapter | Instrument |
|---|---------|-----------|
| I | The Greatest Integer Function | ⌊x⌋ |
| II | The Fractional Part | {x} |
| III | The Signum Function | sgn(x) |
| IV | Absolute Value & Corners | \|x\| |
| V | Inverse Circular Functions | arcsin, arccos, arctan |
| VI | Logarithm & Exponential | ln, eˣ |
| VII | Advanced Trigonometry | sin, tan |
| VIII | Exotic Indeterminate Forms | 1^∞, 0⁰, ∞−∞ |
| IX | Sandwich & Discrete Sums | squeeze, Riemann sums |
| X | The Grand Hybrids | three or more, fused |

Every problem ships with:
- a clean LaTeX **statement** and **answer**,
- **The Trap** — the seductive wrong answer a strong student writes, and why it fails,
- **2–3 distinct solution methods** (squeeze, series, substitution, one-sided analysis, log-transform…),
- an **Insight** note generalising the idea.

## Run it

It's a fully static site — no build, no dependencies, no server logic. Either:

```bash
# from this folder
python3 -m http.server 8750
# then open http://localhost:8750
```

…or just double-click `index.html` (everything works from `file://` too; KaTeX and the fonts load from a CDN, so you need an internet connection the first time).

## Features

- **Beautiful manuscript UI** — Fraunces + Inter + KaTeX, an ivory "paper" theme and a "midnight" dark theme (toggle top-right or press `t`).
- **Chapter navigation** with per-chapter progress bars.
- **Filter** by difficulty (3 / 4 / 5), unsolved, or ★ bookmarked.
- **Search** across statements, titles and tags (press `/`).
- **Progress tracking** — mark problems solved, bookmark favourites; saved in `localStorage`.
- **Keyboard**: `/` search · `t` theme · `j` / `k` next / previous problem.
- **Print-friendly** — `Cmd/Ctrl+P` reveals every solution for a clean PDF.

## How the problems were made

The 100 problems were generated and then **adversarially verified**: every claimed limit and every
solution method was re-checked numerically in Python (evaluating the function from the correct side at
progressively closer points) before being allowed into the book. Wrong answers were recomputed and the
solutions repaired.

## Files

| File | Role |
|------|------|
| `index.html` | Markup + CDN links |
| `styles.css` | The design system (ivory / midnight themes) |
| `app.js` | Routing, rendering, KaTeX, filters, progress |
| `problems.js` | The 100-problem dataset (`window.PROBLEMS`) |

To add or edit a problem, append an object to `window.PROBLEMS` in `problems.js` following the existing
shape (`theme`, `themeLabel`, `title`, `difficulty`, `tags`, `statement`, `answer`, `trap`,
`solutions[]`, `remark`). Statements and answers are **raw LaTeX**; solution steps use `$…$` / `$$…$$`.
