# WordPower 60 Basic — Tap-to-Speak Communication Board

A faithful web replica of the **TouchChat WordPower 60 Basic – Modified Communication Board** used at school. Built for a 4-year-old AAC user: tap a button, it speaks the word.

## Features

- **60 buttons** (6 rows × 10 columns) — same words, same order, same color coding as the school board:
  - Row 1 (yellow): happy, sad, mad, please, thank you, home, bathroom, different, bad, good
  - Row 2 (blue): what, I, me, to, come, that, away, Something hurts, and, more
  - Row 3 (green): where, my, is, eat, drink, finish, get, all, some, Break
  - Row 4 (purple): who, it, can, go, help, open, put, in, look/see, on
  - Row 5 (green): here, you, do, like, play, read, stop, out, up, off
  - Row 6 (red): yes, your, no, want, take, tell, turn, watch, down, again
- **Tap to speak** — every button speaks its word instantly (Web Speech API, no server, works offline)
- **Sentence bar** — tapped words build a message; **🔊 Speak** says the whole sentence; **🗑 Clear** empties it
- **Voice picker** — choose the voice (defaults to a natural US English female voice)
- **Fullscreen button** ⛶ — for distraction-free use on a tablet
- Single-file `index.html` — open it, host it, or ship it. No dependencies, no tracking.

## Usage

Open `index.html` in any modern browser (Chrome/Edge on Windows, Safari on iPad, Chrome on Android). Tap words. That's it.

For the most "real device" feel on a tablet:
1. Open `index.html` in Chrome/Safari
2. Tap ⛶ for fullscreen
3. Add to Home Screen (browser menu) for a one-tap app icon

## Files

- `index.html` — the entire app (HTML + CSS + JS in one file)
- `for_other_ai.md` — context for AI agents working on this repo

## Notes

- Speech uses the built-in browser TTS engine — zero cost, zero API keys, works offline once the page is loaded.
- Icons are hand-drawn inline SVGs in the SymbolStix spirit (not the actual copyrighted SymbolStix artwork).
- This is a family tool, not a commercial product. No data leaves the device.
