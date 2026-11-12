# CPA Manager Plus — Project Homepage (`cpamp-hq/home`)

Live site: **<https://cpamp.seakee.dev/>** (English, default) · **<https://cpamp.seakee.dev/zh/>** (Chinese)

Static bilingual project homepage for [CPA Manager Plus](https://github.com/seakee/CPA-Manager-Plus), deployed to GitHub Pages.

## Design Constraints

- Plain static HTML + CSS (`site/`), no JavaScript at all (the only `<script>` is JSON-LD metadata).
- Zero external fonts, CDNs, trackers, or analytics SDKs. Light and dark themes follow `prefers-color-scheme`.
- Brand icons and SVGs (`favicon.svg`, `favicon.ico`, `apple-touch-icon.png`, `assets/logo*.svg`) are copied directly from `seakee/CPA-Manager-Plus@v1.14.10`.
- Product screenshots (`assets/img/*.webp`) are converted from the product repository `img/*.png` at `dev@0728c256` (1.x UI, synthetic demo data) with `cwebp -q 78`; `assets/og.jpg` is a 1200×630 crop of `img/dashboard.png`. Refresh them when the 1.x UI changes, and switch to v2 screenshots at GA.
- Facts on the page (version, features, ports, install commands) must match the current 1.x Stable docs; the version pill and channel cards name the latest stable release explicitly and need updating on each 1.x release.

## SEO

- English is the default language at `/` and `x-default`; Chinese lives at `/zh/`. Both pages carry `canonical`, reciprocal `hreflang`, Open Graph / Twitter cards and a JSON-LD graph (`Organization`, `WebSite`, `WebPage`, `SoftwareApplication`, `FAQPage`).
- The visible FAQ section and the `FAQPage` JSON-LD must stay in sync, and `softwareVersion` in JSON-LD must match the version pill.
- `robots.txt` points to `sitemap.xml`, which lists both language URLs with `xhtml:link` alternates; bump `<lastmod>` when page content changes.
- `/en/` is a `noindex` redirect to `/` that keeps the previously published English URL working.

## Repository Layout

```text
.
├── .github/workflows/deploy.yml   # Deploys site/ directly to GitHub Pages
└── site/
    ├── .nojekyll
    ├── 404.html                   # Bilingual 404 page (English first)
    ├── apple-touch-icon.png
    ├── assets/
    │   ├── img/                   # Product screenshots, zh (-zh) and en
    │   ├── logo-white.svg
    │   ├── logo.svg
    │   ├── og.jpg                 # Social preview image
    │   └── styles.css
    ├── en/
    │   └── index.html             # Redirect from the old English URL to /
    ├── favicon.ico
    ├── favicon.svg
    ├── index.html                 # English homepage (/)
    ├── robots.txt
    ├── site.webmanifest
    ├── sitemap.xml
    └── zh/
        └── index.html             # Chinese homepage (/zh/)
```

## Local Preview

Serve `site/` with any static HTTP server, for example:

```bash
python3 -m http.server 8080 --directory site
```

## Related Sites

- Documentation: <https://cpamp-docs.seakee.dev/> (`main` = 1.x Stable, `/next/` = v2 Beta)
- Online Demo (1.x Stable): <https://cpamp-demo.seakee.dev/>
- Product Repository: <https://github.com/seakee/CPA-Manager-Plus>
