# Deploy Quick Reference

## Pre-deploy Checklist

- [ ] Replace `your-username` placeholder in README.md with your actual GitHub username
- [ ] Replace `YOUR-DEPLOY-URL.vercel.app` in README.md with your deploy URL
- [ ] Replace the GitHub link in `index.html` (search for `your-username`)
- [ ] Verify the disclosure banner is visible at top of page
- [ ] Test on mobile (real device, not just emulator)
- [ ] Test with iOS Smart Invert ON to confirm dark theme survives

## Option 1: GitHub Pages (most permanent)

```bash
# Create repo on GitHub (e.g. "in-the-black-time-dance")
cd /path/to/portfolio_package
git init
git add .
git commit -m "Initial commit: concept exploration"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/in-the-black-time-dance.git
git push -u origin main

# Then on GitHub:
# Settings → Pages → Source: main branch / (root) → Save
# Wait ~1 minute, your site is at:
# https://YOUR-USERNAME.github.io/in-the-black-time-dance/
```

## Option 2: Vercel (fastest, custom domain easiest)

```bash
# Install once
npm i -g vercel

cd /path/to/portfolio_package
vercel

# Follow prompts. First time will ask:
# - Set up and deploy? Yes
# - Which scope? (your account)
# - Link to existing project? No
# - Project name? in-the-black-time-dance
# - Directory? ./
# - Override settings? No

# Production deploy:
vercel --prod
```

You'll get a URL like `https://in-the-black-time-dance.vercel.app`

## Option 3: Netlify (drag and drop)

1. Go to https://app.netlify.com/drop
2. Drag the entire `portfolio_package` folder onto the page
3. Done. URL is shown immediately.

## Option 4: Notion (private viewing)

You can't deploy HTML/JS interactivity directly to Notion, but you can:

1. Deploy to Vercel first (private)
2. In Vercel project settings → "Password Protection" (Pro only)
   OR use Vercel Preview deployments with `vercel.json` access controls
3. Embed in Notion via `/embed` block

For purely document-form sharing, copy README.md content into a Notion page directly.

## Custom Domain

If you have a domain (e.g., from Awack Studio):

### Vercel
- Project → Settings → Domains → Add
- Add records to your DNS:
  - `CNAME` `subdomain` → `cname.vercel-dns.com`
  - Or `A` `@` → `76.76.21.21`

### GitHub Pages
- Settings → Pages → Custom domain
- DNS: `CNAME` → `YOUR-USERNAME.github.io`
- Wait for HTTPS certificate (15-60 min)

## SEO + Sharing Cards

The HTML already includes `og:title` and `og:description` meta tags. To get a custom share card image:

1. Take a screenshot of the v6.1 hero (1200×630)
2. Save as `og-image.png` in the root
3. Add to `<head>`:
```html
<meta property="og:image" content="https://YOUR-URL/og-image.png">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:image" content="https://YOUR-URL/og-image.png">
```

## After Deploy

- Test the live URL on real mobile (iOS Safari + Android Chrome)
- Test on a slow 3G connection (Chrome DevTools → Network → Slow 3G)
- Submit to your portfolio sites (Awwwards, CSS Design Awards, etc.) if desired
- Tag the project on social with the live URL and disclosure note

## Maintenance

This is static. There's nothing to maintain unless you want to:
- Update version (e.g., add v7 with sound)
- Add new sections / content
- Localize to English

Each change: edit, commit, push (GitHub Pages) or `vercel --prod` (Vercel).
