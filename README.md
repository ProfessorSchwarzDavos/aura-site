# Aura · Liquidity agent on Meteora

Static website for Aura (https://x.com/Auraonchainai). No build step: plain HTML files that load Preact + htm from a CDN.

| File | Page |
| --- | --- |
| `index.html` | Homepage (hero, how it works, interactive move preview, pools, safety, roadmap, FAQ, dark mode) |
| `app.html` | App: Overview, My rules, Previews, Reason log, wallet connect |
| `pools.html` | Meteora DLMM pools table with search and token filter |
| `feed.html` | Social feed / media page |
| `favicon.svg` | Aura star icon |

Contract address shown on the site: `AuraL54hWmsKiEY31Sy6hPDYhegdzA3vCKh2uTwCpLZG`

## Host on GitHub Pages

1. Create a new public repository on GitHub (for example `aura-site`).
2. Upload every file in this folder to the root of the repo, including the hidden `.nojekyll` file. (Drag and drop on the repo page works: **Add file → Upload files**.)
3. Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, then **Save**.
4. After a minute your site is live at `https://<your-username>.github.io/<repo-name>/`.
5. Custom domain (optional): in **Settings → Pages → Custom domain** enter your domain, then add the DNS records GitHub shows you at your domain registrar.

To preview locally, run `python3 -m http.server` in this folder and open http://localhost:8000 (opening the files directly with `file://` can block the module scripts in some browsers).

## Things to know before launch

- **Pool numbers** on `pools.html` are a sample snapshot. The status line says “Live” with a ticking clock, so connect Meteora's public DLMM API before launch, or change that wording.
- **Wallet connect** looks for Phantom / Solflare (`window.phantom.solana`, `window.solflare`, `window.solana`). It only reads the public address; nothing is signed.
- **Rules and the reason log** in the app are saved in the visitor's browser (localStorage) only.
- **Token badges** are lettered placeholders. Drop official logo files into the repo and swap them in if you want real logos.
- Remaining placeholders: roadmap phase dates (`[DATE]`), the reason-trail card values (`[TIME]`, `[$]`) on the homepage, and sample feed posts on `feed.html`.
- Everything is in a single file per page: markup is the `html\`...\`` template, behaviour is the `Component` class below it.
