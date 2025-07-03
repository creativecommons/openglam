# Migration

This site was migrated from WordPress hosted on Bytemark to static files hosted
on GitHub Pages.

## WordPress repository

The old WordPress repository was archived:
[cc-archive/wp-theme-openglam][ccarchive].

[ccarchive]: https://github.com/cc-archive/wp-theme-openglam


## Migration process

Process to migrate from WordPress to static files:

1. Used `curl` to pull down the four visible pages as `.html` files
2. Used `curl` to pull down missing dependencie (js, css) into relevant directory structure
3. Used `curl` to pull down missing uploads into `wp-content/uploads/`
4. Moved everything into `docs/`
5. Added `docs/.nojekyll` (empty file)
6. Discovered the site had a lot of "orphan pages" not present within the site's current nav from prior site incarnations, but still publicly accessible.
7. Setup a temporary node environment virtual space.
8. Used [`wordpress-to-eleventy`](https://github.com/mattl/wordpress-to-eleventy), to generate static `.html` pages, amending the default post and page templates' header and footer to pull down all the pages and posts via the site's API as new `.html` files into appropriate subdirectories.
9. Deleted temporary node environment.
10. Used `scp` to pull down everything from the `wp-content/uploads` folder to account for all the orphan posts/pages now added. `scp -r [name-of-ssh-alias]:path/to/wp-content/uploads path/to/local/uploads`

