# CLAUDE.md

Guidance for Claude Code (claude.ai/code) when working in this repository.

## What this repo is

The personal academic website of Francesco Ioli (<https://franioli.github.io>), built on the
**al-folio v1.x** Jekyll theme. This is a *site*, not the al-folio starter project — it holds only
content and configuration.

**The theme runtime lives in Ruby gems** (`al_folio_core`, `al_folio_cv`, `al_citations`, `al_search`,
`al_icons`, …), listed in the `Gemfile` and `_config.yml`. There is deliberately **no local
`_layouts/`, `_includes/`, or `_sass/`**. Do not vendor or copy gem-owned files in to make a change:
shadowing one adds drift tracking via `.al-folio-overrides.yml`. Prefer, in order:

1. `_config.yml` flags and site metadata
2. `_data/*.yml`
3. page content (`_pages`, `_news`, `_bibliography`)
4. a page-scoped `<style>` block for one-off styling

## Content map

| What                  | Where                                                          |
| --------------------- | -------------------------------------------------------------- |
| Home / bio            | `_pages/about.md`                                               |
| Publications          | `_pages/publications.md` + `_bibliography/papers.bib`           |
| CV                    | `_pages/cv.md` + `_data/cv.yml` (**rendercv** schema)           |
| News                  | `_news/` (short `inline: true` posts)                           |
| Social links, CV PDF  | `_data/socials.yml`                                             |
| Assets                | `assets/img/`, `assets/pdf/`                                    |

Navigation is intentionally minimal: **About · Publications · CV**. A paper appears on the homepage
when its BibTeX entry has `selected={true}`.

## Styling constraint (important)

The theme's Tailwind CSS is **prebuilt and pruned** by the gem — it contains only the utilities the
gem's own templates use. Arbitrary utilities (`grid-cols-3`, `gap-4`, `text-sm`, `items-center`, …)
are **not available** and will render unstyled. For custom styling use a page-scoped `<style>` block
and the theme's CSS variables (`--global-theme-color`, `--global-card-bg-color`,
`--global-divider-color`, `--global-text-color-light`) so light and dark mode both work.

## Local development

```bash
docker compose up -d                  # http://127.0.0.1:8080
docker compose logs -f                # watch the build; content reloads automatically
docker compose down
```

`_config.yml` changes restart Jekyll inside the container. Note the container serves from
container-local `/tmp/_site` to avoid host bind-mount write deadlocks.

## Checks before handing work back

```bash
npx prettier --check .                        # formatting (CI-relevant)
bundle exec al-folio upgrade audit --no-fail  # expect 0 blocking / 0 non-blocking
```

Then confirm the site still serves: `/`, `/cv/`, `/publications/` should all return 200.

## Deployment

`.github/workflows/deploy.yml` builds and publishes to GitHub Pages on push to `main`. Three things
it depends on — do not delete them:

- `purgecss.config.js` (the deploy runs `purgecss -c purgecss.config.js`)
- `package.json` + `package-lock.json` (the deploy runs `npm ci`, which fails on an out-of-sync lockfile)
- the `giscus.repo` key in `_config.yml` (a `yaml-update-action` step writes to it)
