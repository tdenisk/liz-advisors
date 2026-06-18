# Liz Advisors — website

Marketing site for **Liz Advisors Private Limited** (parent firm) and its flagship venture **ItsProvn**. Static HTML + one shared stylesheet — no build step, no dependencies. Deploys to Vercel as-is.

## Pages
| File | URL | Purpose |
|------|-----|---------|
| `index.html` | `/` | Home — firm overview + three pillars |
| `advisory.html` | `/advisory` | Strategic Advisory |
| `distribution.html` | `/distribution` | AI Product Distribution |
| `ventures.html` | `/ventures` | Ventures & Products + **ItsProvnRank** deep-dive (`/ventures#rank`) |
| `about.html` | `/about` | The firm + Denis Thomas |
| `contact.html` | `/contact` | Consultation form (opens the visitor's email app) + direct details |
| `styles.css` | — | Shared design system (Option A — "The Institution") |
| `assets/favicon.svg` | — | LA monogram favicon |

## Design system (Option A)
- **Type:** Libre Caslon Display / Libre Caslon Text (headlines) + Archivo (UI & body) — loaded from Google Fonts.
- **Liz palette:** ink `#1A1815`, paper `#F4F1EA`, brass accent `#B08D57`.
- **ItsProvn palette:** unchanged — itsprovn.com keeps its own existing design. The Liz site only **links out** to it (external, in a new tab); it does not restyle it.
- All tokens live in `:root` at the top of `styles.css`.

## Deploy to Vercel
1. Push this folder to a GitHub repo named **`liz-advisors`** (see below).
2. In Vercel → **Add New → Project → Import** the repo.
3. Framework preset: **Other**. Build command: *(none)*. Output directory: `.` (root). Click **Deploy**.
4. **Custom domain:** Project → Settings → Domains → add `www.lizadvisors.com` (and `lizadvisors.com`). In **GoDaddy DNS**, point the domain at Vercel: add the `A` record / `CNAME` Vercel shows you (typically `CNAME www → cname.vercel-dns.com`, and an `A` record for the apex). Vercel issues SSL automatically.

## Push to GitHub
```bash
cd liz-advisors
git init
git add .
git commit -m "Liz Advisors website — Option A"
git branch -M main
git remote add origin https://github.com/<your-username>/liz-advisors.git
git push -u origin main
```

## Editing
- Copy is plain HTML — edit directly in each page.
- Global colours/spacing/type: change the variables in `:root` in `styles.css`.
- Replace the striped `[ portrait ]` placeholders (`.ph` blocks in `index.html` / `about.html`) with a real photo of Denis: drop a `<img>` in place of the `.ph` div.

## To do (content)
- The Denis Thomas portrait (`assets/denis-portrait.jpg`) is graded into the brand palette; swap in a different shot anytime by replacing that file.
- Optional: wire the contact form to a real endpoint (Formspree / Vercel serverless) instead of the `mailto:` fallback.
