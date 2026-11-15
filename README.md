# Vong Studios website

Static site for **vongstudios.com** — studio homepage + a privacy policy per app.
No build step; plain HTML/CSS. Every page shares `site.css`. Deploys unchanged to GitHub Pages, Cloudflare Pages, or Vercel.

- `index.html` — studio homepage (all three games, a For parents section, about and contact)
- `site.css` — the shared look: night sky, Fredoka headings, one accent colour per game
- `logo-nav.webp` — the logo cropped tight for the navigation bar
- `shots/` — screenshots; `cw-*.webp` are Candy Wars, `cc-*.webp` are Coin & Capsule
- `privacy.html` — privacy policy for *Tiến Lên: Grand Master*
- `terms.html` — Terms of Service for *Tiến Lên: Grand Master* (the URL given in Play Console
  → App content → trader status)
- `privacy-candywars.html` — privacy policy for *Candy Wars* (child-directed; different
  audience declaration, so it is a separate page rather than a section of the one above)
- `privacy-coincapsule.html` — privacy policy for *Coin & Capsule: Year 2 Maths*
  (child-directed, no ads; its own page for the same reason)
- `app-ads.txt` — AdMob publisher verification. One line covers **every** app under
  publisher `pub-7642464850463096`, so both games are already authorised — but each app's
  Play listing must point its developer website at `vongstudios.com` for it to be found.
- `robots.txt` / `sitemap.xml` — crawler hints; add any new page to the sitemap
- `CNAME` — custom domain for GitHub Pages (`vongstudios.com`)

## Before publishing
- Check the **Effective date** in `privacy-candywars.html` (currently 9 September 2026).
- Each policy URL must be entered in that app's Play Console listing **and** linked in-app,
  and must agree with the app's Data safety form.
- Replace the Candy Wars **“Notify me at launch”** mailto in `index.html` with its Google
  Play URL once that listing is live. (Tiến Lên already links to
  `play.google.com/store/apps/details?id=com.thirteenchampionship.game`.)

## Deploy on GitHub Pages (with vongstudios.com)
1. Create a public repo (e.g. `vong-studios/vongstudios.com`) and put these files at its **root**.
2. Repo → **Settings → Pages** → Source: *Deploy from a branch* → `main` / root.
3. The `CNAME` file already sets the custom domain, or enter `vongstudios.com` under **Custom domain**.
4. At your DNS registrar, add GitHub's apex records:
   - `A` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - (optional IPv6 `AAAA` → `2606:50c0:8000::153`, `...8001::153`, `...8002::153`, `...8003::153`)
   - `CNAME` for `www` → `<username>.github.io`
5. Wait for the cert, then tick **Enforce HTTPS**.

Result: `https://vongstudios.com/` (home), `https://vongstudios.com/privacy.html`
(Tiến Lên policy) and `https://vongstudios.com/privacy-candywars.html` (Candy Wars policy).
