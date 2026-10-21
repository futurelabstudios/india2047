# Contributing to India 2047

Thank you for helping build this. Everyone is welcome: developers, 3D artists, musicians, writers, translators, and people who just know their city well.

## Ground rules

- **Keep it one file.** Everything lives in `index.html`. No build step, no bundler. three.js is loaded from a CDN at a pinned version (r147).
- **Optimistic, grounded futures.** Marvels should extend something real (a project, a policy, a technology that exists today). Mention the basis in your PR.
- **Respectful and inclusive.** Every region, faith and language is part of this India. Avoid political or partisan messaging.
- **Performance matters.** Many people will open this on a mid-range phone. Prefer instanced meshes, reuse materials, and call `mergeGroup()` on static geometry.

## Getting started

1. Fork the repo and clone your fork.
2. Run `python3 -m http.server 8000` and open http://localhost:8000.
3. Create a branch: `git checkout -b add-konark-temple`.
4. Make your change, test it in Chrome and Safari (and a phone if you can).
5. Open a pull request using the template.

## Where things live in `index.html`

| Section (search for the comment) | What it does |
|---|---|
| `// ---------- Places ----------` | The 10 tour stops: name, coordinates, story text, chips, camera view |
| `// ---------- Height field ----------` | Terrain: Himalaya, Ghats, Deccan, flattened pads for places and marvels |
| `// ---------- Rivers ----------` | Ganga, Yamuna and others as polylines |
| `// ---------- Landmarks ----------` | One `build…()` function per place (Taj, India Gate, …) |
| `// ---------- Cities, energy, transport, life ----------` | Procedural towers, roads, solar, wind, maglev, air taxis, clouds, birds, ships |
| `// ---------- Marvels ----------` | The discoverable marvels, each registered with `marvel({...})` |
| `// ---------- People ----------` | Walkers and seated crowds |
| `// ---------- Music ----------` | Generated raga fallback score |
| `// ---------- Drone camera ----------` | Flight, tour, input |
| `// ---------- UI ----------` | Captions, popovers, discoveries, minimap |

Coordinates use `ll(lat, lon)`, which converts real latitude/longitude into world units (`SCALE = 70` units per degree).

## Add a marvel

```js
const KONARK = ll(19.89, 86.09);
marvel({ id: 'konark', name: 'Konark Sun Temple', kicker: 'Heritage · Odisha', x: KONARK.x, z: KONARK.z, y: 30, keep: 30,
  text: 'One or two sentences on what the player is looking at in 2047.',
  build() {
    const g = grp(KONARK.x, heightAt(KONARK.x, KONARK.z), KONARK.z);
    box(20, 6, 20, MAT.sandstone, 0, 0, 0, g);   // use the helpers: box, cyl, onion, hemisphere, add
    return g;                                     // returned groups are merged for performance
  } });
```

- `y` is how high the discovery beacon floats; `keep` clears trees and buildings in that radius.
- For moving parts, set `obj.userData.dyn = 1` so it isn't merged, and push an update function to `marvelAnim`.
- The discovery counter updates automatically.

## Add a place (tour stop)

1. Add an entry to `PLACES` with `id`, `name`, `short`, `region`, `lat`, `lon`, `ground`, `r`, `view`, `text` and `chips`.
2. Write a `buildYourPlace()` function and call it in `buildWorld()`.
3. Add the `id` to `TOUR_ORDER`, and optionally to `KEEP`, `CITY_CFG` and `buildRoads()`.

## Pull request checklist

- [ ] Runs with no console errors
- [ ] Frame rate is still smooth on a laptop (and ideally a phone)
- [ ] Factual basis for any new claim is linked in the PR
- [ ] Screenshot or short clip attached

## Code of conduct

By participating you agree to our [Code of Conduct](CODE_OF_CONDUCT.md).
