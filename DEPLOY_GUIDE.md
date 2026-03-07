# Caleb Akwesera — Portfolio Deployment Guide

---

## STEP 1 — Set up the Contact Form (Formspree)

Do this **first** so emails work from day one.

1. Go to **https://formspree.io** → Sign up (free)
2. Click **+ New Form** → Name it "Portfolio Contact"
3. Set the destination email to `calebakwe@gmail.com`
4. Copy your **Form ID** — looks like `xpwzknrl`
5. Open `index.html`, find this line near the bottom:
   ```js
   const FORMSPREE_ID = 'YOUR_FORM_ID';
   ```
   Replace `YOUR_FORM_ID` with your actual ID, e.g.:
   ```js
   const FORMSPREE_ID = 'xpwzknrl';
   ```
6. Save. Done — the form will now send directly to your inbox.

---

## STEP 2 — Push to GitHub

### First time setup
```bash
# Install Git if you don't have it: https://git-scm.com/downloads

# 1. Create a new GitHub account or log in at github.com
# 2. Create a new repository named:  caleb-portfolio  (public)
# 3. In your terminal / command prompt:

cd /path/to/your/portfolio-files
git init
git add .
git commit -m "Initial portfolio deploy"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/caleb-portfolio.git
git push -u origin main
```

### Enable GitHub Pages
1. Go to your repo on GitHub
2. **Settings** → **Pages** (left sidebar)
3. Source: **Deploy from a branch**
4. Branch: `main` / folder: `/ (root)`
5. Click **Save**
6. Your site will be live at:
   `https://YOUR_USERNAME.github.io/caleb-portfolio/`

---

## STEP 3 — Custom Domain (e.g. calebakwesera.com)

### A. Buy your domain
Recommended registrars (cheapest for .com):
- **Namecheap** — ~$10/yr
- **Cloudflare Registrar** — at-cost pricing
- **Google Domains** (now Squarespace)

### B. Edit the CNAME file
Open `CNAME` (included in your files) and replace the placeholder:
```
www.calebakwesera.com
```
*(Use whichever domain/subdomain you purchased)*

### C. Add DNS records at your registrar
Log into your domain registrar → DNS settings → Add these records:

| Type  | Host  | Value                          | TTL  |
|-------|-------|-------------------------------|------|
| A     | @     | 185.199.108.153                | Auto |
| A     | @     | 185.199.109.153                | Auto |
| A     | @     | 185.199.110.153                | Auto |
| A     | @     | 185.199.111.153                | Auto |
| CNAME | www   | YOUR_USERNAME.github.io        | Auto |

### D. Configure in GitHub
1. Repo → **Settings** → **Pages**
2. **Custom domain** field → type `www.calebakwesera.com` → Save
3. Check **Enforce HTTPS** (wait ~30 min after DNS propagates)

> DNS propagation takes 1–48 hours. Test at https://dnschecker.org

---

## STEP 4 — Google Analytics 4

1. Go to **https://analytics.google.com** → Create account
2. Create a **Property** → Web → enter your domain
3. Copy your **Measurement ID** — looks like `G-ABC1234567`
4. Open `index.html`, find:
   ```js
   var GA_ID = 'G-XXXXXXXXXX';
   ```
   Replace with your actual ID:
   ```js
   var GA_ID = 'G-ABC1234567';
   ```
5. Push the change to GitHub → Pages auto-deploys

Analytics will only activate after visitors **Accept** the cookie banner.

---

## STEP 5 — Update the sitemap & robots.txt

Once your domain is live, update `sitemap.xml` and `robots.txt`:
- Replace every `www.yourdomainhere.com` with your actual domain

---

## Files in this deploy package

| File | Purpose |
|------|---------|
| `index.html` | Your portfolio (the main file) |
| `CNAME` | Tells GitHub Pages your custom domain |
| `.nojekyll` | Prevents GitHub Pages from running Jekyll |
| `robots.txt` | Tells search engines how to crawl your site |
| `sitemap.xml` | Helps Google index your pages |

---

## Making updates later

Every time you update your portfolio:
```bash
git add index.html
git commit -m "Update: describe what changed"
git push
```
GitHub Pages re-deploys automatically within ~1 minute.

---

*Guide prepared for Caleb Akwesera Ndiwa · March 2026*
