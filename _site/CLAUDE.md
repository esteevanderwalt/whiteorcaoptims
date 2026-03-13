# whiteorcaoptims — Build Notes

## Jekyll Build

Always build with `JEKYLL_ENV=production` to ensure OG tags, canonical URLs, and Twitter Card meta use the production domain (`https://www.whiteorcaoptims.com`) instead of `localhost:4000`.

```bash
JEKYLL_ENV=production jekyll build
```

**Never use `jekyll serve` output for deployment** — `jekyll serve` overrides `site.url` to `localhost:4000`.

## Jekyll Location

Jekyll is installed via Homebrew Ruby. It's on PATH via `~/.zshrc`:

```
/opt/homebrew/lib/ruby/gems/3.4.0/bin
```

## Deployment

Site is deployed via GitHub Pages from the `main` branch.
The `_site/` folder is committed and pushed — GitHub Pages serves it directly.

Typical deploy workflow:
```bash
JEKYLL_ENV=production jekyll build
git add _site/ <any source files changed>
git commit -m "..."
git push
```
