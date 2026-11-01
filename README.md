# NeoEnabler patches: LEGO Dimensions and Disney Infinity 3.0 in PS4 Pro mode

ps-patch-system patches that run both games in PS4 Pro mode on a PS5 (through NeoEnabler) at 1080p or
native 4K, with 60 FPS.

| Game | Version | File |
|---|---|---|
| LEGO Dimensions | CUSA01176, 01.24 | `CUSA01176.xml` |
| Disney Infinity 3.0 | CUSA01862, 01.06 | `CUSA01862.xml` |

Tested on a PS5 with firmware 13.60.

## Requirements

- ps-patch-system
- [NeoEnabler](https://github.com/gasb07/NeoEnabler) **0.5.3 or newer** (tested with 0.6.1). Older versions do
  not start these games in PS4 Pro mode.

## Installation

1. Copy `CUSA01176.xml` and `CUSA01862.xml` to `/data/user/patches/xml_orbis/` on the console (for example over
   FTP).
2. Send ps-patch-system, then NeoEnabler (`neo-manager.elf`).
3. In the NeoEnabler panel (`http://<PS5 IP>:8765`) enable, per game:
   - **one** resolution entry,
   - **one** frame rate entry,
   - optionally the effects in LEGO Dimensions.
4. For the 4K entries, set the PS5 video output to 2160p.

## Entries

### LEGO Dimensions

| Entry | Description |
|---|---|
| `1080p (PS4 Pro mode)` | 1920×1080 in PS4 Pro mode |
| `Native 4K (PS4 Pro mode)` | 3840×2160, about 60 fps with the 60 FPS entry |
| `1440p internal - 2160p output (PS4 Pro mode)` | 2560×1440 render, 4K output; not tested yet |
| `60 FPS - engine target` | 60 fps with vsync (by connorh315) |
| `120 FPS - engine target (experimental)` | **experimental**, 120 Hz; includes the 60 FPS line, enable it instead |
| `Disable depth of field` | turns off depth of field |
| `Enable FXAA` | turns on FXAA |

### Disney Infinity 3.0

| Entry | Description |
|---|---|
| `1080p (PS4 Pro mode)` | 1920×1080 in PS4 Pro mode |
| `Native 4K (PS4 Pro mode)` | 3840×2160 |
| `Native 4K (PS4 Pro mode, requires 8 GiB)` | the same with NeoEnabler's 8 GiB memory budget (FW 13.20/13.60) |
| `60 FPS Unlock V2` | 60 fps with vsync |
| `120 FPS (experimental)` | **experimental**, 120 Hz; enable it instead of the 60 FPS entry |

## 120 FPS (experimental)

- Needs a 120 Hz display. NeoEnabler 0.6.0+ turns the 120 Hz video output on for the game by itself.
- Both games use only two display buffers with vsync, so in testing they reach about 70 fps (LEGO 70–95), not a
  locked 120.
- The PS5 does not support VRR for PS4 games.
- NeoEnabler's CPU/GPU boost did not raise the frame rate in these games and makes the console run hotter.

## Credits

- Gregorious: PS4 Pro mode fixes, resolution entries, effects, Disney frame rate entries, 120 FPS.
- connorh315: `60 FPS - engine target` (LEGO Dimensions).
- gasb07: NeoEnabler.

This repository contains only the patch XML files, no game files.
