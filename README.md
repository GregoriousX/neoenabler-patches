# LEGO Dimensions i Disney Infinity 3.0: tryb PS4 Pro na PS5

Patche ps-patch-system, które uruchamiają obie gry w trybie PS4 Pro na PS5
(przez NeoEnabler) w 1080p albo natywnym 4K, z 60 FPS.

| Gra | Wersja | Plik |
|---|---|---|
| LEGO Dimensions | CUSA01176, 01.24 | `CUSA01176.xml` |
| Disney Infinity 3.0 | CUSA01862, 01.06 | `CUSA01862.xml` |

Testowane na PS5 z firmware 13.60.

## Wymagania

- ps-patch-system;
- [NeoEnabler](https://github.com/gasb07/NeoEnabler) **0.5.3 lub nowszy**
  (testowany 0.6.1). Starsze wersje nie włączą trybu Pro dla tych gier.

## Instalacja

1. Skopiuj `CUSA01176.xml` i `CUSA01862.xml` do `/data/user/patches/xml_orbis/`
   na konsoli (np. przez FTP).
2. Wyślij ps-patch-system, a potem NeoEnabler (`neo-manager.elf`).
3. W panelu NeoEnablera (`http://<IP PS5>:8765`) zaznacz dla gry:
   - **jeden** wpis rozdzielczości,
   - **jeden** wpis FPS,
   - w LEGO opcjonalnie efekty.
4. Dla wpisów 4K ustaw wyjście wideo PS5 na 2160p.

## Wpisy

### LEGO Dimensions

| Wpis | Opis |
|---|---|
| `1080p (PS4 Pro mode)` | 1920×1080 w trybie Pro |
| `Native 4K (PS4 Pro mode)` | 3840×2160, ok. 60 FPS z wpisem 60 FPS |
| `1440p internal - 2160p output (PS4 Pro mode)` | render 2560×1440, wyjście 4K; nietestowany |
| `60 FPS - engine target` | 60 FPS z vsync (autor: connorh315) |
| `120 FPS - engine target (experimental)` | **eksperymentalny**, 120 Hz; zawiera wpis 60 FPS, włącz zamiast niego |
| `Disable depth of field` | wyłącza głębię ostrości |
| `Enable FXAA` | włącza FXAA |

### Disney Infinity 3.0

| Wpis | Opis |
|---|---|
| `1080p (PS4 Pro mode)` | 1920×1080 w trybie Pro |
| `Native 4K (PS4 Pro mode)` | 3840×2160 |
| `Native 4K (PS4 Pro mode, requires 8 GiB)` | to samo z budżetem 8 GiB NeoEnablera (FW 13.20/13.60) |
| `60 FPS Unlock V2` | 60 FPS z vsync |
| `120 FPS (experimental)` | **eksperymentalny**, 120 Hz; włącz zamiast wpisu 60 FPS |

## 120 FPS (eksperymentalne)

- Wymaga monitora 120 Hz. NeoEnabler 0.6.0+ sam włącza wyjście 120 Hz na czas
  gry.
- Obie gry mają tylko dwa bufory obrazu i vsync. W testach wychodzi ok. 70 FPS
  (LEGO 70–95), a nie stałe 120.
- PS5 nie obsługuje VRR w grach z PS4.

## Autorzy

- GregoriousX: poprawki trybu Pro, wpisy rozdzielczości, efekty, wpisy FPS
  Disneya, 120 FPS.
- connorh315: `60 FPS - engine target` (LEGO).

Repozytorium zawiera tylko pliki XML z patchami, bez plików gier.
