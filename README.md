# Undefeated GM

**Undefeated GM** is a basketball draft simulator and mini-game hub inspired by the idea of building the perfect team and chasing an undefeated season.

The main mode lets you spin a random franchise and era, draft players who played for that franchise during that era, build a lineup, and simulate how successful the team would be. The game uses more than just per-game stats — team success is based on player ratings, era-average stats, accolades, roster fit, defense, spacing, playmaking, rebounding, depth, and simulation randomness.

> This is an independent fan-made project. It is not affiliated with, endorsed by, or sponsored by the NBA.

---

## Features

### Main Draft Modes

* **Classic Draft**

  * Spin a random franchise and era.
  * Pick any player who played for that franchise during that era.
  * Build a team and simulate the final result.

* **All-Time Franchise Mode**

  * Choose one franchise.
  * Draft players only from that franchise history.
  * Franchise relocations/name changes are grouped together.

* **Battle Mode**

  * Build a team and face a CPU-generated team.
  * Simulates a best-of-seven style matchup.

* **Playoff Mode**

  * Build a roster and try to survive four playoff rounds.

* **GM Trade Mode**

  * Draft a roster.
  * Enter a trade center.
  * Accept or decline trade offers.
  * Trade offers are not guaranteed upgrades.

* **Dynasty Mode**

  * Draft a roster.
  * Simulate a five-year dynasty run.
  * Tracks wins, playoff results, championships, and dynasty score.

---

## Mini-Games

* **Guess the Player by Stats**

  * Guess the player based on their statistical profile.

* **Higher or Lower**

  * Pick which player had the higher shown stat.

* **Guess the Team**

  * Guess the franchise based on player clues.

* **Guess the Era**

  * Guess the decade based on player clues.

* **Career Path Guess**

  * Guess the player based on the franchises they played for.

* **Player Comparison**

  * Compare two player cards and guess which one has the higher game rating.

---

## How the Game Works

### Drafting

In Classic Draft, the game rolls:

```txt
Franchise + Era
```

Example:

```txt
Lakers + 2000s
```

The player list then shows players who played for that franchise during that era.

You pick a player, choose an eligible position, and build your lineup.

---

## Eras

The game supports historical era groupings:

```txt
1960s
1970s
1980s
1990s
2000s
2010s
2020s
Current / NOW
```

Historical era cards use era averages, not just a player’s single best season.

Example:

```txt
2000s LeBron = average of his 2000s seasons for that franchise
2010s LeBron = average of his 2010s seasons for that franchise
```

Current mode uses a separate current roster file so current teams can be updated without changing historical cards.

---

## Franchise Grouping

The game combines renamed or relocated teams into one franchise group.

Examples:

```txt
New Jersey Nets + Brooklyn Nets = Nets
Seattle SuperSonics + Oklahoma City Thunder = Thunder/Sonics
Cincinnati Royals + Kansas City Kings + Sacramento Kings = Kings/Royals
Washington Bullets + Washington Wizards = Wizards/Bullets
Syracuse Nationals + Philadelphia 76ers = 76ers/Nationals
San Francisco Warriors + Golden State Warriors = Warriors
New Orleans Jazz + Utah Jazz = Jazz
Vancouver Grizzlies + Memphis Grizzlies = Grizzlies
```

If a player played for multiple versions of the same franchise in the same era, the game combines them into one franchise-era card.

Example:

```txt
Tiny Archibald
CIN / KCO / KCK
Kings/Royals 1970s
```

Instead of showing three separate Tiny Archibald cards, the game shows one combined franchise-era card.

---

## Player Positions

Players can be placed in positions they are eligible for.

The game supports:

```txt
PG
SG
SF
PF
C
```

If a player has played multiple positions, they can be moved between those eligible spots.

Example:

```txt
SF/PF player can play SF or PF.
```

Players can also be dragged to different positions after being placed. If two players are both eligible for each other’s spots, they can be swapped.

---

## How Team Success Is Calculated

The game is not based only on per-game stats.

A team’s success is influenced by:

* Era-average stats
* Player game rating
* Skill ratings
* Accolades
* Star power
* Position fit
* Spacing
* Playmaking
* Rebounding
* Perimeter defense
* Interior defense
* Shot blocking
* Paint protection
* Bench/depth
* Team chemistry
* Simulation randomness

