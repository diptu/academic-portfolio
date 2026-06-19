# academic-portfolio

Personal academic/CV portfolio for Nazmul Alam Diptu — Computer Science student and software
engineer specializing in applied Machine Learning, Deep Learning, and full-stack engineering
(MERN / Next.js).

Built with [Hugo Blox](https://hugoblox.com/) (Academic CV template) and deployed via Netlify.

## Local development

```bash
pnpm install
pnpm dev      # hugo server, http://localhost:1313
pnpm build    # hugo --minify + pagefind search index, output in public/
pnpm preview  # full build + pagefind, then serves public/ statically on http://localhost:8080
```

Requires [Hugo Extended](https://gohugo.io/) (this project tracks `hugo_version` in
`hugoblox.yaml`) and [pnpm](https://pnpm.io/). Local Go/Hugo Modules tooling is not required —
Netlify resolves all Go modules and JS dependencies during the cloud build (see `netlify.toml`).

**Search 404s under `pnpm dev`** — this is expected. Pagefind needs a static crawl of `public/`
to build its index, which `hugo server` (an in-memory dev server) never produces. Use
`pnpm preview` to test search locally.

## Structure

- `config/_default/` — site config (`hugo.yaml`, `params.yaml`, `menus.yaml`)
- `content/` — pages: home (`_index.md`), `experience.md`, `projects/`, `blog/`
- `data/authors/admin.yaml` — CV data: bio, education, experience, skills
- `static/uploads/resume.pdf` — placeholder; replace with an actual CV/resume PDF

## Deployment

Pushes build automatically on Netlify (`netlify.toml`). `baseURL` in
`config/_default/hugo.yaml` should be updated once a Netlify domain or custom domain is
assigned.
