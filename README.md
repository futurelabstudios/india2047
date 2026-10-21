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
| W A S D | Fly (Shift to boost) |
| Q E | Turn |
| R F | Climb / descend |
| I | Immersive view of a place (← → for the next place, Esc to leave) |
| N | Time of day |
| C | Save a photo of the view |
| L | Copy a link to this exact view |
| T P M H ? | Tour, places, music, hide controls, help |

New to it? The **Flight school** card in the corner lists every control and ticks each one off as you use it.

## What's inside

**10 places:** Thiksey (Ladakh), Golden Temple, India Gate, Taj Mahal, Ghats of Varanasi, Howrah Bridge, Charminar, Vidhana Soudha, Kerala Backwaters, Gateway of India.

**19 marvels to discover:** Gaganyaan launch, Chenab Bridge, Mumbai–Ahmedabad bullet train, air-taxi vertiport, vertical farm, green hydrogen hub, Gulf of Kutch wind farm, Vizhinjam port, Hanle observatory, Bharatiya Antariksh Station, thorium power, robot farms of Punjab, drone delivery, river dolphins, floating solar, elephant corridor, Statue of Unity, drone light show, Uttarayan kite sky.

Plus maglev lines, EV traffic, air taxis, people, birds, ships, kites and fireworks at night.

**Immersive view:** every place has a full-screen, letterboxed view. The drone drops to eye level and circles the landmark slowly, the place name stands in white behind the monument, and the story is shown beside it.

**Grounded in real physics:**

- **Sun:** it follows its true path for 15 August 2047 at the drone's position (NOAA solar equations). It rises in the east-north-east, stands about 82° high at noon over central India, and sets in the west-north-west.
- **Drone:** it has momentum and air drag. Flicks glide to a stop and it banks into turns.
- **Gaganyaan launch:** an integrated LVM3 ascent with real thrust, mass flow, drag in an exponential atmosphere and a gravity turn. Live T+ telemetry shows altitude, speed and g-load.
- **Fireworks:** shells rise ballistically, and the stars slow under air drag as they fall.
- **Kites:** they fly tethered on sagging lines, downwind in the monsoon breeze, sweeping fighter-kite figure-eights.
- **Air taxis:** they bank at the coordinated-turn angle, tan φ = v²/(g·r).

The map itself is stylised: landmarks are drawn far larger than the map scale so you can see them.

## Contribute

This is meant to grow. Add your city, your state's landmark, a marvel you believe India will build, better music, better performance on phones, or translations. Read [CONTRIBUTING.md](CONTRIBUTING.md) to get started; it explains where everything lives in `index.html` and how to add a place or a marvel in a few lines.

Good first contributions:

- Add a place from a state that isn't on the map yet (North-East, Odisha, Rajasthan, Goa, Tamil Nadu…)
- Add a marvel with a real, sourced basis for its 2047 claim
- Improve mobile performance or accessibility
- Translate the UI and place text into Indian languages

## Share your 2047 idea

You don't need to write code to shape India 2047. Imagine how India solves one of its big challenges by 2047 and share it openly; the strongest ideas can become marvels in the flythrough.

Themes: Health · Education · Climate & Energy · Cities & Mobility · Agriculture & Food · Water · Governance · Jobs & Economy · Culture & Languages · Science & Space

- **No coding:** open a new issue with the **"Imagine a 2047 solution"** template.
- **Add it directly:** copy [`solutions/_TEMPLATE.md`](solutions/_TEMPLATE.md) to `solutions/<theme>-<short-name>.md`, fill in the problem today, India in 2047, how we got there and a first step anyone could take this year, then open a pull request.

See [`solutions/`](solutions/) for ideas already shared. Ideas in any Indian language are welcome.

## Project structure

```
index.html     the whole experience: HTML, CSS and JavaScript
score.mp3      the soundtrack
solutions/     imagined 2047 solutions, one Markdown file each, plus the template
CONTRIBUTING.md
.github/       issue templates, PR template, Pages deploy workflow
```

## Deploying with GitHub Pages

The workflow in `.github/workflows/pages.yml` publishes the site on every push to `main`. One-time setup: **Settings → Pages → Build and deployment → Source: GitHub Actions**.

## License

Code is released under the [MIT License](LICENSE). The soundtrack (`score.mp3`) was created by Futurelab Studios and is included for use with this project.

Built by [Futurelab Studios](https://futurelabstudios.com) and contributors.
