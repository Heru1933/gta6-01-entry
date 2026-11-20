# Coral Bay Heat

An original open-world crime game that runs entirely offline in a desktop browser
from static files. No build step, no network requests at runtime.

You are Dario Venn, a driver fresh off the ferry in Coral Bay. Run jobs for Nadia
Ferro, steal cars, dodge the Coral Bay PD, and work your way from lifting a sports
car to the Bancroft bank job.

## Play

Open `game/index.html` in a desktop browser (or run `node serve.ts` and visit the
address it prints).

- **WASD / arrows** — walk or drive
- **E** — enter / exit a car, talk, use a shop
- **Mouse** — aim, **click** — punch or shoot
- **Shift** — sprint, **Space** — handbrake
- **R** — reload, **1/2/3** — fist / pistol / SMG
- **P or Esc** — pause, **M** — mute

## What's in the city

- A seeded coastal city (100 x 80 tiles) with a road graph, traffic AI with lanes
  and honking, pedestrians who stroll, flee and phone the police
- Stealable parked and moving cars, each model with its own handling
- A wanted system: witness rules, line of sight, heat decay when unseen, police
  pursuit cars, officers on foot and roadblocks at four stars
- Combat: fists, pistol and SMG, reloads, armor, shopkeepers who shoot back
- Six story missions plus repeatable taxi fares
- Shops: a spray shop that clears your heat, a gun shop, a garage, a hospital,
  food stands
- HUD with health/armor bars, weapon and ammo, cash, wanted stars, clock and a
  live minimap
- A full day cycle with night lighting, headlights and lamp glow
- Synthesized WebAudio music and sound effects — no audio files
- Save / continue via localStorage, with autosave

## Self-test

Open `game/index.html?test=1` to run the built-in automated test, which plays the
core loop (walk, steal, drive, wanted level, police response, shooting, the first
mission, minimap, save/load) and reports pass/fail on screen.

Deterministic screenshot scenes for review live at
`game/index.html?shot=cover|play|chase|night`.

## Layout

- `game/` — the game itself (static HTML/CSS/JS modules under `game/src/`)
- `screenshots/` — renders of the game in a browser
- `main.ts` — the hand-in program: copies `game/` and `screenshots/` to the output
  directory and writes `dossier.json`
- `vendor/makefun-game.ts` — the competition's dossier builder (vendored, unchanged)

MIT licensed. Everything in the game — city, names, story, art and sound — is
original to this entry.
