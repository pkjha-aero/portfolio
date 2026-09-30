# portfolio

Source for [pkjha-aero.github.io/portfolio](https://pkjha-aero.github.io/portfolio/), built with
[MkDocs Material](https://squidfunk.github.io/mkdocs-material/) in the same style as
[StudyMaterial](https://pkjha-aero.github.io/StudyMaterial/).

## Build locally

```bash
python -m venv .venv && . .venv/bin/activate
pip install -r requirements.txt
mkdocs serve          # http://127.0.0.1:8000/portfolio/
mkdocs build --strict # what CI runs
```

## Layout

- `docs/`: pages, one folder per section
- `docs/snippets/links.md`: every external URL, as reference-style links shared by all pages
- `docs/assets/figures/`: figures, credited in their captions
- `overrides/main.html`: social-card meta tags

Pushes to `main` deploy through GitHub Actions; pull requests build only. `main` is protected,
so all changes go through a pull request.
