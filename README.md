# Melt 🍄

Five stages, two dreamers, one keyboard. Fizz and Drift run, climb, fall and swim
through a melting world, eating mushrooms as they go. Each stage moves in a
different direction — and the haloed mushrooms are never on the easy path.

Everything is a single `index.html`: vanilla JS, one `<canvas>`, sound synthesised
at runtime. No build step, no dependencies.

## Play

Open `index.html` in any modern browser.

To serve it locally instead:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

It works as-is on GitHub Pages — point Pages at the repository root.

## Controls

Both players share one keyboard. Pick **1 player** or **2 players** on the title
screen.

| | Run | Jump |
|---|---|---|
| **Fizz** (pink) | `A` / `D` | `W` |
| **Drift** (teal) | `←` / `→` | `↑` |

Solo plays as Fizz and accepts either WASD or the arrow keys. `M` toggles sound.

Everyone can **double jump** — tap jump again in mid-air. Every ledge can be
jumped up through and landed on. In two-player, standing on the other player's
head gives you a **boost**.

On touch devices the game goes fullscreen landscape and shows a thumbstick and a
jump button; touch is single-player.

## The five stages

Each stage is its own world, with its own size, camera axis and threat.

| | Stage | Direction | Threat |
|---|---|---|---|
| 1 | The Meadow | run east under a melting sun | a snail in the way |
| 2 | The Forest | over the rocks, under the pines | — |
| 3 | The Canopy | climb — the dark rises behind | a roach |
| 4 | The Downpour | fall; the flood is faster than you | the flood |
| 5 | The Deep | swim — something is awake | an angler |

## Mushrooms

Edible mushrooms are **1 point**. Haloed ones are **2 points** and grant a power:

| Mushroom | Power | Effect |
|---|---|---|
| Chanterelle | Magnet | Drags loose mushrooms to you |
| Morel | Triple jump | A second mid-air jump on top of yours |
| Porcini | Giant | Grow huge — stomps hit twice as hard |
| Indigo | Swift | Run half again as fast |
| Enoki | Spring | Jump noticeably higher |
| Shiitake | Shield | Soaks up the next hit |
| Oyster | Glide | Hold jump to drift down slowly |
| Amethyst | Ghost | Nothing can touch you |
| Puffball | Spore Bomb | Bursts at once — wounds the boss, clears the swarm |
| Hedgehog | Spines | Hurt whatever runs into you |
| Agaric | Glow | Blaze with light, score double |
| Liberty | Slow time | Enemies move at half speed |

Two haloed mushrooms in a row **reverses your controls**. Somewhere in the run a
butterfly passes through and steals a mushroom — catch it and you'll see things.

## Notes

The only external resource is the Google Fonts stylesheet for *Bagel Fat One* and
*Space Mono*; the game falls back to system fonts and plays fine offline without
it. All artwork is drawn to canvas or inlined as SVG data URIs, and all sound is
generated with the Web Audio API — there are no asset files.
