# India 2047

**15 August 2047. India is a developed nation: clean rivers, clear air, a space station overhead and prosperity that reached every village.**

India 2047 is an open-source, browser-based drone flythrough of that future. Fly over ten places you know, from Thiksey in Ladakh to the Kerala backwaters, and discover the marvels that got us there: a Gaganyaan launch, the Chenab rail bridge, green hydrogen in Kutch, river dolphins at Varanasi and more.

It is one HTML file, built with [three.js](https://threejs.org/). No build step, no install.

▶ **Play it:** https://futurelabstudios.github.io/india2047/ *(after GitHub Pages is enabled, see below)*

## Run it locally

```bash
git clone https://github.com/futurelabstudios/india2047.git
cd india2047
python3 -m http.server 8000
# open http://localhost:8000
```

A local server is needed so the browser can load `score.mp3`. If the score can't load, the page falls back to a live, generated raga score.

## Controls

| Input | Action |
|---|---|
| Drag | Look around |
| Right drag / Shift + drag | Slide across the ground |
| Scroll / pinch | Zoom toward the cursor |
| Double-click | Dive to that spot |
| W A S D | Fly |
| Q E | Turn |
| R F | Climb / descend |
| T P N M H | Tour, places, time of day, music, hide controls |

## What's inside

**10 places:** Thiksey (Ladakh), Golden Temple, India Gate, Taj Mahal, Ghats of Varanasi, Howrah Bridge, Charminar, Vidhana Soudha, Kerala Backwaters, Gateway of India.

**19 marvels to discover:** Gaganyaan launch, Chenab Bridge, Mumbai–Ahmedabad bullet train, air-taxi vertiport, vertical farm, green hydrogen hub, Gulf of Kutch wind farm, Vizhinjam port, Hanle observatory, Bharatiya Antariksh Station, thorium power, robot farms of Punjab, drone delivery, river dolphins, floating solar, elephant corridor, Statue of Unity, drone light show, Uttarayan kite sky.

Plus maglev lines, EV traffic, air taxis, people, birds, ships, four times of day and fireworks at night.

## Contribute

This is meant to grow. Add your city, your state's landmark, a marvel you believe India will build, better music, better performance on phones, or translations. Read [CONTRIBUTING.md](CONTRIBUTING.md) to get started; it explains where everything lives in `index.html` and how to add a place or a marvel in a few lines.

Good first contributions:

- Add a place from a state that isn't on the map yet (North-East, Odisha, Rajasthan, Goa, Tamil Nadu…)
- Add a marvel with a real, sourced basis for its 2047 claim
- Improve mobile performance or accessibility
- Translate the UI and place text into Indian languages

## Project structure

```
index.html     the whole experience: HTML, CSS and JavaScript
score.mp3      the soundtrack
CONTRIBUTING.md
.github/       issue templates, PR template, Pages deploy workflow
```

## Deploying with GitHub Pages

The workflow in `.github/workflows/pages.yml` publishes the site on every push to `main`. One-time setup: **Settings → Pages → Build and deployment → Source: GitHub Actions**.

## License

Code is released under the [MIT License](LICENSE). The soundtrack (`score.mp3`) was created by Futurelab Studios and is included for use with this project.

Built by [Futurelab Studios](https://futurelabstudios.com) and contributors.
