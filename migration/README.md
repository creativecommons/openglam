# Migration

This site was migrated from WordPress hosted on Bytemark to static files hosted
on GitHub Pages.

## WordPress repository

The old WordPress repository was archived:
[cc-archive/wp-theme-openglam][ccarchive].

[ccarchive]: https://github.com/cc-archive/wp-theme-openglam


## Migration process

Process to migrate from WordPress to static files:

1. Used `curl` to pull down the four pages as `.html` files
2. Used `curl` to pull down missing dependencie (js, css) into relevant directory structure
3. Used `curl` to pull down missing uploads into `wp-content/uploads/`
4. Moved everything into `docs/`
5. Added `docs/.nojekyll` (empty file)
