# Dope Wars: Perth 

Perth-themed parody of the classic *Dope/Drug Wars* 90s game.
Buy low, sell high across the suburbs, bank your cash in the CBD, dodge the heat, and
survive 30 days with the highest net worth. Created from conversation about a father named Tom, who played a similar game 30 years ago. 

**Play:** https://dope.harrys.monster

## Live leaderboard

End-of-run scores post to a shared leaderboard backed by [Supabase](https://supabase.com)

If the backend is unreachable (offline, `file://`, or not configured) the game plays
exactly as normal and just hides the leaderboard. A local high score is always kept in
`localStorage` as a fallback.

Row-Level Security allows **insert + read only**, so anyone can add and view scores but
can't edit or delete others'. Scores are client-computed, so a determined player could
forge one — acceptable for a parody game.

