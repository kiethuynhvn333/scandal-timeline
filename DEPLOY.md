# Deploy to GitHub Pages — Step-by-step

## What's in this folder

| File | Purpose |
|------|---------|
| `index.html` | The complete site — 100% self-contained, no build step needed |

External dependencies (loaded from CDN, no install required):
- **Google Fonts** — Playfair Display, Inter, JetBrains Mono
- **Chart.js 4.4.1** — cdnjs.cloudflare.com

---

## Step 1 — Create a GitHub repo

1. Go to https://github.com/new
2. Name it something like `scandal-timeline` or `nghe-si-ma-tuy`
3. Set it to **Public** (required for free GitHub Pages)
4. Leave "Add a README" **unchecked** — we'll push our own files
5. Click **Create repository**

---

## Step 2 — Push this folder

Open Terminal, `cd` into this `deploy/` folder, then run:

```bash
cd "/path/to/scandal timeline/deploy"

git init
git add .
git commit -m "initial deploy"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git push -u origin main
```

Replace `YOUR_USERNAME` and `YOUR_REPO_NAME` with your actual GitHub username and repo name.

---

## Step 3 — Enable GitHub Pages

1. Go to your repo on GitHub
2. Click **Settings** (top tab bar)
3. Scroll down to **Pages** (left sidebar)
4. Under **Source**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**

---

## Step 4 — Your site is live

GitHub will show a banner:

> ✅ Your site is published at `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`

It usually takes **30–90 seconds** to go live after the first push.

---

## Updating the site later

Whenever you edit `index.html`, just push again:

```bash
git add index.html
git commit -m "update: describe your change"
git push
```

GitHub Pages will redeploy automatically within ~30 seconds.

---

## Optional: custom domain

If you have a domain (e.g. `scandal.yourdomain.com`):

1. In **Settings → Pages**, enter your custom domain
2. GitHub will create a `CNAME` file in the repo automatically
3. At your DNS provider, add a CNAME record:
   - Name: `scandal` (or whatever subdomain)
   - Value: `YOUR_USERNAME.github.io`
4. Wait for DNS propagation (minutes to hours)
