# Deploying this portfolio (GitHub Pages - MkDocs)

This repo contains a GitHub Actions workflow that builds the MkDocs site and deploys to the `gh-pages` branch automatically on push to `main` or `master`.

## Quick checklist

1. Repository is ready with `.github/workflows/deploy.yml`
2. Default branch is set to `main`
3. GitHub Actions is enabled
4. After the first successful workflow run, the site is published to GitHub Pages

## Notes

- The workflow uses `GITHUB_TOKEN` automatically (no extra secret needed)
- Site URL: https://ejsang.github.io/erik-sangeorzan-portfolio-harman/
