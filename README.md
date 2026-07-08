# HIT Log Book & Nutrition Log

Two mobile-first, dark-themed single-page web apps: a 4-day
High-Intensity Training (HIT) log book (`index.html`) and a daily
calorie & macro tracker (`nutrition.html`), cross-linked in each
other's headers. Built with plain HTML5, Tailwind CSS, and vanilla
JavaScript. All data is stored in the browser's `localStorage`, so your
logs persist between visits with no server or account required.

## The split

| Day | Session | Focus |
| --- | --- | --- |
| Mon | Upper A | Bench, Pendlay Row, OHP, Weighted Pull-Ups, Flyes, Curls, Skulls |
| Tue | Lower A | Back Squat, RDL, Leg Press, Leg Curls, Calf Raises, Hanging Raises |
| Thu | Upper B | Incline DB Press, DB Row, Cable Row, Laterals, Incline Curls, Tricep Ext |
| Fri | Lower B | Deadlift, Bulgarian Split Squat, Leg Ext, Calf Raises, Cable Crunches |

## Features

- **Carry-Forward targets** — when you log a new week, each exercise shows
  the exact weight × reps you hit in the *previous* week's matching session
  as a green "target" line above the inputs, so you always know what to beat.
- **Week switching** — dropdown plus prev/next arrows; "+ Add week" / "Start
  next week" creates the next training week.
- **2 working sets per exercise** with separate Weight (kg) and Reps inputs.
- **HIT failure cues** — heavy compound lifts (Bench, Squat, RDL, Deadlift)
  carry a pulsing 🔥 "To failure" badge as a reminder to push to true
  technical failure.
- **Session notes** — a per-session text area for sleep, energy and recovery.
- **Autosave** — every keystroke is saved to `localStorage` immediately.
- **Export / Import** — back up or move your data as a JSON file (handy since
  `localStorage` is tied to one browser on one device).

## Nutrition Log (`nutrition.html`)

A flat, chronological daily food log with three views — **Log**, **Foods**,
**Targets** — designed to sit alongside the training log book.

- **Describe a meal (automatic macros)** — type a meal in plain English
  ("2 mince beef patties and one sweet potato") and the app parses
  quantities and food names — tolerating plurals and misspellings — and
  pulls calories and macros automatically. Review each matched item,
  adjust quantities or swap matches, then log the whole meal in one tap.
- **Built-in food database** — ~230 common whole foods (meats, fish,
  eggs, dairy, grains, potatoes, legumes, vegetables, fruit, nuts,
  sauces, supplements) embedded in the app with per-100 g macros and
  typical serving sizes. Fully offline, no API or signup.
- **Saved meals** — save a reviewed meal under a name and re-log the
  whole thing in one tap later, with optional scaling (e.g. 2× the
  meal). Meals snapshot their macros, so later edits to your food
  library never rewrite them.
- **Personal food library** — save a food once (per-100 g or per-serving
  macros); after that, logging is two taps: pick it, enter grams or
  servings. Your saved foods take priority over the built-in database
  when a meal description matches both. One-off "Quick add" entries
  cover foods not worth saving.
  Kcal auto-fills from macros (4 / 4 / 9) but can be typed over to match
  a label. Entries snapshot their macros, so editing or deleting a
  library food never rewrites logged history.
- **Daily totals & targets** — big kcal total with remaining/over, plus
  progress bars for calories, protein, carbs, and fat against your
  targets.
- **Target calculator** — suggests targets from bodyweight and goal:
  33 kcal/kg (+300 bulk / −500 cut), protein 2 g/kg (2.2 on a cut),
  fat 0.9 g/kg, carbs fill the remainder. One tap applies the result.
- **Date navigation** — prev/next day arrows, a date picker, and a
  "Today" shortcut; past days remain fully editable.
- **Autosave + Export/Import** — same pattern as the log book, stored
  under its own `localStorage` key (`nutritionLog.v1`), fully isolated
  from the training data (`hitLogBook.v1`).

## Running it

Both apps are static files. Either:

- Open `index.html` (training) or `nutrition.html` (nutrition) directly
  in any modern browser, or
- Serve the folder, e.g. `python3 -m http.server` then visit
  `http://localhost:8000`.

The only external dependency is the Tailwind CDN, so a network connection is
needed on first load.
