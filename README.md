# Flashcard Maker

A free, single-file flashcard app for learning word pairs (vocabulary,
translations, definitions, anything two-sided). No sign-up, no backend —
everything runs client-side and decks are stored in the browser's
`localStorage`.

## Features

- **Deck editor** — a spreadsheet-style table for entering word pairs, with
  custom column names for each side (e.g. "Polish" / "Dutch").
- **Paste-to-import** — paste a list of `word — translation` pairs (one per
  line) and it splits them into cards automatically.
- **Auto-translate** — if the two column names are recognized language
  names (e.g. "English" / "French"), cards with an empty second side are
  auto-translated via the free MyMemory translation API.
- **Study mode** — flip-card or type-the-answer modes, studying in either
  direction (A → B or B → A).
- **Spaced repetition-style weighting** — cards rated "Bad" reappear more
  often than "Alright" or "Perfect", with a shuffle that keeps repeats
  spaced apart.
- **Save/load multiple decks**, each with its own progress, stored locally.
- **Share via code** — encodes a deck into a copyable text code that
  others can paste in via "Import code" (no server round-trip).
- **Dark/light theme toggle.**
- **Localized UI** — auto-detects the browser's language and shows menus
  in one of ~20 languages.

Published automatically via GitHub Pages on every push to `main`.
