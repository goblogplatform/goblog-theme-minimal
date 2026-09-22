# Minimal — a goblog theme

Sans-serif, plenty of whitespace and a single blue accent. This is the theme that shipped compiled into goblog as `minimal` up to 0.6.x, published as a directory theme so it can be installed and updated on its own.

## Install

From your goblog: **Admin → Themes → Browse → Minimal → Install**, then **Activate**. Requires goblog 0.7.0 or newer (earlier releases have a built-in `minimal` that shadows an installed copy).

Upgrading a site that already used the built-in `minimal`: after the goblog upgrade the site renders the default theme until you install Minimal from the directory; the `theme` setting is left alone, so the site switches back as soon as the theme is installed.

## What it overrides

Only the public-facing templates that differ from default (`header`, `footer`, `home`, `post`, `posts`, `login` and the `page_*` types) and `static/css/goblog.css`. Everything else — admin and wizard pages, tags, archives, search, error — renders from goblog's default theme, so it keeps up with new goblog releases automatically.

## Developing

Edit the files under `templates/` and `static/`, drop the folder into a goblog checkout as `themes/installed/minimal/` (or point `THEMES_INSTALLED_DIR` at its parent) and set the `theme` setting to `minimal`. Templates are Go `html/template`; see [goblog.live/docs/writing-a-theme](https://www.goblog.live/docs/writing-a-theme) for the contract.

## Releasing

Tag `vX.Y.Z` and publish a GitHub release; the directory picks up the tag's archive. `screenshot.png` at the root is shown in the listing.
