# Flashcard Maker

A free, single-file flashcard app for learning word pairs (vocabulary,
translations, definitions, anything two-sided). No sign-up required.
Personal decks are stored in the browser's `localStorage`; shared decks are
persisted in Firestore (see "Cloud sharing" below).

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
- **Share via link** — clicking "Share" uploads the current deck to
  Firestore and gives back a short link (`?deck=<id>`); opening that link
  loads the deck for anyone, no account needed. Falls back to a
  copy-pasteable offline code if Firestore is unreachable.
- **Dark/light theme toggle.**
- **Localized UI** — auto-detects the browser's language and shows menus
  in one of ~20 languages.

## Cloud sharing

Shared decks are stored in a Firebase project (Firestore, `decks`
collection). Each shared deck is a write-once document — anyone can create
one via "Share" and anyone can read one via a share link, but existing
decks can't be edited or deleted (see `firestore.rules`), since there's no
auth to tell owners apart. If you fork this and stand up your own Firebase
project, paste your own `firebaseConfig` into `index.html` and publish
`firestore.rules` in the Firestore console's Rules tab.

Published automatically via GitHub Pages on every push to `main`.
