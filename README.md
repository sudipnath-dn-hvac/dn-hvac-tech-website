# DN HVAC Tech — website

A Jekyll site for DN HVAC Tech Private Limited, built to deploy on GitHub Pages.

## What's in here

```
_config.yml          site + company data (address, GSTIN, CIN, phone, directors)
_layouts/default.html main page wrapper
_includes/            head, header, footer partials
assets/css/style.css  all styling (no build step — plain CSS)
assets/img/logo.png   transparent emblem, cropped from your office board artwork
index.html            homepage
services.html         /services/
about.html             /about/
contact.html           /contact/
404.html               custom not-found page
.github/workflows/     GitHub Actions workflow that builds & deploys on push
CNAME                  set to dnhvactech.co.in — remove this file if you don't
                        want to use the custom domain yet
```

## Run it locally

You'll need Ruby installed, then:

```bash
bundle install
bundle exec jekyll serve
```

Visit `http://localhost:4000`.

## Deploy to GitHub Pages

1. Create a new GitHub repository and push this folder's contents to the `main` branch.
2. In the repo, go to **Settings → Pages** and set **Source** to **GitHub Actions**.
   The included workflow (`.github/workflows/jekyll-gh-pages.yml`) will build
   and deploy automatically on every push to `main`.
3. **Custom domain:** a `CNAME` file is already set to `dnhvactech.co.in`. In
   your DNS provider, point that domain at GitHub Pages (an `A`/`ALIAS` record
   to GitHub's IPs, or a `CNAME` record to `<username>.github.io` for a
   subdomain) — GitHub's own Pages docs walk through this. If you'd rather
   launch first on the free `github.io` address, just delete the `CNAME` file.

## Editing content

- **Company details** (phone, email, address, GSTIN, CIN, directors) all live
  in one place: the `company:` block at the top of `_config.yml`. Change it
  there and it updates everywhere (header, footer, homepage strip, about,
  contact).
- **Page copy** is plain HTML with Liquid tags — edit `index.html`,
  `services.html`, `about.html`, `contact.html` directly.
- **Colours and type** are CSS custom properties at the top of
  `assets/css/style.css` under `:root` — change `--navy`, `--blue`, `--cyan`,
  `--ember` etc. to retheme the whole site from one place.

## Notes

- The map on the contact page uses a plain Google Maps embed URL (no API key
  needed). If the pin isn't accurate, swap the `q=` query in `contact.html`
  for a more precise address or a `maps.app.goo.gl` share link.
- No JavaScript is used anywhere — the mobile menu is a pure-CSS
  checkbox toggle, so the site stays fast and simple to maintain.
