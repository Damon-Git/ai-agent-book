# Repository Guidelines

## Project Structure & Module Organization

- `book/` contains the canonical Chinese manuscript; `book-<locale>/` contains translations. Figures live in each edition’s `images/` directory.
- `chapter1/` through `chapter10/` contain companion experiments with individual READMEs and dependencies.
- `agentbook/` provides shared Python infrastructure; `tests/` holds repository regression tests.
- `scripts/`, `extras/`, `overrides/`, and `assets/` support MkDocs publishing. `web-astro/` contains the Astro reader; `slides/` contains the Slidev course.
- `docs/EXPERIMENT_STATUS.md` records experiment evidence and outstanding execution requirements.

## Build, Test, and Development Commands

Use Python 3.11–3.13. Run from the repository root unless stated otherwise:

- `uv sync --locked --extra ch1 --extra dev`: install chapter-one and development dependencies; substitute the relevant chapter.
- `uv run python chapter1/context/main.py`: run an experiment after configuring its documented prerequisites.
- `uv run python -m pytest tests -q`: run regression tests; some require additional dependencies installed by CI.
- `uv run ruff check <changed-paths>`: lint changed Python files.
- `python3 -m pip install -r requirements-docs.txt`: install publishing dependencies.
- `bash scripts/build_site.sh`, then `mkdocs build -d site`: assemble and build the site. Assembly deletes and recreates `_web/`; keep original work elsewhere.
- In `web-astro/`, use `npm ci`, `npm run dev`, and `npm run build`; validate with `npm test` and `npm run check`.

## Coding Style & Naming Conventions

Use four-space Python indentation, `snake_case` functions/modules, and `PascalCase` classes. Ruff uses a 100-character line limit and excludes vendored code. Respect formatter exclusions: `chapter1/web-search-agent/tests/` uses Black’s 88-column convention. Follow nearby JavaScript and Markdown style; Astro provides Prettier through `npm run format`. Preserve chapter numbering and relative links.

## Testing Guidelines

Use pytest; name files `test_*.py` and tests `test_*`. Add focused regression cases and mock external providers where possible. Follow experiment-specific testing instructions. No repository-wide coverage threshold is configured. For translation consistency, run `python3 scripts/check_i18n_consistency.py`; inspect affected figures and links.

## Commit & Pull Request Guidelines

History commonly uses `feat:`, `fix:`, `docs:`, `test:`, and `ci:`, optionally scoped, such as `docs(ch2): clarify caching`. Keep commits focused. PRs should explain changes, link relevant issues, report validation, and include screenshots for visual changes. Edit Chinese manuscript sources first and note translation impacts; translations are synchronized after merging.

## Security & Configuration

Follow experiment READMEs for `.env` placement and provider settings. Never commit credentials or private traces. Confirm costs and hardware requirements before hosted-model or GPU runs; dependency installation alone does not demonstrate reproducibility.

## Learning workflow

This repository is also Damon’s personal learning project. Aim for understanding agent architecture and implementing it independently, beyond making examples run.

- Before a learning task, read `study/LEARNING_CONTEXT.md` and `study/PROGRESS.md` if they exist.
- When studying an experiment, first help Damon identify:
  1. What problem does it solve?
  2. Where is the Context?
  3. Where is the LLM call?
  4. Where are the Tools?
  5. Where is the Controller / Agent Loop?
  6. How does data flow?
  7. What are the termination conditions?
- Do not immediately solve learning exercises. When appropriate, ask Damon to predict important behavior before revealing the answer.
- After understanding an example, give Damon one small modification task to complete himself.
- Put substantial exercises and learning artifacts under `study/`.
- At the end of each learning session, help update `study/PROGRESS.md`.
- Keep this guide concise; store detailed learning notes under `study/`, not here.