A team with high scorers can still have weaknesses if it lacks:

* Rim protection
* Defensive bigs
* Balanced positions
* Shooting
* Playmaking
* Rebounding
* Bench depth

This means the best lineup is not always just the five highest PPG players.

---

## Strengths and Weaknesses

After a simulation, the game analyzes the roster and lists strengths and weaknesses.

Examples of strengths:

```txt
Elite spacing and shooting
Multiple creators/playmakers
Strong interior presence
Controls the glass
Built for close games
Balanced scoring depth
```

Examples of weaknesses:

```txt
No true shot blocker
Paint defense may be thin
Center spot lacks elite rim protection
Limited spacing
Low playmaking
Weak rebounding
Thin bench depth
```

---

## Season Randomness

The **Season Randomness** option controls how much luck affects the final result.

When enabled, the same team can produce slightly different records each time.

Example:

```txt
Team Rating 92 might go 67-15 once,
then 70-12 another time.
```

When disabled, results are more consistent and calculation-based.

---

## Records

The game saves records locally in the browser.

Records can include results from:

* Classic Draft
* All-Time Franchise Mode
* Battle Mode
* Playoff Mode
* GM Trade Mode
* Dynasty Mode
* Mini-games

Records are stored using browser local storage, so they may be cleared if browser data is deleted.

---

## Current Rosters

Current mode is separated from historical modes.

Historical modes use the full era database.

Current mode uses:

```txt
src/current_rosters.js
```

This makes it easier to update trades, signings, and current team changes without changing historical data.

If a player changes teams in real life, update the current roster file or rebuild it using the tools in the `tools/` folder.

---

## Project Structure

A typical version of the project looks like:

```txt
undefeated-gm/
│
├── index.html
├── manifest.json
├── service-worker.js
│
├── src/
│   ├── app.js
│   ├── data.js
│   ├── full_players.js
│   ├── current_rosters.js
│   ├── styles.css
│   └── icons/
│
├── tools/
│   ├── build_current_rosters_from_dataset.py
│   ├── current_rosters_manual_overrides.csv
│   └── import_all_players_from_csv.py
│
└── README.md
```

---

## Running Locally

You can test the game by opening:

```txt
index.html
```

directly in your browser.

For best results, especially with service workers and PWA features, use a local server.

Example with Python:

```bash
python -m http.server 8000
```

Then open:

```txt
http://localhost:8000
```

---

## Hosting on GitHub Pages

1. Create a GitHub repository.
2. Upload all project files.
3. Make sure `index.html` is in the root of the repo.
4. Go to:

```txt
Settings → Pages
```

5. Set the source to:

```txt
Deploy from a branch
main branch
/root
```

6. Save.
7. Wait for GitHub to generate your site link.

Your link should look like:

```txt
https://yourusername.github.io/your-repo-name/
```

---

## Updating the Website

When uploading a new version:

1. Replace the old files with the new files.
2. Commit the changes.
3. Wait for GitHub Pages to redeploy.
4. Hard refresh the page:

```txt
Ctrl + F5
```

If the site still shows an old version, the service worker/browser cache may still be storing old files.

---

## Mobile Support

The game includes responsive layout support for:

* Desktop
* Tablet
* Mobile browsers

Some pages may scroll if the content does not fit the screen.

The game also includes PWA files, meaning it can be added to a phone home screen once hosted online.

---

## Data Notes

The historical database is built from uploaded basketball stat data and converted into game cards.

The game uses:

* Player names
* Teams/franchises
* Eras
* Positions
* Per-game stats
* Era averages
* Ratings
* Franchise grouping
* Current roster overrides

Some ratings are automatically generated and may need manual tuning over time.

Older players may need extra adjustments because certain modern stats, such as three-point shooting, did not exist in earlier eras.

---

## Planned Improvements

Possible future updates:

* Better current roster updater
* More accurate player ratings
* Manual legend rating overrides
* Better trade logic
* More detailed dynasty mode
* More records/stat tracking
* Online leaderboards
* Shareable result images
* More mobile polish
* More help/tutorial screens
* More mini-games
* Difficulty settings
* Custom draft rules

---

## Disclaimer

This is a fan-made basketball game project.

It is not affiliated with, endorsed by, or sponsored by the National Basketball Association, any NBA team, or any official league organization.

All team/player references are used for informational and gameplay purposes in a fan project.
