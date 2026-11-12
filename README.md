# radiance_demo

A standalone example site for the [`radiance`](https://github.com/cirrus365/Radiance)
Hugo theme, deployed to GitHub Pages at
`https://cirrus365.github.io/radiance_demo/`.

## Local development

The theme is **not** vendored in this repository: the site resolves it from
the neighbouring checkout through `themesDir = ".."` (the `Radiance`
directory next to this one), so edits to the theme appear here with a
plain:

```sh
hugo server
```

run from this directory — no build flags required.

## Deployment

A GitHub Actions workflow (`.github/workflows/pages.yml`) builds the site
on every push to `main` and deploys it to GitHub Pages. The workflow
checks out the theme repository (`cirrus365/Radiance`) into
`themes/Radiance` and builds with `--themesDir themes`, overriding the
local development `themesDir`. **The theme repository must therefore be
pushed to GitHub as `cirrus365/Radiance`.**

After pushing, enable Pages once in the repository settings:
*Settings → Pages → Build and deployment → Source: GitHub Actions*.

The site is built with `baseURL = https://cirrus365.github.io/radiance_demo/`
(project-site subpath), which the theme fully supports.

## Content

The content, data files and menus mirror `Radiance/exampleSite` so every
theme feature can be exercised: menus and applets, desktop shortcuts,
moodboard boards (with tile data and generated assets), the archive, tags,
search and the appearance selector.

`hugo.toml` sets `theme = "Radiance"`; on case-sensitive filesystems the
theme checkout directory must keep that name (see the theme README for the
`radiance` naming assumption).

