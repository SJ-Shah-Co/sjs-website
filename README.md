# SJ Shah &amp; Co. — Corporate Website

Static corporate website for **SJ Shah &amp; Co LLC**, a Texas limited liability company that
develops and operates technology and media properties and provides IT consulting.

Plain HTML + CSS. No build step, no dependencies.

## Structure

```
index.html         Landing page (hero, what we do, featured products, CTA)
products.html      Full portfolio + SOHUM consulting
contact.html       Contact info + mailto-based contact form
assets/
  styles.css       All styling
  logo-mark.svg    Standalone pyramid mark (currentColor, scalable)
  favicon.svg      Browser-tab icon
render.yaml        Render.com static site config
```

## Run locally

Open `index.html` directly in a browser, or serve the folder:

```bash
python -m http.server 8000
```

Then visit http://localhost:8000

## Deploy on Render

1. Push this repo to GitHub/GitLab.
2. In Render: **New → Static Site**, connect the repo.
3. Settings (Render also reads `render.yaml` automatically):
   - **Build Command:** *(leave empty)*
   - **Publish Directory:** `.`
4. Add your custom domain (e.g. `sjshahco.com`) under the site's **Settings → Custom Domains**.

## Contact form

The contact form uses a `mailto:` handler — on submit it opens the visitor's email
client with the message pre-filled to **hello@sjshahco.com**. No backend required.
To switch to a hosted form service (Formspree, Web3Forms) later, replace the
`submit` handler in `contact.html`.

## Editing content

- **Product descriptions** live in `index.html` and `products.html`. Review them for
  accuracy — copy should truthfully describe each property.
- **Contact email** is `hello@sjshahco.com`, referenced in all three pages and the footer.
- **Logo**: the mark is inline SVG (in each page's header/footer) and `assets/logo-mark.svg`.
