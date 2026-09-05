# tw-previews

Preview builds of the Top Win campaign landings, for review before anything is
merged. Two links:

- `penalty/` — https://design-mkt-1.github.io/tw-previews/penalty/
- `flip/` — https://design-mkt-1.github.io/tw-previews/flip/

Each folder is the output of `python tools/handoff.py` in its own repository,
which stages exactly what `.github/workflows/pages.yml` publishes there:
`index.html`, `campaign.js`, `.nojekyll`, `css/`, `js/`, `campaign/`, `assets/`.
No `tools/`, no `docs/`, no source art.

**This repository is disposable.** It holds no source: it is a place to click
on a build. The source lives in `tw-penalty` and `tw-flip-cards-lp`, on the
`retrofit/template` branch of each.

## Pages settings

Settings → Pages → Source: **Deploy from a branch**, `main`, `/ (root)`.
Everything committed here is meant to be served, which is why this repo does
not carry the template's `_site` allowlist workflow.

`<meta name="robots" content="noindex, nofollow">` is on the index page: a
preview of a gambling campaign has no business in a search result.

## Refreshing a preview

    cd ../tw-penalty && python tools/handoff.py
    # unzip dist/<name>-<date>.zip over tw-previews/penalty/, then commit here
