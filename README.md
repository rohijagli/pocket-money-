# Sprout 🌱

Automated pocket money for teens — recurring allowance, savings jars, and chores tied to payment, with separate parent and teen views.

## Run locally

```bash
npm install
npm run dev
```

Opens at `http://localhost:5173`.

## Build for production

```bash
npm run build
```

Outputs a static site to `dist/`. Preview it locally with `npm run preview`.

## Deploy

This is a static Vite app — deploy `dist/` (or connect the repo) to any static host:

- **Vercel**: `npx vercel` (auto-detects Vite) or connect the GitHub repo at vercel.com — build command `npm run build`, output dir `dist`.
- **Netlify**: `npx netlify deploy --prod` or connect the repo — build command `npm run build`, publish dir `dist`.
- **GitHub Pages / Cloudflare Pages**: same build command/output dir as above.

## What's here

- Parent and Teen views (toggle in the header)
- Savings jars visualized as growing plants — the fill % drives stem height, leaf count, and bloom
- Chores: teen marks done → parent approves/rejects → balance updates
- Allowance: configurable amount/frequency, manual "run payout now", or simulate days passing
- Activity feed of recent transactions
- State persists to `localStorage` (`sprout-app-state-v1`) so a refresh doesn't lose progress
- Error boundary with a friendly fallback + reload

## Not yet wired up

This is a front-end prototype with local state — no backend, auth, or real payments yet:
- No login (single hardcoded "Alex" teen profile)
- No real bank/payment integration (that's the next stage — was scoped for Plaid sandbox)
- No multi-teen or multi-parent support
- `localStorage` is per-browser, not shared between parent and teen devices

## Stack

React 19 + Vite, [lucide-react](https://lucide.dev) for icons, no CSS framework — plain inline styles + design tokens (see top of `src/App.jsx`).
