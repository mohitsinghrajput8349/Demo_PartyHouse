# Utsav Wholesale Bazaar (demo)

A demo storefront for an Indian party-supplies wholesaler/retailer — balloons, candles,
toffees, mithai, birthday and party decor — with retail/wholesale pricing and a mock
admin dashboard.

## Run it locally

```bash
npm install
npm run dev
```

Then open the URL Vite prints (usually http://localhost:5173).

## Deploy to Vercel via GitHub

1. **Push this folder to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Utsav Wholesale Bazaar demo"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```

2. **Import into Vercel**
   - Go to vercel.com and sign in (GitHub login is easiest).
   - Click **Add New → Project**.
   - Select the GitHub repo you just pushed.
   - Vercel auto-detects this as a Vite project — leave the defaults:
     - Build command: `vite build`
     - Output directory: `dist`
   - Click **Deploy**.

3. Vercel gives you a live URL in about a minute, and redeploys automatically every
   time you push to `main`.

## Important limitation to know before showing a client

This demo persists the product catalog and orders in the browser's `localStorage`.
That means:
- Data survives a page reload on the **same browser**.
- It is **not shared** between different visitors or devices — each person who opens
  the site gets their own local copy of the catalog/orders.
- Admin sign-in (`admin` / `admin123`) is a hardcoded demo credential, not real auth.

This is fine for a client walkthrough or portfolio demo. For a real production site,
the next step is to replace the `loadShared`/`saveShared` functions in `src/App.jsx`
with calls to a real backend (e.g. a database + API, or a service like Supabase/Firebase),
and to replace the mock login and mock payment gateway with real providers.
