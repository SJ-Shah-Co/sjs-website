# SJ Shah &amp; Co. — Corporate Website

Static corporate website for **SJ Shah &amp; Co LLC**, a Texas limited liability company
(established 2013) that develops and operates technology and media properties and provides
consulting through its SOHUM.agency trade name.

Plain HTML + CSS + a small vanilla JS file. No build step, no dependencies.

## Structure

```
index.html         Home: hero, company facts, featured properties, pillars, company details, CTA
products.html      All properties + SOHUM.agency, with category filters
contact.html       Contact details + mailto-based contact form
privacy.html       Privacy policy
terms.html         Terms of use
robots.txt         Crawler rules + sitemap pointer
sitemap.xml        Page list for sjshahco.com
assets/
  styles.css       Design system (dark minimal; tokens at the top of the file)
  site.js          Mobile nav, scroll reveal, product filters, contact form
  logo-mark.svg    Pyramid mark (black strokes; inverted with CSS on dark)
  favicon.svg      Browser-tab icon
  og.png           1200x630 social share image
  fonts/           Self-hosted Geist (SIL OFL)
  shots/           Screenshots of each live property (WebP, 1200x750)
render.yaml        Render.com static site config
```

## Run locally

```bash
python -m http.server 8000
```

Then visit http://localhost:8000

## Deploy on Render

1. Push this repo to GitHub.
2. In Render: **New → Static Site**, connect the repo. Render also reads `render.yaml`.
   - **Build Command:** *(leave empty)*
   - **Publish Directory:** `.`
3. Add `sjshahco.com` under **Settings → Custom Domains**.

## Editing content

- **Property copy** (`products.html`, `index.html`) is taken from each live site's own
  description. If a product changes, update the copy here too so it stays accurate.
- **Screenshots** in `assets/shots/` are of each site's homepage at 1440x900. Retake and
  re-export as WebP (about 1200x750) when a site's look changes.
- **Header/footer** are repeated in every HTML file; edit all five when they change.
- **Contact email** is `hello@sjshahco.com`, used across pages, the footer and the form.
- **Contact form** opens the visitor's email client (`mailto:`). To use a hosted form
  service instead, replace the submit handler in `assets/site.js`.
- **Accent colour and surfaces** are CSS variables at the top of `assets/styles.css`.
