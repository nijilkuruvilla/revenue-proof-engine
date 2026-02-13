# Testing and Launch

## Local Setup

1. Clone repo
2. Install dependencies
3. Create .env.local

SUPABASE_URL=
SUPABASE_KEY=
CLAUDE_API_KEY=
STRIPE_SECRET_KEY=

4. Run npm run dev

---

## QA Checklist

- Upload proof works
- Extraction returns valid JSON
- Proof saves
- Asset generates
- PDF downloads
- Events logged

---

## Deployment

- Push to GitHub
- Connect to Vercel
- Add environment variables
- Run migrations
- Smoke test

---

## Post-Launch Signals

Track weekly:
- Proof uploads
- Asset generations
- PDF exports

Weekly exports = wedge validation.
