# Decoder Ring Generation Edition

Free, no-login decoder ring that turns teen and kid slang into plain English for parents. Definitions are paraphrased from named dictionary and news pages — not invented.

**Web / PWA is the shippable product.** Apple and Google stores need a later native wrap — see `STORE.md`.

## Stack

Next.js 16 (App Router) · React 19 · Tailwind 4 · Drizzle · PostgreSQL

Saved terms live in `localStorage` (`jargon-decoder-saved-v1`). There is no auth.

## Setup

```bash
cp .env.example .env
npm install
npx drizzle-kit push --force
pip install edge-tts   # optional, better Play audio
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

Production:

```bash
npm run build
npx next start -H 0.0.0.0 -p 3000
```

## Legal (required for stores)

- `/legal/privacy`
- `/legal/terms`
- `/legal/content` — rating answers (12+ / Teen, not Kids)

Replace `YOUR-DOMAIN` in `STORE.md` before you file.

## Install on a phone

HTTPS + this PWA: Safari → Share → Add to Home Screen, or Chrome → Install app.

## License

App code is yours to publish. Glossary text is paraphrased from the cited `sourceUrl` on each term.
