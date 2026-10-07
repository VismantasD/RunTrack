# RunTrack

A single-page lap timer for timing a group of runners by hand at the finish line.

Open `index.html` in a phone browser (no install, no server, works offline once loaded).

1. Enter the runner numbers (`1-20`, `3 7 12`, …), the race distance and the lap length.
2. Press **Start clock** on the gun.
3. Tap a runner's number each time they cross the finish line. The last crossing is their finish time.
4. Open **Results** for positions and splits, and copy them as CSV.

Details:

- Fractional lap counts are handled: 3000 m on a 400 m track is 7.5 laps, so the start is 200 m back
  and each runner crosses the line 8 times.
- A second tap on the same runner within 10 s (configurable) is ignored, with an option to count it anyway.
- **Undo** removes the most recent tap; **Remove last** in Results fixes a single runner.
- Everything is saved in the browser as you go, so a reload or accidental tab close doesn't lose the race.
- The screen is kept awake while timing, where the browser allows it.
