# Deploying this site (notes for Daniël)

This is a personal academic website built on [al-folio](https://github.com/alshedivat/al-folio), pre-filled from your CV.

## Deploy to GitHub Pages (recommended)

1. Create a **public** repo named `Daniel-Trujillo.github.io` under your GitHub account (it must match your username to be served at the root URL).
2. In this folder:
   ```bash
   git init -b main
   git add -A
   git commit -m "Initial website"
   git remote add origin git@github.com:Daniel-Trujillo/Daniel-Trujillo.github.io.git
   git push -u origin main
   ```
3. In the repo settings → **Pages**, set **Source: GitHub Actions**. The included workflow (`.github/workflows/deploy.yml`) builds and deploys automatically on every push to `main`.
4. The site will be live at **https://daniel-trujillo.github.io** (already set as `url:` in `_config.yml`). If you deploy somewhere else instead (e.g. your CSAIL web space at `people.csail.mit.edu/danieltr/`), update `url:`/`baseurl:` in `_config.yml` accordingly.

## Where things live

- Bio / homepage: `_pages/about.md`
- News items: `_news/announcement_*.md` (newest 3 show on the homepage; all show at `/news/`)
- Publications: `_bibliography/papers.bib` (`selected={true}` puts a paper on the homepage)
- Social links: `_data/socials.yml` · Name/description: top of `_config.yml`
- Photo: `assets/img/prof_pic.jpg` (full-res original kept at `headshot.jpg`, not published)
- CV: `assets/pdf/cv.pdf` + `_data/cv.yml` render a hidden page at `/cv/` — flip `nav: false` to `true` in `_pages/cv.md` to show it in the navbar

## Hidden template pages

Blog, projects, teaching, repositories, and books pages are built but hidden from the navbar (`nav: false` in `_pages/*.md`), and the template's sample posts/projects are still in `_posts/`/`_projects/` — delete them or personalize them if you ever enable those sections.

## Local preview

`./dev.sh 4001` builds the site and serves it at `http://localhost:4001/` (requires Ruby + `bundle install`).
