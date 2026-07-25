# EASE 1 — conversion link hub

Static single-page site. One job: route traffic to **Buy Now** on Zellerfeld,
with UTM tags passed through for attribution. No build step.

## Files
- `index.html` — the whole site (self-contained; fonts via Google Fonts CDN)
- `images/` — product renders (ease1-side/top/sole/heel/angle.png)
- `vercel.json` — cache + security headers

## Domain
Set to **easefootwearbyryanjans.com** in the meta tags — nothing to change.

## Deploy — GitHub → Vercel (Path A, CLI)
Run from this folder:

```bash
git init && git add -A && git commit -m "EASE 1 landing"
gh repo create ease1 --public --source=. --push      # or add a remote and push

npm i -g vercel
vercel            # log in with GitHub, create/link project → preview URL
vercel --prod     # promote to production
```

Vercel settings: **Framework = Other**, no build command, **output = root**.
Linking the GitHub repo turns on auto-deploy: every push to `main` redeploys.

## Custom domain
Vercel → Project → **Domains** → add your domain → set the A/CNAME records Vercel
shows at your registrar. HTTPS is automatic.

## Using it (attribution)
Link to the hub with a channel tag; it flows through to the Zellerfeld checkout link:
`https://easefootwearbyryanjans.com/?utm_source=tiktok` → Buy button carries `utm_source=tiktok`
(+ `utm_content=<button>_<color>`). Use `tiktok`, `reddit`, `instagram`, etc.
