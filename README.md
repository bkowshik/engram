# engram

An *engram* is the physical trace a memory leaves in the brain — so this is where I store what I learn.

📖 **Published site:** https://bkowshik.github.io/engram

## Workflow

The build **never executes notebooks** — it renders the outputs already saved inside each `.ipynb` (`execute: enabled: false`). So the runner needs no Python, no dependencies, and never downloads datasets.

That means: **run a notebook (locally or in Colab), save it with its outputs, then commit.** A notebook committed without outputs will render with no figures.

```bash
quarto preview        # live preview while editing (renders saved outputs)
git add .
git commit -m "Add notebook"
git push
```

Pushing to `main` triggers the Action, which publishes to the `gh-pages` branch → GitHub Pages.
