# faulkner.engineering

The Faulkner Engineering LLC site: Astro 5 with Tailwind 4, deployed to GitHub Pages by `.github/workflows/deploy.yml` on
every push to `main`.

## Pages
- `src/pages/index.astro`: the consulting homepage.
- `src/pages/hyperharbor.astro`: the HyperHarbor product page. Brand assets and the client screenshot are in
  `public/hyperharbor/`; `og.png` is the social preview card. Put the demo video at `public/hyperharbor/demo.mp4` and
  the hero plays it; until then the poster image shows.
- `src/layouts/Site.astro`: shared head, header, and footer. Pass `title`, `description`, `path`, and optionally
  `ogImage`, `twitterCard`, and `current`.

## Commands
| Command | Action |
| --- | --- |
| `npm install` | Install dependencies |
| `npm run dev` | Dev server at `localhost:4321` |
| `npm run build` | Build to `./dist/` |
| `npm run preview` | Preview the build |

`public/sitemap.xml` is maintained by hand; update `lastmod` when a page changes.

## Analytics
Cloudflare Web Analytics (free, no cookies). The beacon is emitted only when `CF_ANALYTICS_TOKEN` is set at build
time; the deploy workflow reads it from the repository secret of the same name. Locally, put it in `.env` to test.
Tag links you post elsewhere with `?utm_source=` so the referrer survives apps that strip it.
