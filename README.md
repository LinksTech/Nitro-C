# Nitro-C – Crash Nitro Kart for Windows

A native PC reimplementation of Crash Nitro Kart, reverse-engineered from the PS2 version. No emulation.

**Driving should feel like the original** (acceleration, braking, steering, drifting, boosts, hops and jumps, surfaces and item hits on the kart). It is rebuilt from the original game logic and checked against it; nothing about the handling is made up.

**Everything around the driving is built new for PC:** race flow, menus, HUD, graphics and sound, with PC-style controls (Xbox controller, keyboard) and higher resolutions.

> **Note:** This project contains **no game data**. You need your own legally obtained copy of Crash Nitro Kart (PS2, NTSC-U, `SLUS_206.49`). All graphics, models, sounds and tracks are read locally from your ISO and are never distributed.

## Progress

How the number is computed: the overall value is the weighted average of 17 areas. For the areas *Tracks* and *Drivers & karts* it is the sum of fixed sub-goals that are fully met (for example "collision of all 26 tracks readable"); a sub-goal that holds only for some tracks or drivers counts 0 until it holds for all. The other areas do not have such a breakdown yet; their values are unchanged since the last update and are raised only when a countable sub-goal is met. When in doubt, the lower number is used.

<!-- PROGRESS:START -->
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/progress-dark.svg">
  <img alt="Nitro-C progress: 34 % overall" src="assets/progress-light.svg" width="600">
</picture>

### Milestones

- ✅ Build foundation and ISO verification
- ✅ Import and decode resources
- ✅ Intro and PC main menu
- ✅ Original track textured in 3D
- ✅ 3D free drive with the original camera and an Xbox controller
- 🔧 Driving checked against the original code
- ✅ Own DirectX 11 renderer with fixed simulation tick
- ✅ Audio module (sounds, voices, music from your own ISO)
- 🔧 All 26 tracks and 16 drivers readable from the original files
- 🔧 First real race (start, laps, finish)
- ⬜ Opponents on the track
- ⬜ Weapons and items
- ⬜ All tracks, drivers and karts
- ⬜ PC menus, HUD and sound
- ⬜ All game modes including Adventure
- ⬜ First playable release

✅ done · 🔧 in progress · ⬜ open

### Current state (2026-11-03)

- **Tracks:** 7 of 13 race tracks load in the game. On Earth1 the complete scene is now loaded and drawn (all geometry, textures and the sky); water, lava and transparency effects are still missing.
- **Graphics:** untextured geometry (for example the sky) now has its original colours; boost pads lie flat on the road.
- **Title screen:** pressing START unlocks at the same moment as in the original; the story intro that follows in the original is not built yet.
- **Menus:** the keyboard works in the menus (arrow keys, Enter, Backspace/Esc).
- **Driving:** the wall response and the stand-still timer were corrected to match the original code in the places identified so far; the physics step rate (59.94 Hz, one step per frame) is proven to match the original.
- **Weapons & items:** research is finished and a build plan exists; nothing is built yet.
- **Checks:** 2,878 automatic driving checks and an automated test driver on Earth1 pass.

**Known gaps:** opponents (AI) are not active yet; anti-gravity sections are not finished; driver and kart animations are missing; weapons and items are not built; 6 race tracks do not load yet.
<!-- PROGRESS:END -->

## Source code

The source code is not published yet. It will follow here as research into the game progresses. The port is built with CMake and Visual Studio 2022 for Windows 10/11 x64.

Game data is imported from your own ISO into a local folder on your machine and is never uploaded. A one-step import for new users is planned.

## How the port works

- **Not an emulator:** No PS2 code is executed. The original kart and driving logic is analyzed and rewritten as native C++.
- **Faithful driving:** The driving code is tested against the original game's own logic, including the PS2's floating-point rounding, so it feels like the original.
- **PC-native everything else:** Race flow, menus, HUD, rendering and audio are designed new for PC instead of copying the console's way of doing them.
- **Local data only:** The ISO, extracted files and analysis reports stay on your machine and are excluded from version control.

## Legal

Nitro-C is a fan project and is not affiliated with Activision, Vicarious Visions or Sony. "Crash Nitro Kart" and "Crash Bandicoot" are trademarks of their respective owners. No copyrighted game content, Sony SDK or PS2 BIOS is distributed.
