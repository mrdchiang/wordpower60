# wordpower60 — context for other AI agents

## What this is
A single-file web replica of the AAC communication board **TouchChat WordPower 60 Basic – Modified Communication Board** that David's 4-year-old son uses at school. Requested in the Chiang Family Ai Discord server (thread 1539430474022387782) — "each of these are buttons that speak the corresponding word. Plan it, collaborate… Review with each other and send to gitlab when done."

## Source of truth
The school board photo (`img_9daf439e365c.jpeg` in the Discord thread). Word order and row colors in `ROWS` (index.html) were transcribed 1:1 from that photo. DO NOT reorder or recolor rows without re-checking the photo.

Row colors (classic TouchChat pastels):
- R1 yellow `#FCEBA3`, R2 blue `#B9DCF4`, R3 green `#BEE8BE`, R4 purple `#DBCBF0`, R5 green `#BEE8BE`, R6 red `#F8C8C0`

## Architecture
- `index.html` = everything (CSS + JS + inline SVG icons). No build step, no deps, no network calls.
- Speech: `window.speechSynthesis` (Web Speech API). Tap → `speak(word)` immediately AND append to sentence array; `🔊 Speak` → `speak(sentence.join(' '))`.
- Icons: `I` object maps name → SVG body string with `%s` placeholders replaced by stroke color `#222`. Icon names in `ROWS` reference this map; empty/absent icon = text-only button.
- Voice selection persists via `localStorage['wp60-voice']`.

## Known quirks / pitfalls
- `speechSynthesis.getVoices()` is async on some browsers (esp. Chrome) — handled via `onvoiceschanged` + a load-time call. Don't remove either.
- On iOS Safari speech may require the tap to be the triggering gesture — that's the normal flow here (tap = speak), so fine.
- `100dvh` is used for the app height (mobile URL bar issues). Fallback: `height:100%` on html/body.
- Don't add external resources (fonts, CDN icons) — must work fully offline on a school-grade tablet.
- Icons are original hand-drawn SVGs, deliberately NOT the copyrighted SymbolStix set.

## Task ownership (8/18 rule)
First bot to claim a task builds it; other bots stand down to save tokens. MoreChiang claimed this build via the family bridge (`to-moredinh` inbox). MoreDinh was invited to REVIEW (not rebuild) — if she posts review notes, apply them.

## Delivery
David said "send to gitlab". GitHub repo `mrdchiang/wordpower60` exists as backup. Ask David for the GitLab repo URL/credentials if not yet pushed there.
