# Current roster system

Version 15 separates **Current/NOW mode** from the historical era database.

- `src/full_players.js` = historical decade cards, including every player-season/team-era card from the uploaded dataset.
- `src/current_rosters.js` = one Current/NOW card per active player, using the uploaded 2025-26 rows plus current-team overrides.
- `tools/current_rosters_manual_overrides.csv` = edit this when trades/signings happen.

Historical modes should not change when a player gets traded. Example: Jaren Jackson Jr. can still appear for 2020s Grizzlies historically, but his Current/NOW card can be on Utah.

## Updating a current team manually

Open `tools/current_rosters_manual_overrides.csv` and add/update:

```csv
player_id,name,current_team,notes
jacksja02,Jaren Jackson Jr.,UTA,Confirmed current roster
```

Then rebuild `src/current_rosters.js` with the builder script.

## Why this exists

The uploaded stats dataset has one row per player/team stint. A traded player can have multiple Current rows in the same season. The game needs Current/NOW mode to show the player on their current roster only, while keeping all historical team cards untouched.
