# Full Player Database Guide

Your goal is to eventually include every player who played at least one NBA season from the 1960s through the 2020s/current era.

## Best database approach

Keep two layers of data:

1. **Player profile**: name, id, height, position, first season, last season.
2. **Season cards**: player + specific season + team + era + ratings.

This game uses season cards because the spin result is based on:

```txt
rolled team + rolled era
```

A player appears as an option when:

```txt
card.team === rolled team
card.era === rolled era
```

So if a player played for multiple teams in the same era, add multiple cards or use their best season with each team.

## Files to use

### Starter data

```txt
src/data.js
```

This has the sample cards currently used by the game.

### Full database add-on

```txt
src/full_players.js
```

This file is loaded automatically after `src/data.js`.

### CSV importer

```txt
tools/import_all_players_from_csv.py
```

Run it like this from the project folder:

```bash
python tools/import_all_players_from_csv.py tools/all_players_template.csv
```

Replace the template file with your real full CSV when you have one.

## Required CSV columns

```txt
id,player_id,name,season,era,team,positions,tier,seasons_played,games,ppg,rpg,apg,spg,bpg,fg,three,ft,accolades,scoring,shooting,playmaking,defense,rebounding,clutch,durability,athleticism,tags
```

Use `|` for list fields:

```txt
positions: PG|SG
accolades: MVP|Champion|All-NBA 1st
tags: shooter|defense|bench
```

## Era labels

Use these era labels exactly:

```txt
1960s
1970s
1980s
1990s
2000s
2010s
2020s
Current
```

## Team abbreviations

Use common abbreviations like:

```txt
ATL, BOS, BKN, BRK, CHA, CHI, CLE, DAL, DEN, DET, GSW, HOU, IND, LAC, LAL, MEM, MIA, MIL, MIN, NJN, NYK, OKC, ORL, PHI, PHX, POR, SAC, SAS, SEA, TOR, UTA, WAS
```

You can add old franchise/team abbreviations in `TEAM_NAMES` inside `src/app.js`.

## Rating advice

Do not make ratings only from PPG/RPG/APG. Use:

- Skills
- Era-adjusted stats
- Accolades
- Longevity/role
- Playoff/clutch
- Team fit

Older players should not be punished for not having 3PT stats before the 3-point line existed.

## Full database rule

A player should be included if they appeared in at least one regular NBA season from 1960-61 onward.

For gameplay, you should still tier players:

```txt
Legend
Star
Starter
Role
Deep
```

This keeps normal mode fun while still supporting the full database through the Everyone pool.
