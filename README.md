# 🧠 engram

> An *engram* is the physical trace a memory leaves in the brain. This is where I store what I learn.

Runnable notebooks and experiments from my work in **NeuroAI** and **brain–computer interfaces** — papers reimplemented, models dissected, ideas chased down.

📖 **Published site:** https://bkowshik.github.io/engram

## Layout

One folder per project; each holds its notebooks.

```
engram/
├── _quarto.yml              # site config (frozen builds)
├── index.qmd                # landing page + auto-listing of all notebooks
├── braindecode/
│   └── shallow-convnet.ipynb
└── _freeze/                 # committed precomputed outputs (do not delete)
```

## Adding a notebook

1. Drop the `.ipynb` into the relevant project folder (or create a new one).
2. Add a front-matter raw cell at the top so it lists nicely:

   ```yaml
   ---
   title: "Short title"
   description: "One-line summary."
   date: "YYYY-MM-DD"
   categories: [topic, tags]
   ---
   ```

3. (Optional) Add a Colab badge as the first markdown cell:

   ```markdown
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bkowshik/engram/blob/main/<folder>/<notebook>.ipynb)
   ```

## Local workflow (important)

Builds are **frozen**: GitHub Actions never executes notebooks, it only assembles the site from the committed `_freeze/` cache. So you must render locally before pushing:

```bash
quarto preview        # live preview while editing
quarto render         # updates _freeze/ with fresh outputs
git add . && git commit -m "Add notebook" && git push
```

Pushing to `main` triggers the Action, which publishes to the `gh-pages` branch → GitHub Pages.

## One-time setup

```bash
# 1. Install Quarto: https://quarto.org/docs/get-started/
# 2. Create the repo on GitHub (bkowshik/engram), then:
git init && git add . && git commit -m "Initial commit: engram"
git branch -M main
git remote add origin git@github.com:bkowshik/engram.git
git push -u origin main
# 3. In GitHub repo Settings → Pages, set source to the gh-pages branch.
```
