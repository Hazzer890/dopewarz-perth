# Dope Wars: Perth 🦘

A Windows 98–styled, Perth-themed parody of the classic *Dope Wars* trading game.
Buy low, sell high across the suburbs, bank your cash in the CBD, dodge the heat, and
survive 30 days with the highest net worth. Goods are fictional.

**Play:** https://&lt;user&gt;.github.io/dopewarz-perth/

## Run locally

It's a single self-contained `index.html` — no build, no dependencies. Open the file
directly, or serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/index.html
```

## Live leaderboard

End-of-run scores post to a shared leaderboard backed by [Supabase](https://supabase.com)
over its REST API (plain `fetch`, no SDK — the file stays self-contained). The Supabase
URL and **publishable** key in the script are public by design and safe to commit.

If the backend is unreachable (offline, `file://`, or not configured) the game plays
exactly as normal and just hides the leaderboard. A local high score is always kept in
`localStorage` as a fallback.

Row-Level Security allows **insert + read only**, so anyone can add and view scores but
can't edit or delete others'. Scores are client-computed, so a determined player could
forge one — acceptable for a parody game.

## Tech

Vanilla HTML/CSS/JS in one file. No framework, no build step.
