# Nitro-C – Crash Nitro Kart for Windows

An unofficial, native **Windows x64 port of Crash Nitro Kart** (PS2), written in C++20 with Direct3D 11.

The game logic is rebuilt function by function from the original game, so driving feels exactly like it does on the console. Graphics and controls may be PC-style (higher resolution, Xbox controller, keyboard), but the driving behavior and physics are never replaced with made-up approximations.

> **Note:** This project contains **no game data**. You need your own legally obtained copy of Crash Nitro Kart (PS2, NTSC-U, `SLUS_206.49`). All graphics, models, sounds and tracks are read locally from your ISO and are never distributed.

## Progress

The percentages are honest estimates by the developers. They are updated with every major step, so you can follow here what already works and what is still missing.

<!-- PROGRESS:START -->
![Overall progress](https://img.shields.io/badge/progress-27%25-orange?style=for-the-badge)

**Overall: 27 %** `█████░░░░░░░░░░░░░░░`  
_Last updated: 2026-11-01_

| Area | Progress | % | Status |
| --- | --- | ---: | --- |
| ISO import & data extraction | `█████████████████░░░` | 85 % | Full extraction with checksums; GOB/GFC name resolution incomplete |
| Asset decoders (textures, models, audio) | `█████████░░░░░░░░░░░` | 45 % | TGA, PNG, VAG, track and kart geometry; animations and many formats missing |
| Graphics / renderer (Direct3D 11) | `██████░░░░░░░░░░░░░░` | 30 % | Textured track, kart in a static pose; no animation, LOD or effects |
| Driving physics & kart handling | `████████████░░░░░░░░` | 60 % | Original driving logic ported, free drive works |
| Collision & physics world | `██████████████░░░░░░` | 70 % | Contacts, surfaces, static world |
| Input (Xbox controller, keyboard) | `████████████████░░░░` | 80 % | XInput and keyboard |
| Race flow (start, countdown, laps, finish) | `███░░░░░░░░░░░░░░░░░` | 15 % | Individual pieces ported, not yet connected |
| Opponent AI | `░░░░░░░░░░░░░░░░░░░░` | 0 % |  |
| Weapons & items | `░░░░░░░░░░░░░░░░░░░░` | 0 % |  |
| Tracks | `█░░░░░░░░░░░░░░░░░░░` | 5 % | One track (Earth1) loads |
| Drivers & karts | `█░░░░░░░░░░░░░░░░░░░` | 5 % | One kart loads |
| In-game audio (music, effects, voices) | `█░░░░░░░░░░░░░░░░░░░` | 5 % | Intro audio only |
| Menus & frontend | `██░░░░░░░░░░░░░░░░░░` | 10 % | Intro and a provisional PC main menu |
| HUD | `░░░░░░░░░░░░░░░░░░░░` | 0 % |  |
| Game modes (Adventure, Arcade, Time Trial, Battle, multiplayer) | `░░░░░░░░░░░░░░░░░░░░` | 0 % |  |
| Save data & options | `░░░░░░░░░░░░░░░░░░░░` | 0 % |  |
| User setup & release | `░░░░░░░░░░░░░░░░░░░░` | 0 % | Importing data from your own ISO is not automated yet |

### Milestones

- ✅ Build foundation and ISO verification
- ✅ Import and decode resources
- ✅ Intro and PC main menu
- ✅ Original track textured in 3D
- ✅ Free drive with an Xbox controller on the original track
- 🔧 First real race (start, laps, finish)
- ⬜ Opponents on the track
- ⬜ Weapons and items
- ⬜ All tracks, drivers and karts
- ⬜ Original menus, HUD and sound
- ⬜ All game modes including Adventure
- ⬜ First playable release

✅ done · 🔧 in progress · ⬜ open
<!-- PROGRESS:END -->

## What already works in development builds

- **Free drive:** Crash's kart on the original Earth1 track with the original driving physics and collision. No opponents, countdown or lap scoring yet.
- **Track viewer:** explore the textured original track with a free camera.
- **Intro and main menu:** the Alchemy intro, followed by a provisional PC menu.

Free drive controls:

| Action | Xbox controller | Keyboard |
| --- | --- | --- |
| Accelerate | RT | W / ↑ |
| Brake / reverse | LT | S / ↓ |
| Steer | Left stick | A, D / ←, → |
| Reset kart | Start | R |
| Quit | – | Esc |

## Source code

The source code is not published yet. It will follow here as research into the game progresses. The port is built with CMake and Visual Studio 2022 for Windows 10/11 x64.

Game data is imported from your own ISO into a local folder on your machine and is never uploaded. A one-step import for new users is planned.

## How the port works

- **Not an emulator:** No PS2 code is executed. The original program's behavior is analyzed and rewritten as native C++.
- **Verifiably faithful:** Ported game logic comes with verification tools that compare the results against the original code, plus automated tests.
- **Local data only:** The ISO, extracted files and analysis reports stay on your machine and are excluded from version control.

## Legal

Nitro-C is a fan project and is not affiliated with Activision, Vicarious Visions or Sony. "Crash Nitro Kart" and "Crash Bandicoot" are trademarks of their respective owners. No copyrighted game content, Sony SDK or PS2 BIOS is distributed.
