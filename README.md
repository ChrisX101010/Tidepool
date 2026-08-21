# Tidepool

A cozy, interactive desktop scene for [Lively Wallpaper](https://www.rocksdanister.com/lively/).

A quiet stretch of coast that runs on your actual clock and your actual sky.
Skip stones, trace real constellations, keep notes, and let the sea run over
your feet.

## What makes it different

**The sky is real.** Sixty catalogued stars with true right ascension and
declination, projected through local sidereal time to your latitude. Polaris
sits at exactly your latitude above the northern horizon. Vega is overhead in
August, Orion arrives in winter, Scorpius stays low if you live far enough
north. Set your coordinates and it is your sky, not a decoration.

**The sun is real too.** Sunrise, sunset and the colour of the light come from
the NOAA solar position algorithm — accurate to about a minute. Golden hour
happens when golden hour happens.

**Every sound is synthesised.** Not one audio file. The surf is filtered noise
with a swell envelope, waves break on their own irregular rhythm, gulls are FM
chirps, the ship's horn is three detuned sawtooths, the buoy bell is four
bronze partials. The lo-fi is *generated*: a ii–V–I–vi progression in a random
key each session, a Rhodes built from an FM pair, swung hats, a wandering
pentatonic melody and vinyl crackle. It never repeats.

**It cannot touch your computer.** No network requests of any kind. No `eval`,
no `Function`, no dynamic imports, no external scripts, fonts or assets.
One file you can read top to bottom. Your music and video are read from local
files you pick; nothing is uploaded anywhere.

## Things to do

- **Hold and aim** anywhere over the water, release to skip a stone. Each hop
  scores above the surface.
- **Click the stars** after dark to trace constellations. Thirteen to find.
  Completed ones stay lit forever.
- **Drag any widget** by its header. Collapse with the − button.
- **H** hides everything for full immersion. **R** puts the widgets back.
- **Ambience** and **Lo-fi** in the sound panel. They are built to run together.

## Setting your location

Right-click Tidepool in Lively's library → Customise → latitude and longitude
in decimal degrees, east positive. Defaults to Belgrade.

Works anywhere on Earth. The camera defaults to facing the equator — south if
you are north of it, north if you are south — because that is where the sun and
moon are. You cannot see the whole sky at once, so press **,** and **.** to turn
the view: face the pole for the circumpolar figures, the Plough from the north
or the Southern Cross from the south. Twenty constellations, ninety-one stars.

## Performance

The scene renders at 480×270 and upscales with nearest-neighbour, so a 4K
display costs the same as a laptop screen. Frame rate is delta-timed and capped
at 30 or 60. The loop halts completely when the window is hidden, and Lively
suspends the whole process during fullscreen apps.

## Verifying the security claim

Clone it and check for yourself. This should print 0:

    grep -c "eval(\|new Function\|fetch(\|XMLHttpRequest\|http://\|https://" index.html

There is one file. Read it top to bottom if you like.

## Credits

Star positions from public astronomical catalogues. Solar position from the
NOAA general solar calculator. Everything else written from scratch.
