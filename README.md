# Workout Tracker v7

A browser-based workout tracker for a 7-day program with local persistence, adaptive defaults, progress graphs, and import/export backup support.

## Features

- Day-based workout plans (Day 1 to Day 7) with reps and timer-based exercises.
- Editable defaults per day and per exercise.
- Adaptive rep defaults per day/exercise:
  - `+1` default after every `3` fully completed sessions.
  - `-1` default after every `2` skipped sessions.
- Day/Night theme toggle (default: Night) with saved preference.
- Save/edit workout history for specific day/date entries.
- Progress dashboard with:
  - Summary completion stats
  - Completion bar graph by session
  - Exercise moving line graph (average completed reps over time)
- Data tools:
  - Export JSON (with Save Picker when supported, fallback download otherwise)
  - Import JSON backup
  - Add 2 weeks of demo data for graph testing
  - Clear all local data
- Offline-ready service worker cache for app shell files.

## How to Use

1. Select a day from the day dropdown.
2. Update reps/timers and mark sets/exercises done.
3. Click `✓ DONE — SAVE WORKOUT`.
4. Open **Progress** to view summary, bars, and moving exercise graph.
5. Open **History** and use `Edit` to update a specific saved day/date.
6. Open **Data** to export/import, load demo data, or clear records.

## Export / Import Data

- Export writes JSON in this shape:
  - `{"workouts":[...],"defaults":{...}}`
- Import supports:
  - Full object format above, or
  - Direct workouts array.

## Browser Notes

- Save location picker (`showSaveFilePicker`) works in supported browsers (typically Chromium-based desktop in secure contexts).
- Unsupported environments automatically use normal file download fallback.

## Data Storage

All workout data is stored in browser `localStorage` only.
No backend/server is required.
