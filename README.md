# joshbenodin.com

Static site served by GitHub Pages at https://joshbenodin.com. No build step: edit HTML, commit, push, live in about a minute.

## Layout

```
index.html            list of apps
style.css             shared styles (light/dark via prefers-color-scheme)
404.html
CNAME                 custom domain for GitHub Pages
<app-slug>/
  index.html          what the app is, pricing, links
  privacy.html        privacy policy  → App Store Connect "Privacy Policy URL"
  terms.html          terms of use    → App Store Connect "Terms of Use (EULA)" / paywall link
  support.html        FAQ + contact   → App Store Connect "Support URL"
```

## Adding an app

1. Copy `match-camera/` to `<new-slug>/` and rewrite the four pages. Keep the header nav links pointing at the new slug.
2. Add a card to `index.html` under `<ul class="apps">`.
3. Update the effective date in `privacy.html` and `terms.html`.
4. Commit and push to `main`.

URLs to paste into App Store Connect: `https://joshbenodin.com/<slug>/privacy.html`, `.../terms.html`, `.../support.html`.

## DNS (Hover)

GitHub Pages needs these records on `joshbenodin.com`:

| Type  | Host | Value                |
|-------|------|----------------------|
| A     | @    | 185.199.108.153      |
| A     | @    | 185.199.109.153      |
| A     | @    | 185.199.110.153      |
| A     | @    | 185.199.111.153      |
| CNAME | www  | hogarths-giant.github.io |

Then in the repo: Settings → Pages → Custom domain `joshbenodin.com`, and tick *Enforce HTTPS* once the certificate is issued (up to an hour after DNS propagates).
