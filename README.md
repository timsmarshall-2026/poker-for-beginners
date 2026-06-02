# Hold'em Helper

A mobile-first Texas Hold'em coaching tool for beginners. Pure static HTML/CSS/JS — no build step, no backend, no dependencies. Works offline.

## Local Preview

Just open the file directly in your browser:

```
open public/index.html
```

Or use a local server:

```
npx serve public
```

Then visit `http://localhost:3000`.

## Deploy to Cloudflare Pages

### Via GitHub

1. Push this repo to GitHub:

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/holdem-helper.git
git push -u origin main
```

2. Go to [Cloudflare Pages](https://pages.cloudflare.com/)
3. Click **Create a project** > **Connect to Git**
4. Select your repository
5. Configure the build:
   - **Build command:** _(leave blank)_
   - **Build output directory:** `public`
6. Click **Save and Deploy**

Your site will be live at `https://holdem-helper.pages.dev` (or your chosen subdomain).

### Direct Upload

Alternatively, drag and drop the `public/` folder in the Cloudflare Pages dashboard.

## How It Works

- **Stage 1:** Pick your two hole cards (rank + suit)
- **Stage 2:** Choose your table position
- **Stage 3:** Get a pre-flop read with observations, odds, and a suggested lean
- **Stage 4–5:** Add community cards (flop, turn, river) for street-by-street coaching

All strategy advice is rule-based (not random) and framed as "leans" — real decisions depend on bet sizes, opponents, and pot odds.
