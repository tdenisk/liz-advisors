# Cursor / Claude Code handoff prompt

Paste this into Cursor (or Claude Code) **inside the `liz-advisors/` folder** to continue development.

---

You are working on the **Liz Advisors** marketing website — a static, dependency-free HTML site (no framework, no build step) that deploys to Vercel. Liz Advisors is a strategic-advisory firm; **ItsProvn** is its flagship venture (a verified student-credential platform powered by *ItsProvnRank*, a patent-pending 0–1,000 admissions score).

## Ground rules
- Keep it **static HTML + one shared `styles.css`**. Do not introduce React, a bundler, Tailwind, or a build step unless explicitly asked.
- All design tokens live in `:root` in `styles.css`. Never hardcode brand colours in pages — use the CSS variables (`--ink`, `--paper`, `--brass`, etc.).
- The shared header, footer and nav markup are repeated in each Liz page; if you change one, change all (or extract a small JS include — but only if asked).
- **ItsProvn (itsprovn.com) is a separate, existing site — do not restyle it.** The Liz site only links out to `https://www.itsprovn.com` (external, new tab). ItsProvn is described on the Ventures page; there is no local ItsProvn page.

## Design system (Option A — "The Institution")
- **Headlines:** Libre Caslon Display / Libre Caslon Text. **UI & body:** Archivo. (Google Fonts.)
- **Liz accent:** brass `#B08D57`. **ItsProvn accent:** verified-green `#0E8F6B`.
- Institutional register: generous whitespace, hairline rules, numbered structure, one accent per surface. No gradients, no emoji, no rounded corners on the Liz pages (ItsProvn may use rounded cards/pills).

## Likely next tasks
1. Swap the Denis Thomas portrait (`assets/denis-portrait.jpg`) if a new photo is provided — it's a 3:4 image graded to the brand palette.
2. Wire `contact.html`'s form to a real endpoint (Formspree or a Vercel serverless function) instead of the current `mailto:` fallback.
3. Add Open Graph / Twitter meta + an `og-image` per page. *(done — `assets/og-image.jpg`, tags in every page head.)*
4. `sitemap.xml` and `robots.txt`. *(done.)*

## Deploy target
GitHub repo `liz-advisors` → Vercel (framework: Other, no build, output `.`) → custom domain `www.lizadvisors.com` via GoDaddy DNS. ItsProvn lives at `www.itsprovn.com` and is linked both ways.

Read `README.md` and `styles.css` first, then make changes page by page. Preserve the existing copy unless asked to revise it.
