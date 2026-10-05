# Deep DNA Tracker

**Beta v1.01 · by mr.xzu**

An unofficial browser-based DNA progress tracker for **Creatures of the Deep**. Track your samples, choose your next target and find catch guidance in one place.

## Features

- Track DNA percentages for **300 entries** covering fish, creatures and monsters.
- Browse nine non-VIP locations with species thumbnails and guide links.
- Search by name and filter by location, rarity or completion status.
- Sort by name, rarity or estimated difficulty, easiest or hardest first.
- Open concise catch tips with scarcity notes, practical suggestions and source links.
- Choose your next DNA target using location, map area, day/night and seasonal month.
- Adjust DNA in **5% or 25% increments**, or enter a percentage directly.
- Mark a recommended sample complete and move to the next suggestion, with session Undo.
- Import percentages from a screenshot or photo and review them before saving.
- View milestone rewards at **50%, 75% and 100%** completion.
- Save progress locally and export/import JSON backups.

## Quick start

1. Download [deep_dna_tracker_beta_v1.01.html](deep_dna_tracker_beta_v1.01.html).
2. Open it in a modern browser with JavaScript and local storage enabled.
3. Select a location and species category, then enter your DNA percentages.

The app is a single HTML file containing its styles, scripts and images. There is no build step, account or backend. Core tracking can work offline; photo recognition downloads its reader and needs an internet connection. External guides also require internet access.

For more consistent browser storage behaviour, serve the file from a static web server. If Python is installed, run this in the repository folder:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000/deep_dna_tracker_beta_v1.01.html`.

## Progress and backups

Progress is saved in the current browser's `localStorage`. There is **no automatic sync** between devices, browsers or game accounts.

- **Export progress** downloads `deep-dna-progress.json`.
- **Import progress** replaces the current progress with the selected JSON backup.
- Export before clearing browser data, changing browsers or moving to another hosted copy.

Storage for directly opened local files varies between browsers. Keep backups, especially when updating or moving the HTML file. The app retains the `deep-dna-progress-v1` storage key used by earlier versions.

Overall completion measures entries with **100% DNA**, rather than averaging all individual percentages.

## Next best DNA sample

Select **Next best DNA sample**, then choose your current game location, optional map area and target category. Your in-game position is selected manually.

Automatic time uses your device clock, with day targets eligible from **04:00–20:00** and night targets from **20:00–04:00**. You can override day/night, adjust the clock by one hour in either direction and choose the seasonal month manually.

Recommendations prioritise:

1. Species matching your selected location, area, category and time.
2. In-season species, or only in-season species when that filter is enabled.
3. Samples closest to completion.
4. Lower in-game rarity when other priorities tie.

The difficulty sort changes the species list; it does **not** change the recommendation algorithm. Recommendations use stored guide data, not live spawn detection. Seasonal activity may affect catch sizes and does not guarantee a spawn.

**Caught enough — complete & next** saves the selected entry at 100% in this tracker. You must still complete the DNA submission in the game. Undo restores the previous percentage during the current session.

## Difficulty and scarcity

Difficulty is an **estimate**, not an official game statistic.

- **26 species** have species-specific scarcity estimates drawn from player reports.
- **13 of those** have supporting reports from a second player thread.
- Other species use in-game rarity plus time and seasonal restrictions.
- Ratings describe estimated encounter difficulty, not the difficulty of the reeling minigame.
- Reliable numerical spawn percentages have not been found.

The labels **Elusive**, **Very elusive** and **Exceptionally elusive** reflect qualitative community reports. Multiple reports support scarcity, but do not validate the exact tier or establish a measured catch rate. Older reports may be affected by game updates.

Tap **Catch tips** on a species or recommended target to view short advice and evidence links. Scarcity research was last updated on **5 October 2026**.

## Photo import

1. Select **Import photo** and choose the location shown in your image.
2. Choose a clear screenshot or photo, preferably cropped to the DNA list.
3. Select **Read photo**.
4. Check the matched species and percentages; correct any errors.
5. Select the rows to import and save the selected percentages.

Recognition uses **Tesseract.js 6.0.1** in the browser. Only visible names and percentages can be read. Similar species names and digits can be misread, so review every result before saving. The selected image is processed by the browser; the reader and language resources are downloaded from external services.

## Locations

Marina · Paradise Island · Great Lakes · Costa Rica · Alaska · Australia · Scotland · Thailand · Amazon

VIP areas are excluded from this beta's DNA coverage.

## Repository files

```text
README.md
deep_dna_tracker_beta_v1.01.html
```

Keep both files in the repository root so the download link above works. The app can be served by static hosting without a build process. This README does not assume an existing live deployment.

## Feedback

Please report bugs and data corrections through GitHub Issues. Include:

- Browser, device and app version.
- Steps to reproduce the problem, with expected and actual behaviour.
- Species and map for data corrections.
- A screenshot or source link where useful.

For scarcity reports, include the game version, location, time, bait/perks and number of attempts or fishing duration where possible. A long unsuccessful search alone cannot establish a spawn percentage.

## Sources and credits

- [CloverSalad](https://cloversalad.com/) — species locations, thumbnails, seasonal information and guides.
- [CloverSalad skill guide](https://cloversalad.com/guides/skill-tree/) — perk descriptions.
- [Community scarcity ranking](https://www.reddit.com/r/CreaturesOfTheDeeptip/comments/1ww928y/catching_difficulty_ranking/) — initial encounter tiers.
- [Player discussion of elusive species](https://www.reddit.com/r/CreaturesOfTheDeeptip/comments/1mh297g/) — supporting reports and additional targets.
- [DNA Lab community wiki](https://creatures-of-the-deep-app.fandom.com/wiki/DNA_Lab) — milestone reward information.
- [Tesseract.js](https://github.com/naptha/tesseract.js) — photo text recognition.

This is an unofficial fan project and is not affiliated with or endorsed by Infinite Dreams. Game names and assets belong to their respective owners. Attribution does not grant redistribution rights to third-party assets; review those rights before redistribution.

## Beta v1.01 changes

- Added difficulty sorting and concise catch tips.
- Expanded scarcity evidence to 26 species, with additional support for 13 ratings.
- Added 5% controls to the next DNA target.
- Removed the reset button.
- Retained location/time/season-aware recommendations, photo import and progress backups.
