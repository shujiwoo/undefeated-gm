
## v32 - Smarter Strengths / Weaknesses Analysis
- Strengths and weaknesses now analyze more than average ratings.
- Added checks for shot blocking, rim protection, paint defense, point-of-attack defense, scoring ceiling, lineup balance, and roster roles.
- Teams with weak interior defense should no longer show “No major weaknesses” just because their overall rating is strong.

# Undefeated GM v30 Mini-Game Cleanup

- Hidden stat values on Higher or Lower and Player Comparison until the answer is revealed.
- Career Path team pills are smaller and use team/franchise colours.
- Updated service worker cache name.

# v29 - Wheel Scroll Fix

- Fixed mouse wheel scrolling on pages and nested scroll areas.
- Scrollbar dragging still works, but wheel scrolling now manually targets the nearest scrollable screen/list when needed.
- Player dragging still blocks scrolling only while an actual drag is active.

# v28 - Universal Scroll Safety

- All major pages can now scroll if content does not fit the viewport.
- Player lists, trade offers, mini-games, result screens, and home pages are no longer trapped inside a hidden frame.
- Internal scroll boxes still work where useful, but the whole page can also scroll as a fallback.
- Updated service worker cache name for hosted/GitHub refreshes.

## v27 - Help Scoring Explanation
- Added a clear Help section explaining how team success is calculated.
- Clarified that the simulator uses more than per-game stats: skills, era averages, accolades, fit, chemistry, roster depth, and randomness all matter.

# v24 - Player List Scroll Fix

- Fixed long player lists running out of the visible frame.
- Player list now scrolls internally on desktop, tablet, and mobile.
- Gameplay screen still stays in one frame where possible.
- Updated service worker cache name so hosted sites load the new CSS.

# Undefeated GM v22

- Fixed home/menu buttons not opening game pages.
- The v21 home layout rule accidentally overrode `.hidden`, leaving the home screen visible above gameplay views.
- Added stronger hidden-state CSS so navigation works properly while keeping the spacious scrollable home menu.


## v23
- Reworked the home hero so it doesn't swallow the whole page.
- Shortened the hero headline and tightened mode cards so the menu feels intentional instead of oversized.
- Kept game pages compact and menu scrolling separate.

## v26 - End Screen + Help Page
- Rebuilt the end/result screen with a cleaner 82-style vertical result layout.
- Made the result screen scrollable so long rosters and full roster modes display properly.
- Added lineup cards with initials, team colors, player stats, and team totals.
- Added a How to Play/Help drawer accessible from the top bar, home menu, and result screen.
- Updated the service worker cache name for hosted/GitHub deployments.


## v31 - Franchise Era Combine
- Historical cards are now merged by player + franchise + era.
- Renamed/relocated teams from the same franchise now show one combined franchise-average card.
- Example: Tiny Archibald on Cincinnati Royals / Kansas City-Omaha Kings / Kansas City Kings appears once for Kings/Royals 70s.
