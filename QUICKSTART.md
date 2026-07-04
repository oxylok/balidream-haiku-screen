# 🚀 BaliDream — 5-Minute Live Deployment

## Step 1: Prepare Git Repository (1 min)

```bash
cd /Users/iles/Claude\ Code\ site-factory-experiments/balidream-haiku-screen

# Verify files
ls -la index.html README.md selfcheck.md

# Check git status
git log --oneline
# Should show 4 commits
```

## Step 2: Push to GitHub (2 min)

### If repository doesn't exist yet:

```bash
# 1. Create new repo at github.com/oxylok/balidream-haiku-screen
#    (Public or Private - your choice)

# 2. In terminal:
git remote add origin https://github.com/oxylok/balidream-haiku-screen.git
git branch -M main
git push -u origin main
```

### If repository already exists:

```bash
git push origin main
```

## Step 3: Deploy to Vercel (2 min)

### Method A: Automatic (Recommended)

1. Go to [vercel.com/dashboard](https://vercel.com/dashboard)
2. Click **"New Project"**
3. Click **"Import Git Repository"**
4. Select `balidream-haiku-screen` from the list
5. Click **"Deploy"**
6. Wait 30 seconds for deployment
7. Get live URL from success screen

### Method B: Using Vercel CLI

```bash
# 1. Install Vercel CLI
npm install -g vercel

# 2. Deploy
cd /Users/iles/Claude\ Code\ site-factory-experiments/balidream-haiku-screen
vercel

# 3. Follow prompts (accept defaults)
# 4. Get live URL
```

## Step 4: Your Site is Live! 🎉

Your new site is now deployed at:

```
https://balidream-haiku-screen.vercel.app
```

✅ **Share this link!**

---

## Alternative: GitHub Pages (3 min)

If you don't have Vercel setup yet:

```bash
# After pushing to GitHub:

# 1. Go to github.com/oxylok/balidream-haiku-screen/settings
# 2. Scroll to "Pages" section
# 3. Select: Branch = "main", Folder = "/ (root)"
# 4. Click "Save"
# 5. Wait 1 minute
```

Your site will be at:
```
https://oxylok.github.io/balidream-haiku-screen/
```

---

## Troubleshooting

### "Repository not found"
→ Make sure the repo is created at github.com first

### "Permission denied"
→ Use `gh auth login` or check SSH keys configured

### "Deployment failed"
→ Check that `index.html` exists in the repo root

### "Want to test locally first?"
→ Open `file:///Users/iles/Claude\ Code\ site-factory-experiments/balidream-haiku-screen/index.html` in browser (but better via http server)

---

## What's Deployed

✅ `index.html` — Your complete website  
✅ `README.md` — Project docs  
✅ `selfcheck.md` — QA report  

**That's it!** No build step needed.

---

## Next Steps After Deployment

1. **Verify it's live**
   - Click the live URL
   - Test on mobile (use DevTools)
   - Click all buttons and links

2. **Customize for real**
   - Edit `index.html` to add real images
   - Update pricing, descriptions, testimonials
   - Change contact info in footer

3. **Connect booking system**
   - Choose: Calendly, Acuity, Stripe, or custom API
   - Update form action in index.html

4. **Set up custom domain** (optional)
   - Vercel: Dashboard → Settings → Domains
   - GitHub Pages: Settings → Pages

---

## Support

- 📖 Full docs: See `DEPLOYMENT.md`
- 📋 QA report: See `selfcheck.md`
- 📝 Everything: See `DELIVERY_REPORT.md`

**Questions?** Contact oliverxhaddo@gmail.com

---

**Status:** Ready to deploy ✅  
**Time spent:** ~15 minutes  
**Cost:** Free (Vercel, GitHub, Netlify all have free tiers)
