# RunTrack

A single-page lap timer for timing a group of runners by hand at the finish line. The interface is in Lithuanian.

Open `index.html` in a phone browser (no install, no server, works offline once loaded).

1. Enter the runner numbers (`1-20`, `3 7 12`, …), the race distance and the lap length.
2. Press **Start clock** on the gun.
3. Tap a runner's number each time they cross the finish line. The last crossing is their finish time.
4. Open **Results** for positions and splits, and copy them as CSV.

Details:

- **Due next ordering.** Buttons are sorted by when each runner should next reach the line
  (last crossing + their latest lap time), so the runners about to arrive are at the top-left.
  Runners not yet seen stay at the top, so a missed runner doesn't get buried.
  While you're tapping a pack, the buttons don't move: tapped runners fade in place, and the grid
  re-sorts after 2.5 s without taps. Switch to **By number** for a fixed order.
- Compact buttons: 40 runners fit on one phone screen. Finished runners move to a strip below.
- Fractional lap counts are handled: 3000 m on a 400 m track is 7.5 laps, so the start is 200 m back
  and each runner crosses the line 8 times.
- A second tap on the same runner within 10 s (configurable) is ignored, with an option to count it anyway.
- **Atšaukti** (undo) removes the most recent tap; **Pašalinti paskutinį** in Results fixes a single runner.
- **Iš naujo** (reset) on the timing screen and **Naujas bėgimas** in Results clear all times after a second tap
  to confirm; the runner list and distance are kept.
- **Kopijuoti rezultatus** copies tab-separated text that pastes into spreadsheet cells; the downloaded CSV uses `;`
  so it opens in columns in Excel with Lithuanian settings.
- Everything is saved in the browser as you go, so a reload or accidental tab close doesn't lose the race.
- The screen is kept awake while timing, where the browser allows it.

## Deploying to GitHub Pages

`.github/workflows/pages.yml` publishes the app on every push to `main` or
`claude/runner-lap-timer-awaf2m` (or manually from the Actions tab).

One-time setup:

1. Pages on a **private** repository needs a paid GitHub plan (Pro, Team or Enterprise).
   On a free account, make the repository public instead (Settings → General → Danger Zone → Change visibility).
   Either way, the published site itself is public.
2. Settings → Pages → Build and deployment → Source: **GitHub Actions**.
3. Actions → *Deploy to GitHub Pages* → **Run workflow** (or push a commit).

The site appears at `https://<username>.github.io/RunTrack/`.

Once opened, the app is cached for offline use, and can be added to the phone's home screen
(Share → Add to Home Screen on iPhone, menu → Install app on Android).
