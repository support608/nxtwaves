# NxtWaves — Clinical Intelligence UI

A minimal, production-ready React landing page for NxtWaves — a recruiter-paid platform delivering precision-vetted talent in AI, Healthcare and Engineering.

## Features
- Accessible, minimalist "Clinical Intelligence" design
- SEO: `react-helmet` + Schema.org JSON-LD (Service + offers + contactPoint)
- Responsive Bento-grid (3 pillar cards)
- Tailwind CSS with a custom `rounded-custom-24` radius
- Framer Motion micro-animations and Lucide icons
- Pre-configured for Vercel deployment

## Quick start
1. Install
   npm install

2. Dev server
   npm run dev

3. Production build
   npm run build

4. Preview production build locally
   npm run preview

## Code quality & deploy
- CI: GitHub Actions workflow (`.github/workflows/ci.yml`) runs `npm ci` + `npm run build` on pushes and PRs to `main`.
- Vercel: connect the GitHub repository to Vercel — build command `npm run build`, output directory `dist` (or use `vercel.json`).

## Deployment to Vercel (short)
1. Push repo to GitHub.
2. Sign in to Vercel and "Import Project" → select the repo.
3. Set Framework Preset to "Vite" (Vercel usually auto-detects).
4. Build command: `npm run build` — Output directory: `dist`.
5. Add your custom domain in Vercel Dashboard → follow DNS instructions.

## Optional: Deploy to Cloudflare Pages / Workers
If you prefer Cloudflare Pages + Workers (edge-first hosting), use one of these options:

- Cloudflare Pages (recommended for static SPA): Connect GitHub repo in Cloudflare Pages, set build command `npm run build` and output directory `dist`.

- Wrangler / Workers (serve pre-built assets via Wrangler): A `wrangler.jsonc` is included in this repo — it points `assets.directory` to `./dist`. To deploy with Wrangler:

  1. npm i -g wrangler
  2. npx wrangler login
  3. npx wrangler deploy --assets=./dist

Notes:
- Cloudflare Pages provides a direct GitHub integration (automated builds). Wrangler is useful if you want a Worker to serve the `dist` bundle or need custom edge logic.
- `wrangler.jsonc` is provided so `wrangler deploy --assets=./dist` will upload the pre-built static assets.

## Notes before publishing
- Update `package.json.repository.url` to point to your GitHub repo.
- Replace placeholder social URLs in `src/App.jsx` with real profiles.
- Consider adding OG images and more JSON-LD entries (Organization, JobPosting) if you publish jobs.

## Maintainer
- NxtWaves — frontend scaffold for marketing & lead capture
