# BaliDream Deployment Guide

## Quick Start

The site is ready to deploy. Choose one of the options below:

### Option 1: Deploy to Vercel (Recommended)

1. **Push to GitHub**
   ```bash
   git remote add origin https://github.com/oxylok/balidream-haiku-screen.git
   git branch -M main
   git push -u origin main
   ```

2. **Connect to Vercel**
   - Go to [vercel.com/dashboard](https://vercel.com/dashboard)
   - Click "New Project"
   - Select the repository from GitHub
   - Vercel will auto-detect it's a static site
   - Click "Deploy"

3. **Your site is live!**
   - Default URL: `https://balidream-haiku-screen.vercel.app`
   - Custom domain: Set in Vercel dashboard under "Settings" → "Domains"

### Option 2: Deploy to GitHub Pages

1. **Push to GitHub**
   ```bash
   git remote add origin https://github.com/oxylok/balidream-haiku-screen.git
   git branch -M main
   git push -u origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repository settings
   - Scroll to "Pages" section
   - Select "Deploy from a branch"
   - Branch: `main` / Folder: `/ (root)`
   - Click "Save"

3. **Your site is live!**
   - URL: `https://oxylok.github.io/balidream-haiku-screen/`
   - Takes 1-2 minutes to deploy

### Option 3: Deploy to Netlify

1. **Push to GitHub** (same as above)

2. **Connect to Netlify**
   - Go to [netlify.com](https://netlify.com)
   - Click "New site from Git"
   - Select GitHub and authorize
   - Select the repository
   - Build settings:
     - Build command: (leave empty)
     - Publish directory: `.` (or leave empty)
   - Click "Deploy site"

3. **Your site is live!**
   - URL: `https://balidream-haiku-screen.netlify.app` (or custom)

## What Gets Deployed

The following files are deployed:

```
index.html           # Main page
README.md            # Project documentation
selfcheck.md         # QA report
vercel.json          # Vercel configuration
```

**Not deployed** (git ignored):
- `.git/` — Version control
- `node_modules/` — No dependencies
- `.env` — Environment variables

## Post-Deployment

### 1. Test Live Site

```bash
# Verify all links work
# Check responsive design on mobile/tablet/desktop
# Test all CTA buttons
# Verify contact form (currently static)
```

### 2. Set Up Custom Domain (Optional)

**Vercel:**
- Dashboard → Project → Settings → Domains
- Add your domain (e.g., `balidream.com`)
- Update DNS records as instructed

**GitHub Pages:**
- Repository → Settings → Pages
- Custom domain: `balidream.com`
- Check "Enforce HTTPS"

### 3. Monitor Performance

**Vercel Analytics:**
- Dashboard → Project → Analytics
- Monitor Core Web Vitals

**Google PageSpeed Insights:**
```
https://pagespeed.web.dev/?url=YOUR_LIVE_URL
```

Expected score: 85-95 (Performance, Accessibility, Best Practices, SEO)

### 4. Update Booking Integration (Next Phase)

Current form is static. To make bookings work:

1. **Backend Options:**
   - Serverless function (Vercel Functions)
   - Third-party booking API (e.g., Calendly, Acuity)
   - Email webhook (e.g., Formspree, Basin)

2. **Implementation:**
   ```html
   <form action="https://your-api-endpoint/book" method="POST">
     <!-- existing form -->
   </form>
   ```

## Environment Variables (if needed)

Create `.env` file in root (not committed to git):

```env
VITE_API_URL=https://api.balidream.com
VITE_STRIPE_KEY=pk_test_...
```

## Rollback Instructions

If deployment fails, rollback is instant:

**Vercel:** Dashboard → Deployments → Select previous version → "Redeploy"

**GitHub Pages:** Revert commit: `git revert HEAD`

## CI/CD Pipeline

The `.github/workflows/deploy.yml` file automatically:
- Triggers on push to `main` or `master`
- Runs tests (if configured)
- Deploys to GitHub Pages
- Completes in ~1-2 minutes

To enable for other platforms:
- **Vercel:** Automatically detected from `vercel.json`
- **Netlify:** Use `netlify.toml` instead

## File Structure

```
balidream-haiku-screen/
├── index.html                  # Main page
├── README.md                   # Project info
├── selfcheck.md                # QA audit report
├── DEPLOYMENT.md               # This file
├── vercel.json                 # Vercel config
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions
├── .gitignore                  # Git ignore rules
└── .claude/
    └── launch.json             # Local dev config
```

## Troubleshooting

### 404 errors on refresh (GitHub Pages)
**Issue:** Single-page app needs routing fix
**Solution:** Currently not an issue (static HTML page) but if we add JS routing later:
```json
// In vercel.json or _redirects
{
  "redirects": [
    {
      "source": "/:path*",
      "destination": "/index.html",
      "statusCode": 200
    }
  ]
}
```

### Font loading slow
**Issue:** Google Fonts over network
**Solution:** Already optimized with:
- Font preconnect headers
- `display=swap` for fallback

### Images not loading
**Issue:** Image paths incorrect
**Solution:** Currently using SVG data-URIs. When adding real images:
```html
<!-- Use absolute paths for root-relative deployment -->
<img src="/images/bali.jpg" alt="Description">
```

## Questions?

See `README.md` for project overview or contact Oliver at oliverxhaddo@gmail.com

---

**Last Updated:** 2024-07-04  
**Deployment Ready:** ✅ Yes
