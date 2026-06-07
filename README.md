# Undefeated GM - v18 Big Modes Update

A clean browser basketball draft game and mini-game hub inspired by team/era spin drafts, built with original code, design, ratings, and modes.

## What is playable

Main games:
- Classic Draft
- All-Time Franchise Mode
- Battle Mode
- Playoff Mode

Mini-games:
- Guess the Player by Stats
- Higher or Lower
- Guess the Team
- Guess the Era
- Career Path Guess
- Player Comparison

Future menu slots still planned:
- Dynasty Mode
- GM Trade Mode

## Database

- Historical modes use `src/full_players.js`.
- Current/NOW mode uses `src/current_rosters.js`.
- Historical decade cards use era/team averages, not just peak seasons.
- Current rosters can be updated using the files inside `tools/`.


# Undefeated GM - Full Database Spin Draft v12

This version uses era-average player cards instead of prime/peak cards.

- 15,003 player/team/era cards
- 4,484 unique NBA players from 1960-61 onward
- Decade cards use game-weighted averages across that player/team/era
- Current mode still uses exact 2025-26 player/team rows
- Team + era spin draft


This version includes the full generated database from the uploaded NBA stats archive.

- 15,003 player/team/era cards
- 4,484 unique NBA players from 1960-61 onward
- Team + era spin draft
- Every eligible player appears in **Everyone** mode
- Current mode uses 2025-26 player/team cards


This version includes the full generated database from the uploaded NBA stats archive.

- 14,819 player/team/era cards
- 4,484 unique NBA players from 1960-61 onward
- Team + era spin draft
- Every eligible player appears in **Everyone** mode
- Current mode uses 2025-26 player/team cards


This version includes the full generated database from the uploaded NBA stats archive.

- 14,819 player/team/era cards
- 4,484 unique NBA players from 1960-61 onward
- Team + era spin draft
- Every eligible player appears in **Everyone** mode
- Current mode uses 2025-26 player/team cards


A clean browser basketball draft game inspired by the simple spin flow of 82-0, but with original code, design, ratings, and extra systems.

## How to run

1. Unzip the folder.
2. Open `index.html` in your browser.
3. Press **SPIN**.

No install needed.

## Main gameplay

- Round count changes based on game mode: 5-Man, 6-Man, or Full Roster.
- Spin a random **team** and **era**.
- Eras roll from the **60s to the 20s** by default.
- Pick any eligible player who played for that team in that era.
- You get **1 Team respin and 1 Era respin for the whole game**.
- Player list has tabs for **All / G / F / C**, search, and sorting.
- When picking a player, click them, then click an eligible court/bench position.
- Players can only be placed at listed positions. Example: a C/PF can only be placed at C or PF.
- Picked players are moveable by dragging. Drag a filled court/bench spot to an eligible open spot, or drag onto another filled spot to swap if both players are eligible.
- After 5 picks, the game calculates your team score and 82-game record.

## What changed in this version

- Theme changed from orange/purple to a blue/teal style.
- Position moves are supported during the draft, even while you are currently placing a new player. Example: if you place a PF/SF at PF and SF is open, drag them to SF. If another SF/PF is already there, you can drag to swap them.
- Added `src/full_players.js` as an add-on database file.
- Added `tools/import_all_players_from_csv.py` to generate a full database from a CSV.

## Important about all players

This zip does **not** include every NBA player yet. It includes the full-code structure for it:

- `src/data.js` = starter sample cards.
- `src/full_players.js` = extra database cards loaded automatically.
- `tools/import_all_players_from_csv.py` = CSV importer for a real full player-season database.
- `tools/all_players_template.csv` = template showing the required columns.

Do not manually type thousands of players. Use a real player-season dataset, convert it into the template format, then run the importer.


### Latest controls update

You now get one Team respin and one Era respin for the whole game. The move-position panel stays in the screen so you should not need to scroll to move a player.


## v4 Notes

New settings:

- **5-Man Team**: normal PG/SG/SF/PF/C lineup.
- **6-Man Team**: adds one 6TH bench spot.
- **Full Roster**: adds a full bench under the starting five.

Position movement now supports swaps. Example: if one SF/PF is at PF and another SF/PF is at SF, click either filled spot and swap them.

Respins are still game-wide: 1 team respin and 1 era respin total per run, but now they animate dramatically instead of changing instantly.

## Franchise grouping

Team rolls now group renamed/relocated franchises together. For example, a Nets roll can include New Jersey Nets and Brooklyn Nets players from that era, and a Thunder/Sonics roll can include Seattle SuperSonics and Oklahoma City Thunder players. Player rows still show the exact historical team abbreviation so you can see where that season came from.

## Mobile / Different Devices
This version includes a responsive mobile layout and PWA files.

To test on your phone, host the folder online with Netlify, Vercel, Cloudflare Pages, or GitHub Pages. Opening `index.html` directly works for local testing, but the install/offline PWA feature only works after hosting on a normal `https://` website.

On mobile:
- The player list stacks above the court.
- The court sticks near the bottom so you can still place or drag players.
- Touch targets are larger.
- Dragging uses pointer/touch-friendly CSS.


## Logo / App Icon

The site logo is stored in `icons/site-logo.png`. It is used in the top-left header and as the favicon/PWA icon through `manifest.json`. The header logo is a link back to `index.html`, so it works like a home/reset button when hosted on GitHub Pages.


## v15 Current roster system

Current/NOW mode now uses `src/current_rosters.js` instead of the historical era-average file. This means trades/signings only change Current mode; decade modes like 2000s, 2010s, and 2020s still keep the teams players actually played for during those eras.

To update a current team, edit `tools/current_rosters_manual_overrides.csv`, then run:

```bash
python tools/build_current_rosters_from_dataset.py
```

Then upload the updated files to GitHub again.


## v18 Big Modes

Playable modes now include Classic Draft, All-Time Franchise, Battle Mode, Playoff Mode, GM Trade Mode, Dynasty Mode, and the v17 mini-game pack.

- GM Trade Mode: draft a team, accept up to two trade offers, then simulate.
- Dynasty Mode: draft a core and simulate five seasons of title chances.
