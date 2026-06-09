# Martins Over the Bluegrass

Professional Purple Martin gourd tower installation for the Lake Cumberland / Monticello, Kentucky area.

**Live site:** (add after first Vercel deploy)

## What's in this repo

- `index.html` — single-file, premium static marketing site (Tailwind via CDN + custom CSS)
- `images/` — all production photos (optimized JPGs)
- `vercel.json` — production-grade static hosting config (security headers, immutable image caching, SPA-friendly rewrites)
- `.vercelignore` — keeps deploys small and clean

No build step. No framework. Pure static files — deploys to Vercel in seconds.

## Local development

Any static server works:

```bash
# Python
python -m http.server 8000

# Node (if installed)
npx serve .

# Then open http://localhost:8000
```

## Deploy to Vercel

1. Push this repo to GitHub.
2. Import the repo at [vercel.com](https://vercel.com) (or run `vercel` CLI).
3. Vercel auto-detects it as a static site thanks to `vercel.json`.
4. **After first successful deploy**, update the four placeholder URLs in `index.html` (search for `YOUR-VERCEL-DOMAIN`):

   - `og:url`
   - `canonical`
   - `og:image`
   - `twitter:image`

   Replace `https://YOUR-VERCEL-DOMAIN.vercel.app` with your real production URL (e.g. `https://martins-over-the-bluegrass.vercel.app` or your custom domain).

5. Redeploy (or push again) so social cards resolve correctly.

## GitHub + folder rename note

This project was previously in a folder with a different name. The repo is now self-contained in `bluegrass-martins/`. If you previously had push problems, it was almost certainly because a parent directory had a stray `.git` (your home directory was acting as the git root). 

**To push cleanly from now on:**

```bash
cd bluegrass-martins

# Make sure we're in a dedicated repo for just this project
git init
git add .
git commit -m "Initial clean commit - Martins Over the Bluegrass site"

# Connect to your GitHub repo (example using the previous MOTB remote)
git remote add origin https://github.com/muhgits77/MOTB.git

# First push (force is usually needed if the remote had mixed history from the old folder layout)
git branch -M main
git push -u origin main --force
```

Then connect that same GitHub repo to Vercel.

## After deploy checklist

- [ ] Update the 4 `YOUR-VERCEL-DOMAIN` placeholders in index.html
- [ ] Test the contact form (it's a frontend demo only — replace with Formspree, Resend, Vercel serverless function, or email service when ready)
- [ ] Optional: add a custom domain in Vercel
- [ ] Optional: set up analytics or a real form backend

## Images

All photos in `images/` are the final curated set used on the site. Raw phone dumps and working files live outside this repo (in the old "Martins over the bluegrass" folder on Desktop if you still have it).

## Tech notes

- Uses Tailwind CSS via CDN (`cdn.tailwindcss.com`) + Font Awesome CDN for zero-config deploys.
- All navigation is hash-based (`#about`, `#gallery`, etc.).
- Lightbox, mobile menu, form demo, and scroll behavior are vanilla JS (no dependencies).
- Excellent Lighthouse scores expected on Vercel edge.

Built with care for Kentucky lake and farm properties that want beautiful, long-lasting Purple Martin housing.

---

Ready for GitHub → Vercel.
