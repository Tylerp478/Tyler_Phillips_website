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

## Deploying

The site is static, so any static host works free.

**GitHub Pages** — create a repo named `Tylerp478.github.io`, push this folder to it,
and it publishes at `https://tylerp478.github.io`.

```bash
git init && git add . && git commit -m "Personal site"
git remote add origin https://github.com/Tylerp478/Tylerp478.github.io.git
git push -u origin main
```

**Netlify / Cloudflare Pages** — drag this folder onto their dashboard. No build command,
publish directory `.`.

Once it's live, update the `og:image` URL in `index.html` to the absolute hosted URL so
link previews render on LinkedIn.
