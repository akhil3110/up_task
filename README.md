# Base44 Export → Local Run + Vercel Deploy

This project can run in two modes:

1. **Static website mode (no backend required)** ✅
2. **Base44 connected mode (requires Base44 env vars)**

## Run locally (no backend required)

```bash
npm install
npm run dev
```

Open the local URL shown by Vite (usually `http://localhost:5173`).

> No `.env.local` file is required for static website mode.

## Optional: Run with Base44 backend

Create `.env.local` only if you need Base44 auth/API features:

```env
VITE_BASE44_APP_ID=your_app_id
VITE_BASE44_APP_BASE_URL=your_backend_url
```

Then run:

```bash
npm run dev
```

## Build locally (production check)

```bash
npm run build
npm run preview
```

## Deploy to Vercel

### Option A: Vercel Dashboard
1. Push this repo to GitHub.
2. In Vercel, click **Add New → Project**.
3. Import the repository.
4. Keep defaults:
   - Framework preset: **Vite**
   - Build command: `npm run build`
   - Output directory: `dist`
5. Click **Deploy**.

### Option B: Vercel CLI

```bash
npm i -g vercel
vercel
vercel --prod
```

## Connect your custom domain in Vercel

1. Open your project in Vercel.
2. Go to **Settings → Domains**.
3. Add your domain (e.g. `example.com`).
4. Add the DNS records shown by Vercel at your domain provider.
   - Usually an **A** record for root (`@`) and/or **CNAME** for `www`.
5. Wait for DNS propagation, then mark primary domain in Vercel.

## Notes

- `vercel.json` is included with an SPA rewrite so client-side routes load correctly on refresh.
- If you are only deploying a marketing/informational site, you can leave Base44 env vars unset.
