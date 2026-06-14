# HIT Log Book

A mobile-first, dark-themed single-page web app for tracking a 4-day
High-Intensity Training (HIT) split. Built with plain HTML5, Tailwind CSS,
and vanilla JavaScript. All data is stored in the browser's `localStorage`,
so your log persists between visits with no server or account required.

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

## Running it

It's a single static file. Either:

- Open `index.html` directly in any modern browser, or
- Serve the folder, e.g. `python3 -m http.server` then visit
  `http://localhost:8000`.

The only external dependency is the Tailwind CDN, so a network connection is
needed on first load.
