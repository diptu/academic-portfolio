# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A Hugo Blox "Academic CV" site for Nazmul Alam Diptu, deployed via Netlify. Hugo Modules
(declared in `go.mod` / `config/_default/module.yaml`) pull the actual theme layouts/CSS from
`github.com/HugoBlox/kit` at build time — this repo only holds config, content, and data.

## Commands

```bash
pnpm install        # JS deps: Tailwind CSS v4 CLI, Pagefind
pnpm dev             # hugo server --disableFastRender, http://localhost:1313
pnpm build           # hugo --minify && pagefind --site public
pnpm preview         # pnpm build, then serves public/ statically (python3 -m http.server)
```

There is no test suite or linter configured. Validate changes by running `pnpm dev` and
checking the affected page, or `pnpm build` to confirm the site builds cleanly.

`/pagefind/pagefind.js` will always 404 under `pnpm dev` — Hugo's dev server renders in-memory
and never writes/serves `public/`, so Pagefind (which needs a static HTML crawl) cannot produce
a working index there. This is structural, not a bug to chase. Use `pnpm preview` to actually
test search locally.

## Architecture

- **`config/_default/hugo.yaml`** — core Hugo config: `title`, `baseURL`, taxonomies, build
  options.
- **`config/_default/params.yaml`** — under the `hugoblox:` key: site identity/tagline/SEO,
  theme colors, header/footer, analytics, comments, etc. This is the main "site-level branding"
  file (separate from per-person profile data, which lives under `data/authors/`).
- **`config/_default/menus.yaml`** — top nav. Entries can point to a page (`experience/`,
  `projects/`) or to a homepage widget anchor (`/#news`).
- **`config/_default/module.yaml`** — Hugo Modules imports (the actual theme code) and asset
  mounts.
- **`content/_index.md`** — homepage, built from `sections:` blocks (`resume-biography-3`,
  `markdown`, `collection`, etc.). Each block's `content.username` (where present) references a
  folder name under `content/authors/` — currently `admin`.
- **`content/experience.md`** — Experience/Skills/Awards/Languages page, built from
  `resume-experience`, `resume-skills`, `resume-awards`, `resume-languages` blocks. These blocks
  read their data from `data/authors/<username>.yaml`, not from markdown body content.
  `content/authors/admin/_index.md` itself is just a `build: render: never` cascade stub — it
  does not hold profile content.
  - **`data/authors/admin.yaml`** is the actual CV data: bio, education, experience, skills,
    links, interests. Edit this file to update the CV.
- **`content/projects/<slug>/index.md`** — one folder per project; rendered by
  `content/projects/_index.md`'s `collection` block (`article-grid` view).
- **`content/blog/<slug>/index.md`** — notes/posts; surfaced on the homepage via the `news`
  collection block (`page_type: blog`).
- **`assets/media/authors/admin.jpg`** — avatar image, matched by author slug.
- **`netlify.toml`** — `pnpm install` (Tailwind CLI + Pagefind) must run before `hugo`; Hugo then
  resolves its Go Modules theme dependencies and Pagefind builds the search index afterward.
  Don't drop the `pnpm install` step or pin `HUGO_VERSION` below what `hugoblox.yaml` declares —
  older Hugo can't resolve this kit's Hugo Modules.

## Known placeholders to fill in later

- `data/authors/admin.yaml` → `education[0].institution` (marked `[Add your university name]`).
- `static/uploads/resume.pdf` is the upstream template's placeholder PDF.
- `config/_default/hugo.yaml` → `baseURL` is a guessed Netlify subdomain; update once the real
  deploy URL (or custom domain) is known.
