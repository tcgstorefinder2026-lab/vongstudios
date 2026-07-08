# Vong Studios website

Static site for **vongstudios.com** — studio homepage + the app privacy policy.
No build step; plain HTML/CSS. Deploys unchanged to GitHub Pages, Cloudflare Pages, or Vercel.

- `index.html` — studio homepage
- `privacy.html` — privacy policy for *Tiến Lên: Grand Master*
- `CNAME` — custom domain for GitHub Pages (`vongstudios.com`)

## Before publishing
- Set the **Effective date** in `privacy.html` (search `[SET BEFORE PUBLISHING]`).
- Replace the Google Play `href="#"` in `index.html` once the store listing is live.

## Deploy on GitHub Pages (with vongstudios.com)
1. Create a public repo (e.g. `vong-studios/vongstudios.com`) and put these files at its **root**.
2. Repo → **Settings → Pages** → Source: *Deploy from a branch* → `main` / root.
3. The `CNAME` file already sets the custom domain, or enter `vongstudios.com` under **Custom domain**.
4. At your DNS registrar, add GitHub's apex records:
   - `A` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - (optional IPv6 `AAAA` → `2606:50c0:8000::153`, `...8001::153`, `...8002::153`, `...8003::153`)
   - `CNAME` for `www` → `<username>.github.io`
5. Wait for the cert, then tick **Enforce HTTPS**.

Result: `https://vongstudios.com/` (home) and `https://vongstudios.com/privacy.html` (policy).
