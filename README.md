# franioli.github.io

Personal academic website of **Francesco Ioli** — post-doctoral researcher in Geomatics at the
Dept. of Civil and Environmental Engineering, Politecnico di Milano.

🌐 **<https://franioli.github.io>**

Built with [Jekyll](https://jekyllrb.com/) on the
[al-folio](https://github.com/alshedivat/al-folio) theme (v1.x), whose runtime ships as Ruby gems
(`al_folio_core` and friends) rather than being vendored into this repo.

## Running it locally

The quickest way is Docker:

```bash
docker compose up -d          # then open http://127.0.0.1:8080
docker compose logs -f        # follow the build
docker compose down
```

Edits to content are picked up automatically; changes to `_config.yml` trigger a Jekyll restart.

Alternatively, with a local Ruby toolchain:

```bash
bundle install
bundle exec jekyll serve      # http://127.0.0.1:4000
```

## Where the content lives

| What                  | Where                                                            |
| --------------------- | ---------------------------------------------------------------- |
| Home / bio            | `_pages/about.md`                                                 |
| Publications page     | `_pages/publications.md` (entries in `_bibliography/papers.bib`)   |
| CV page               | `_pages/cv.md` (data in `_data/cv.yml`, rendercv format)           |
| News items            | `_news/`                                                          |
| Site settings         | `_config.yml`                                                     |
| Social links & CV PDF | `_data/socials.yml`                                               |
| Images, CV PDF        | `assets/img/`, `assets/pdf/`                                      |

A publication shows up on the homepage when its BibTeX entry has `selected={true}`.

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the site and publishes it to
GitHub Pages.

## Maintenance

```bash
npx prettier --check .                      # formatting
bundle exec al-folio upgrade audit          # check against the al-folio v1 contract
```

Layouts, includes and styles come from the al-folio gems and are intentionally **not** copied into
this repo — customisation is done through `_config.yml`, `_data/`, and page content.

## Credits & licence

Theme: [al-folio](https://github.com/alshedivat/al-folio) by Maruan Al-Shedivat and contributors —
see its [documentation](https://github.com/alshedivat/al-folio#readme) for features and configuration
options. Distributed under the [MIT licence](LICENSE).
