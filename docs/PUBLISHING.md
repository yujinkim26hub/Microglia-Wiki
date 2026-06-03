# Publishing the Microglia Wiki

The site is built with [Quartz v4](https://quartz.jzhao.xyz/) and published to **GitHub Pages**.

## How it works

This repo stores **only Markdown** (in `content/`) plus a Quartz config (`quartz.config.ts`). Quartz itself is **not** vendored here — the GitHub Actions workflow [`.github/workflows/deploy.yml`](../.github/workflows/deploy.yml) clones Quartz at build time, drops in our `content/` and `quartz.config.ts`, builds, and deploys.

```
push to main
   └─ checkout this repo
   └─ checkout jackyzha0/quartz (QUARTZ_VERSION)
   └─ cp content/        → .quartz-build/content/
   └─ cp quartz.config.ts → .quartz-build/
   └─ npm ci && npx quartz build
   └─ upload .quartz-build/public → GitHub Pages
```

## One-time setup

1. Go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **GitHub Actions**.
3. Push to `main` (or run the workflow manually via **Actions → Deploy … → Run workflow**).

The site will publish at: **https://yujinkim26hub.github.io/Microglia-Wiki/**

> `baseUrl` in `quartz.config.ts` is set to `yujinkim26hub.github.io/Microglia-Wiki`. If you rename the repo or use a custom domain, update `baseUrl` to match.

## Pinning the Quartz version

The workflow uses `QUARTZ_VERSION: "v4"`. Quartz's config API can change between revisions; if a build breaks after Quartz updates, pin `QUARTZ_VERSION` to a specific commit SHA or tag and/or reconcile `quartz.config.ts` with that version's API.

## Running locally

To preview before pushing:

```bash
git clone https://github.com/jackyzha0/quartz
cd quartz
npm i
rm -rf content && cp -r /path/to/Microglia-Wiki/content content
cp /path/to/Microglia-Wiki/quartz.config.ts quartz.config.ts
npx quartz build --serve
# open http://localhost:8080
```

## Notes

- `90-Meta/templates/` is excluded from the built site via `ignorePatterns` (templates contain `{{placeholders}}`, not real pages).
- Obsidian wikilinks (`[[microglia]]`) and aliases resolve in Quartz via the Obsidian-flavored-markdown transformer and `AliasRedirects` emitter — so keep `aliases:` in frontmatter accurate.
