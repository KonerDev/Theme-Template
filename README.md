# Xed-Editor Theme Template

This is a theme template for [Xed-Editor](https://github.com/Xed-Editor/Xed-Editor), allowing you to create custom light and dark color schemes for the application, editor and terminal.
You can use this template as a starting point to build your own themes.

> [!TIP]
> See the [documentation](https://xed-editor.github.io/Xed-Docs/docs/themes/#creating-custom-themes) page for details on customizing the theme.

## Getting started

1. Clone this repository
2. Edit `theme.json` to customize your theme's colors
3. Update `manifest.json` with your package metadata (at least `id`, `name`, `version`, `author`, `repository`)
4. Run `npm run build` (or `node build.js`) to produce the `.xed` package in `output/`

## Configure your theme

Edit the color palettes in `theme.json`:

* `light` / `dark` – color palettes for the app, editor and terminal

> `theme.json` holds colors only. All package metadata lives in `manifest.json` and the two files are kept separate.

The `manifest.json` holds the package metadata shown in the store:

* `id` – unique identifier of your theme (lowercase letters, numbers, `.`, `_`, `-`)
* `name` – display name of your theme
* `version`, `author`, `description`, `tags`, `repository`, `license` – store listing metadata
* `minAppVersion` – minimum Xed-Editor app version your theme supports (`null` for no restriction)
* `inheritBase` – whether to inherit token colors from the base theme

> [!WARNING]
> `manifest.json` `id` must match the package name you use when publishing.

## Build

```bash
npm run build
```

This creates `output/<id>.xed`, a ZIP package containing `theme.json`, `manifest.json` and — when present — `README.md`, `icon.png` and `CHANGELOG.md`.

## Install locally

Go to **Xed-Editor → Settings → Themes → Add theme** and select the built `.xed` file.

## Publish to the store

Upload the built `.xed` on [xed-editor.app](https://xed-editor.app). Make sure the package name you pick matches the `id` in `manifest.json`.
