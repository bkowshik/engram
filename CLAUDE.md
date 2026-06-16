# engram — working notes for Claude

engram is a **public** repository: a Quarto site of NeuroAI / brain–computer-interface notebooks, published at https://bkowshik.github.io/engram. Write everything here as if anyone can read it — because they can.

# 🔒 Git

Never `git commit` or `git push` unless Bhargav explicitly says so. Make the changes, then stop and let him commit.

# 📐 Conventions

Authoring and build conventions live in [`cookbook.ipynb`](cookbook.ipynb) — repo structure, the publish workflow, and the Quarto patterns. Read it before changing how notebooks are built or styled, and don't restate its contents elsewhere.

Two constraints worth keeping front of mind:

- **The build never executes notebooks** (`execute: enabled: false`). Commit notebooks *with their saved outputs* — a notebook without outputs renders blank.
- **Retina plots.** Set `%config InlineBackend.figure_format = "retina"` near the top of every notebook so saved figures are crisp.

# 🤝 Working style

How Bhargav wants Claude to work. He corrects, Claude updates.

- **Keep it public-safe.** Never commit personal notes, private file paths, or anything not meant for the world.
- **Start minimal, layer up on request.** For design, styling, and scope, build the clean baseline first and *propose* flourishes rather than applying them wholesale.
- **Don't duplicate content that lives elsewhere.** Link to the source instead of restating it.
- **Verify actual state before diagnosing.** When something "isn't working," inspect what's actually committed, the deployed branch, and the live config before assuming a cause.
