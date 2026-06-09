# Poker Helper — Project Notes

## What this is
Mobile-first Texas Hold'em coaching app for beginners. Single-file static app (`public/index.html`, ~2000 lines inline CSS+JS). No build step, no backend, no dependencies. Deployed to Cloudflare Pages.

## Quick orientation
- **Main app** lives in `public/index.html` — CSS in `<style>`, JS in `<script>`
- **Glossary** lives in `public/glossary.html` — standalone A–Z poker term reference, same visual style
- **6 stages**: Cards → Position → Pre-flop → Flop → Turn → River (each a progress dot)
- **Navigation**: Swipe left = forward, swipe right = back. Header has "Glossary" (top-left, opens new tab) and "New Hand" (top-right).
- **Strategy engine**: Rule-based (not random). Tiers 1-5, 7 hand-type buckets, descriptive + numeric hand evaluators, draw detection, river exhaustive enumeration.
- **Fonts**: Playfair Display (headings), Crimson Text (body), loaded via Google Fonts
- **Palette**: `--felt` greens, `--gold` accents, `--cream` text, `--red` for hearts/diamonds

## Style conventions
- Observations and advice use **terse fragments**, not full sentences
- Strategy is framed as "leans" (guidance, not commands)
- Aggressive leans show Bet/Raise sub-cases side by side
- Call leans show pot-odds guidance tied to actual draw odds
- Hand label uses `strategicLabel()` — draws override weak made hands in the headline

## Validate after edits
```bash
node -e "const fs=require('fs'); const html=fs.readFileSync('public/index.html','utf8'); const m=html.match(/<script>([\s\S]*)<\/script>/); if(m){try{new Function(m[1]);console.log('OK')}catch(e){console.log(e.message)}}"
```

## Probability figures
All 16 probability chip values were audited (June 2026) against Upswing Poker, Wizard of Odds, Card Player, Primedope, and PokerNews. All verified correct. Do not change these without re-verifying against sources.
