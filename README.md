# Turnover Cleaning Co. — website

A one-page marketing site for a holiday-let turnover cleaning business. Built as a single static `index.html` (no build step, no dependencies) — perfect for deploying on **Vercel** straight from **GitHub**.

## What's inside

```
index.html      ← the whole site (HTML + CSS + JS in one file)
vercel.json     ← Vercel config (SPA-style routing, security headers)
README.md       ← this file
```

## Deploy in 5 minutes

### 1. Push to GitHub
1. Create a new repo on GitHub (e.g. `turnover-cleaning`).
2. Upload these three files to the root of the repo (or `git clone`, copy, commit, push).

### 2. Connect to Vercel
1. Go to [vercel.com](https://vercel.com) → **Add New → Project**.
2. Import your GitHub repo.
3. Framework preset: **Other** (it's static HTML — no framework).
4. Build command: leave empty. Output directory: leave empty (root).
5. Click **Deploy**. Your site is live in ~20 seconds at `your-project.vercel.app`.

### 3. Add a custom domain
In Vercel: **Project → Settings → Domains → Add**. Buy one through Vercel or point an existing domain's DNS at Vercel. Free SSL is automatic.

## Make the contact form actually send

Right now the form shows a success toast but doesn't transmit anywhere. Two easy options:

### Option A — Formspree (zero code, free tier)
1. Sign up at [formspree.io](https://formspree.io) and create a form. You'll get an endpoint like `https://formspree.io/f/abcdwxyz`.
2. In `index.html`, find the `<form class="quote" id="quoteForm">` line and add `action="https://formspree.io/f/abcdwxyz" method="POST"`.
3. Remove the `e.preventDefault()` line in the script (or keep it and `fetch()` to Formspree for a smoother UX).
4. Submissions land in your inbox.

### Option B — Vercel serverless function
Add `/api/quote.js` and POST to it. See [Vercel docs](https://vercel.com/docs/functions/serverless-functions). More setup, but no third party.

## Things to personalise before going live

Search-and-replace these placeholders in `index.html`:

| Placeholder | Replace with |
|---|---|
| `Turnover Cleaning Co.` | your real business name (also in `<title>`, footer, nav) |
| `07700 900 000` | your phone / WhatsApp |
| `hello@turnovercleaning.co.uk` | your email |
| Postcode list in `#coverage` | the postcodes you actually cover |
| `£35`, `£12` etc. | your real starting prices |
| Testimonial names & towns | real reviews once you have them |
| `CT1–CT6` style coverage list | your actual service area |
| Brand mark "T" | your initial, or swap for an SVG logo |

## Colours & fonts

- Brand green: `--brand: #0e6a52` (change in `:root` at top of `<style>`)
- Accent gold: `--accent: #c79a3a`
- Fonts: Inter (body) + Fraunces (headings) loaded from Google Fonts

## Tech notes

- Fully responsive (mobile nav, stacked grids under 920px / 620px).
- No jQuery, no React, no build step — just one file you can edit in any editor.
- Lighthouse-friendly: lightweight, system-font fallback, lazy-loaded only via Google Fonts.
- Accessible: semantic landmarks, labelled form fields, keyboard-navigable nav.

---

Built for hosts who've been burned by no-show cleaners. Make it yours.