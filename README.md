# Tyler Phillips — Personal Site

A single-page professional site for job applications. Plain HTML/CSS/JS — no build step,
no dependencies, no framework. Everything is self-contained in this folder.

```
index.html      all page content
styles.css      styling, light + dark themes, responsive breakpoints
script.js       theme toggle, mobile menu, scrollspy, scroll reveals, stat counters
assets/         headshot + both résumé PDFs (served as downloads)
Resumes/        original source résumés (not used by the site)
```

## Preview locally

```bash
python3 -m http.server 4321
```

Then open http://localhost:4321.

## Updating content

All copy lives in `index.html` — sections are commented (`HERO`, `ABOUT`, `EXPERIENCE`,
`PROJECTS`, `SKILLS`, `CREDENTIALS`, `CONTACT`).

When you update a résumé, replace the PDF in `assets/` keeping the same filename:

- `assets/Tyler-Phillips-Resume.pdf` — general / data & observability
- `assets/Tyler-Phillips-Resume-Splunk.pdf` — Splunk-focused

## Deploying with GitHub Desktop

The repo is already initialized with an initial commit on `main` and no remote set.

1. **File → Add Local Repository…** and choose this folder
   (`/Users/tylerphillips/Tyler_Phillips_website`).
2. Click **Publish repository**.
3. In the dialog:
   - **Name** — `Tylerp478.github.io` for a site at `https://tylerp478.github.io`.
     Any other name gives `https://tylerp478.github.io/<name>/` instead; both work,
     since every asset path in `index.html` is relative.
   - **Uncheck "Keep this code private."** GitHub Pages will not serve a private repo
     on a free account.
4. On github.com: **Settings → Pages → Source: Deploy from a branch → `main` / `root`.**
   A repo named `Tylerp478.github.io` skips this step and publishes automatically.

The site goes live about a minute later. Pushing any later commit redeploys it.

After it's live, replace the `og:image` value in `index.html` with the full absolute URL
(e.g. `https://tylerp478.github.io/assets/tyler-phillips-headshot.jpeg`) so link previews
render on LinkedIn and in email — relative paths don't resolve for preview scrapers.

### Privacy note

A public repo puts the source — including the phone number in `index.html` and both
résumé PDFs — on your GitHub profile, where it is discoverable regardless of the
`noindex` tag in the page `<head>`. To avoid that, deploy from a **private** repo via
Netlify or Cloudflare Pages, both free, instead of GitHub Pages.
