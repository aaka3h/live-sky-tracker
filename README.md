# Live Sky Tracker

A single-page web app that shows where the Sun, Moon, planets, stars and satellites are in your sky right now, based on your device's location and clock.

**Live demo:** https://aaka3h.github.io/live-sky-tracker/

## Features

- **Live sky** whose colours follow the Sun's altitude: daylight, golden hour, sunset, twilight and night.
- **Sun** with atmospheric glow and lens flare; **Moon** drawn with its true phase and tilt.
- **5,044 real stars** (Hipparcos catalogue, to magnitude 6), the Milky Way band, and all 88 constellations with stick figures.
- **Planets** Mercury to Neptune from JPL's approximate orbital elements (checked against astropy to within ~0.07°).
- **Satellites** propagated with SGP4 (satellite.js), using orbit data (TLEs) from CelesTrak, or TLE lines you paste in.
- **Tap any object** to open the Inspector: name and catalogue ID, azimuth/altitude, RA/Dec, distance, magnitude, constellation, rise/transit/set times (or next pass for satellites), and a short fact.
- **Search** (`/`) for any planet, named star, HIP number or satellite, then lock the camera onto it.
- Compass horizon, overhead mini-map, phone compass mode, and a ±12 hour time scrubber with time-lapse.
- Dashboard with countdowns to golden hour, sunrise, sunset, moonrise and moonset.

## Run it

Open `index.html` in a browser, or visit the GitHub Pages link above. Location needs HTTPS (Pages) or a local file; if you deny it, pick a place from the location menu.

### Controls

| Action | Mouse / keyboard | Touch |
| --- | --- | --- |
| Look around | Drag, arrow keys | Drag |
| Zoom | Scroll, `+` / `-` | Pinch |
| Inspect | Click an object | Tap an object |
| Search | `/` | Tap the search bar |
| Play / pause time-lapse | `Space` | Play button |
| Back to live time | `L` | Live button |
| Hide panels | `H` | Eye button |

## How it works

- Sun and Moon positions, phases and rise/set: a port of [SunCalc](https://github.com/mourner/suncalc).
- Planets: JPL Keplerian elements (Standish, valid 1800–2050).
- Satellites: [satellite.js](https://github.com/shashwatak/satellite-js) SGP4, TLEs from [CelesTrak](https://celestrak.org) (cached for 2 hours).
- Rendering: HTML Canvas 2D at 60 fps; styling with Tailwind CSS (compiled and inlined).

Accuracy is good to a fraction of a degree for planets, the Sun and the Moon. Satellite positions depend on how fresh the TLE data is.

## Credits

- Star, constellation-line and boundary data: [d3-celestial](https://github.com/ofrohn/d3-celestial) © Olaf Frohn, BSD-3-Clause.
- SunCalc © Vladimir Agafonkin, BSD-2-Clause.
- satellite.js © Shashwat Kandadai and UCSC, MIT.
- Tailwind CSS © Tailwind Labs, MIT.

## License

MIT for the app code. See [LICENSE](LICENSE) and [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
