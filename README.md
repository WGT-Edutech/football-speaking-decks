# Football English — Speaking & Grammar Decks

Single-file ESL slide decks for football fans. One teacher, one student at a time.

## Live

Portal: `https://wgt-edutech.github.io/football-speaking-decks/`

## Decks

| Deck | Level | Slides | Focus |
|---|---|---|---|
| `european-football-week.html` | B2+ | 30 | 20 open conversation questions on European football news |
| `match-day-grammar.html` | B1 | 13 | Grammar in match-day situations — adjectives, articles, *will* / *going to*, present simple vs continuous |

## How the decks work

Every deck is one self-contained HTML file. No build step, no dependencies, no server.

- **Navigation** — `Space` / `→` next, `←` previous, or the bottom buttons.
- **Vocabulary** — click a dotted-underline word for its definition (in English, not translated).
- **Model answers** — "Reveal Model Answer" toggles a sample response for every question.
- **Completion** — "Mark as Completed" writes to `localStorage` under the key `ielts-progress`, keyed by each deck's `deckSlug`. The portal reads the same key and shows how many decks you have finished on that device.
- **Theme + sound** — the theme cycler and sound toggle also persist in `localStorage`.

## Adding a future deck

1. Build the deck as a single `.html` file using the same structure (dark theme, `data-slide` sections, bottom nav, a unique `deckSlug`).
2. Drop it in this folder next to `index.html`.
3. Add one object to the `DECKS` array at the top of the `<script>` in `index.html` — the card grid is generated from that array, so no HTML edits are needed. `slug` must match the deck's own `deckSlug` so completion state lines up.
4. Set the deck's home link to `index.html` so its "Back to Portal" button returns here.
5. Commit and push to `main`; GitHub Pages rebuilds within a few minutes.

## Verifying a change

```bash
node --check <(sed -n '/<script>/,/<\/script>/p' index.html | sed '1d;$d')   # JS parses
grep -c "<body>" index.html                                                # must be 1
```

Then poll the live URL for a unique marker string from the new commit before reporting it live.

## Notes

- Both decks load their photography from Pexels and their fonts from Google Fonts, so they need a network connection on first load.
- No analytics, no tracking, no accounts.
