# 🚀 Cloudflare Pages Deployment Guide

## Option 1: Deploy via GitHub Integration (Recommended)

1. Go to [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. Navigate to **Workers & Pages** → **Create Application** → **Pages**
3. Click **Connect to Git**
4. Select repository: `profastpage/Velocity-kicks`
5. Configure build settings:
   - **Production branch**: `main`
   - **Build command**: `echo 'Static site - no build required'`
   - **Build output directory**: `.` (root)
6. Click **Save and Deploy**

✅ Cloudflare will automatically deploy on every push to `main`

---

## Option 2: Deploy via CLI (Direct)

### First time setup:
```bash
# Install Wrangler (already installed)
npm install -g wrangler

# Login to Cloudflare
wrangler login
```

### Deploy to Cloudflare Pages:
```bash
# Deploy to production
wrangler pages deploy . --project-name=velocity-kicks --branch=main
```

### Create project first (if needed):
```bash
wrangler pages project create velocity-kicks
```

---

## Option 3: Using npm script

```bash
npm run deploy
```

---

## Automatic Deployments

Once connected to GitHub:
- ✅ Push to `main` → Auto-deploy to **Production**
- ✅ Push to other branches → Auto-deploy to **Preview**

---

## Environment Variables (if needed)

Add in Cloudflare Dashboard:
- **Settings** → **Environment Variables** → **Add Variable**

---

## Custom Domain

1. Go to **Workers & Pages** → **velocity-kicks**
2. **Custom Domains** → **Set up a custom domain**
3. Follow DNS configuration instructions

---

## Status

✅ Wrangler CLI installed
✅ Configuration files added (package.json, wrangler.toml)
✅ Ready for deployment
