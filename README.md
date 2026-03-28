# EMB Global PMS — Deployment Guide

## Files in this package

```
emb-pms/
├── index.html      ← The full app (single file)
├── vercel.json     ← Vercel deployment config
├── package.json    ← Project metadata
├── .gitignore
└── README.md
```

---

## Option 1 — Deploy via Vercel CLI (fastest)

### Step 1: Install Vercel CLI
```bash
npm install -g vercel
```

### Step 2: Login to Vercel
```bash
vercel login
```

### Step 3: Deploy
```bash
cd emb-pms
vercel --prod
```

Vercel will give you a URL like `https://emb-pms.vercel.app` — live in ~30 seconds.

---

## Option 2 — Deploy via GitHub + Vercel Dashboard (recommended for teams)

### Step 1: Push to GitHub
```bash
cd emb-pms
git init
git add .
git commit -m "EMB PMS v1.0 — initial deploy"
git remote add origin https://github.com/YOUR_ORG/emb-pms.git
git push -u origin main
```

### Step 2: Connect to Vercel
1. Go to [vercel.com](https://vercel.com) → **New Project**
2. Import your GitHub repo `emb-pms`
3. Framework Preset: **Other**
4. Build Command: *(leave blank)*
5. Output Directory: `.` (root)
6. Click **Deploy**

Done — every `git push` auto-deploys.

---

## Option 3 — Drag & Drop (no CLI needed)

1. Go to [vercel.com/new](https://vercel.com/new)
2. Drag the entire `emb-pms` folder onto the deploy box
3. Live in under a minute

---

## Custom Domain (optional)

In your Vercel project dashboard → **Settings → Domains** → add `pms.emb.global` or any domain you own.

---

## Notes

- All data persists in the browser's `localStorage` — no backend needed.
- To reset all data on a device, open browser DevTools → Application → Local Storage → clear keys starting with `emb_`.
- The app is fully self-contained in `index.html` — fonts and Chart.js load from CDN.
