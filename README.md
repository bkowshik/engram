# 🧠 engram

> An *engram* is the physical trace a memory leaves in the brain. This is where I store what I learn.

Runnable notebooks and experiments from my work in **NeuroAI** and **brain–computer interfaces** — papers reimplemented, models dissected, ideas chased down.

📖 **Published site:** https://bkowshik.github.io/engram

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

## Workflow (important)

The build **never executes notebooks** — it renders the outputs already saved inside each `.ipynb` (`execute: enabled: false`). So the runner needs no Python, no dependencies, and never downloads datasets.

That means: **run a notebook (locally or in Colab), save it with its outputs, then commit.** A notebook committed without outputs will render with no figures.

```bash
quarto preview        # live preview while editing (renders saved outputs)
git add . && git commit -m "Add notebook" && git push
```

Pushing to `main` triggers the Action, which publishes to the `gh-pages` branch → GitHub Pages.
