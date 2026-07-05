# tend-site

The marketing + support site for **Tend: Gentle Routines**. Plain static HTML/CSS, no
build step, no framework. Hosted free on GitHub Pages.

## Files
```
tend-site/
  index.html      Landing page (hero, features, screenshots, why-Tend, email capture)
  support.html    Support page (contact + FAQ), linked from the nav and App Store
  assets/         App icon + screenshots used by both pages
  .nojekyll       Tells GitHub Pages to serve files as-is (don't run Jekyll)
```

## Before you publish: two quick edits in `index.html`
1. **Email form:** find `YOUR_FORM_ID` and replace the whole `action="..."` URL with your
   real form endpoint from [Formspree](https://formspree.io) or [Buttondown](https://buttondown.email)
   (both free). Until then the "Notify me" button won't submit.
2. **App Store buttons:** the "Download on the App Store" links point to `https://apps.apple.com/`.
   Swap in your real app URL once the listing is live.

## Publish to GitHub Pages

### Option A: brand-new repo (recommended: gives you `…github.io/tend-site/`)
Run these from inside this `tend-site` folder. Create an empty repo named `tend-site` on
github.com first (no README), then:

```sh
git init
git add .
git commit -m "Tend landing + support site"
git branch -M main
git remote add origin https://github.com/ryansan2001-source/tend-site.git
git push -u origin main
```

Then on github.com: **Settings → Pages → Build and deployment → Source: Deploy from a
branch → Branch: `main` / `/ (root)` → Save.** Your site goes live in ~1 minute at:

```
https://ryansan2001-source.github.io/tend-site/
```

### Option B: reuse your existing `tend-legal` repo
Copy `index.html`, `support.html`, and `assets/` into that repo (it already has Pages on),
commit, and push. The landing page then lives alongside your privacy/support pages.

```sh
git add .
git commit -m "Add Tend landing + support pages"
git push
```

## Updating later
Edit the file, then:
```sh
git add .
git commit -m "Update site"
git push
```
GitHub redeploys automatically within a minute.

## Use as your App Store Connect URLs
- **Marketing URL:** `https://ryansan2001-source.github.io/tend-site/`
- **Support URL:** `https://ryansan2001-source.github.io/tend-site/support.html`

## Custom domain (optional, later)
Buy a domain (e.g. `tendapp.com`), add a `CNAME` file containing just the domain, and point
the domain's DNS at GitHub Pages. Not needed for launch; the `github.io` URL is fine.
