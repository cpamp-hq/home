# CPA Manager Plus — Project Homepage (`cpamp-hq/home`)

Live site: **<https://cpamp.seakee.dev/>** (Chinese) · **<https://cpamp.seakee.dev/en/>** (English)

Static bilingual project homepage for [CPA Manager Plus](https://github.com/seakee/CPA-Manager-Plus), deployed to GitHub Pages.

## Design Constraints

- Plain static HTML + CSS (`site/`), zero JavaScript frameworks.
- Zero external fonts, CDNs, trackers, or analytics SDKs.
- Brand icons and SVGs (`favicon.svg`, `favicon.ico`, `apple-touch-icon.png`, `assets/logo*.svg`) are copied directly from `seakee/CPA-Manager-Plus@v1.14.10`.

## Repository Layout

```text
.
├── .github/workflows/deploy.yml   # Deploys site/ directly to GitHub Pages
└── site/
    ├── .nojekyll
    ├── 404.html                   # Bilingual 404 page
    ├── apple-touch-icon.png
    ├── assets/
    │   ├── logo-white.svg
    │   ├── logo.svg
    │   └── styles.css
    ├── en/
    │   └── index.html             # English homepage (/en/)
    ├── favicon.ico
    ├── favicon.svg
    └── index.html                 # Chinese homepage (/)
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
