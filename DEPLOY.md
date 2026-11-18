# kabalcı.com — deploy

The site is one static file: `index.html` (inline CSS + JS, fonts from Google Fonts). No build step.

Domain: `kabalcı.com` — the DNS/ASCII form is **`xn--kabalc-u9a.com`** (IDN, dotless ı).
Every DNS panel, hosting panel and CNAME file uses the `xn--` form.

## Before going live

1. Contact email: in `index.html`, find `TODO(Halil)`, set the `href` of `#mailBtn` to `mailto:<your address>`
   and remove its `hidden` attribute. Without it the only contact is GitHub.
2. Read every line once. Content comes from `Brain/10-Projects/job-research/FACTS.md`, with the
   critic-refuted wording (2026-11-13 audit) left out. If a fact changes, change it there first.

## Option A — you bought hosting from turkticaret.net too

1. Open the hosting panel (cPanel / Plesk) → File Manager → `public_html` (or `httpdocs`).
2. Upload `index.html`. Done. Turn on the free SSL (Let's Encrypt / AutoSSL) for the domain.

## Option B — domain only (free hosting on GitHub Pages)

1. Create a **public** GitHub repo (free accounts can publish Pages only from public repos), e.g. `kabalci-site`.
2. Push `index.html` and a file named `CNAME` containing one line: `xn--kabalc-u9a.com`
3. Repo → Settings → Pages → Source: `main` branch, root. Custom domain: `xn--kabalc-u9a.com`.
4. turkticaret.net → domain → DNS management:
   - `A` records for `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` for `www`: `halilkkblc.github.io`
5. Wait for DNS (minutes to a few hours), then tick **Enforce HTTPS** in Settings → Pages.

## On the CV

Print it as `kabalcı.com` but make the link `https://xn--kabalc-u9a.com`. Someone typing the
address by hand on an English keyboard will type `kabalci.com` (with a dotted i), which is a
**different domain**. Whether `kabalci.com` is free was NOT MEASURED (DNS lookup timed out on 2026-11-18).
