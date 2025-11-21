# URL Shortener (React + Vite)

Simple URL shortener built with React, Vite and Supabase.

**Project Layout**
- `src/` — React source
- `public/` — static files (includes `_redirects` for Netlify)
- `dist/` — production build output
- `src/db/` — Supabase API helpers

**Quick Start**

- Install dependencies:

```powershell
npm install
```

- Local development:

```powershell
npm run dev
```

- Build for production:

```powershell
npm run build
```

**Environment**
- Copy and edit `.env` (already present in workspace). Required keys:
	- `VITE_SUPABASE_URL` — your Supabase project URL
	- `VITE_SUPABASE_KEY` — anon/public key
	- `VITE_BASE_URL` — (optional) base domain for displayed/copyable short URLs. Example: `https://shorturlbit.netlify.app`

The app reads `VITE_BASE_URL` at build/runtime and falls back to `window.location.origin` when not set.

**Netlify (SPA) configuration**
- To allow direct links like `https://shorturlbit.netlify.app/abc123` to load the single-page app (so the client router can redirect), the repo includes `public/_redirects` with the rule:

```
/*    /index.html   200
```

This file is copied into `dist/` at build time and Netlify will serve `index.html` for all routes.



#
