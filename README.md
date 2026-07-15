# Hindo Website

Static marketing site for Hindo — no build step, no dependencies.

## Files

- `index.html` — landing page (feed, Signal Points, Radio, beat marketplace teaser)
- `privacy.html` / `terms.html` — legal pages (source of truth: `docs/privacy_policy.html`, `docs/terms_of_service.html` — keep in sync)
- `styles.css` — shared styles; mirrors the app theme (black surfaces, purple `#8B5CF6` / orange `#F97316` accents, Roboto)

## Preview locally

```bash
cd website && python3 -m http.server 4321
# open http://localhost:4321
```

## Deploy

Any static host works. Easiest options:

- **Vercel:** `npx vercel website --prod` (or point a Vercel project at the `website/` subdirectory)
- **Netlify:** drag the `website/` folder into app.netlify.com/drop
- **GitHub Pages:** serve the `website/` folder from the repo settings

## Roadmap (when LLC + Stripe exist)

The beat marketplace section becomes real pages:
- Beat detail pages reading slot data (preview URL, title, artist, price) from Supabase
- Stripe Checkout for purchase
- Stripe webhook → email full track (private `full_beats` bucket) + contract PDF to buyer

That phase likely graduates this folder to Next.js — the current site's design system (styles.css) carries over.
