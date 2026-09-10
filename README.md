<h1 align="center">Tidepool</h1>

<p align="center">
  A cozy, interactive coast for your desktop — running on the real sky,
  the real sun, and the real tide for wherever you are.
</p>

<p align="center">
  <a href="https://github.com/ChrisX101010/Tidepool/releases/latest">
    <img alt="Download" src="https://img.shields.io/github/v/release/ChrisX101010/Tidepool?label=download&style=flat-square"></a>
  <img alt="License" src="https://img.shields.io/badge/license-MIT-blue?style=flat-square">
  <img alt="Network requests" src="https://img.shields.io/badge/network%20requests-0-brightgreen?style=flat-square">
  <img alt="Dependencies" src="https://img.shields.io/badge/dependencies-none-brightgreen?style=flat-square">
  <img alt="Size" src="https://img.shields.io/badge/one%20file-161%20KB-lightgrey?style=flat-square">
</p>

---

## Install

1. Install [Lively Wallpaper](https://www.rocksdanister.com/lively/) — free, open source, Microsoft Store.
2. Download **`Tidepool.zip`** from [the latest release](https://github.com/ChrisX101010/Tidepool/releases/latest) and extract it somewhere permanent.
3. In Lively: **+** → **Browse** → select `index.html`.
4. **Settings → Wallpaper → Input**: allow mouse and keyboard, or the scene won't respond to you.
5. Right-click the wallpaper → **Customise** → set your latitude and longitude.

That's it. Nothing else to configure, nothing phones home.

---

## What makes it different

**The sky is real.** Ninety-one catalogued stars with true right ascension and
declination, projected through local sidereal time to your latitude. Polaris
sits at exactly your latitude above the northern horizon. Vega is overhead in
August, Orion arrives in winter. Below the equator the camera turns to face
north, the sun runs right to left, and the Southern Cross comes up. Twenty
constellations to trace, and the set resets each night as the sky turns.

**The sun and moon are real.** Sunrise, sunset and the colour of the light come
from the NOAA solar position algorithm — accurate to about a minute. The moon
runs a proper lunar ephemeris: correct position, correct phase, maria roughly
where they actually are, earthshine on the dark limb.

**The tide is real.** Moon phase sets the range — springs at new and full when
Sun, Earth and Moon align, neaps at the quarters when their pulls oppose. The
cycle is semidiurnal and anchored to the moon's hour angle. It moves the
waterline up the beach, drives the strength of the surf, sets how hard the
moored boat rides, and stops the tidal stream dead at slack water.

**Every sound is synthesised.** Not one audio file. Surf is filtered noise with
a swell envelope; waves break on their own irregular rhythm; gulls are FM
chirps; the ship's horn is three detuned sawtooths; the buoy bell is four
bronze partials. The music is *generated* — a lo-fi mode in a random key each
session with a Rhodes built from an FM pair, swung hats and vinyl crackle, and
a Nocturne mode for the dark hours. Neither ever repeats.

**It cannot touch your computer.** No network requests of any kind. No `eval`,
no `Function`, no dynamic imports, no external scripts, fonts or assets. One
file you can read top to bottom.

---

## Things to do

| | |
|---|---|
| **Hold and aim** over the water, release | Skip a stone. Flat and fast runs longest — the record is 14. |
| **Click the stars** after dark | Trace constellations. The figure reveals its shape as you go. |
| **`,`** and **`.`** | Turn the view. You can't see the whole sky at once. |
| **`H`** | Hide every widget for a clean scene. **`R`** puts them back. |
| **Drag any panel** by its header | Move it. **−** collapses it. Positions persist. |

Watch for: dolphins on the horizon, a whale about once an hour, the lighthouse
flashing every 7.5 seconds, a bottle washing in when you've been away too long,
and — about one night in nine — the water glowing with a plankton bloom.

---

## Verify the security claim

Don't take it on trust. Clone it and check:

```bash
grep -c "eval(\|new Function\|fetch(\|XMLHttpRequest\|http://\|https://" index.html
```

That prints **0**. There is one file, and you can read the whole of it.

This matters more than it might seem. In 2026 Kaspersky found malware
distributed as Wallpaper Engine "application wallpapers" — real executables
running as your desktop background — and Wallpaper Engine removed that
category entirely rather than try to police it. Tidepool is HTML in a
sandboxed WebView. It has no filesystem access, opens no ports, and reaches
no network. Your music and video are read from local files you pick.

---

## Performance

The scene is drawn on a small design grid and supersampled, so a 4K display
costs about the same as a laptop screen. Frame timing is measured
continuously: if the machine can't keep up, render quality steps down before
anything stutters, and climbs back when there's headroom. The loop halts
entirely when the window is hidden, and Lively suspends the process during
fullscreen apps.

---

## Settings

Right-click in Lively → **Customise**. Latitude and longitude, view bearing,
render quality, frame rate, clock size and position, volume, ambience,
generated music, your own audio and video, break reminder, and a toggle for
each widget.

---

## Roadmap

- Weather modes — rain, storm, fog, wind — driven through Lively's property
  channel, so the wallpaper still makes no network calls of its own
- A companion Android app sharing the design language

---

## Credits

Star positions from public astronomical catalogues. Solar position from the
NOAA general solar calculator. Lunar theory abridged from Meeus. Everything
else written from scratch.

MIT licensed — see `LICENSE.txt`.
