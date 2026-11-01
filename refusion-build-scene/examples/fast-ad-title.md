# Example: a five second ad on the beat

**Status:** a plan with the engine's means named, written from the engine's tables; its ids exist in this build. It has not been run and looked at on a device. The Arabic and English copy is a stand-in.

**The brief:** "A five second 9:16 ad for a store: a discount, a price, the logo. Fast, in Arabic with an English line." Music at 120 beats a minute (a beat is 0.5 s).

## Direction

Bold kinetic type ([styles.md](../references/craft/styles.md), direction 2). One idea: the discount. The headline is the focal element; the English line supports; the price badge is the accent; the ground is alive. One accent colour; the badge is the only warm thing on screen.

## The plan

| Time | Element | Role | Verb | Arrives | Holds | Leaves | Means |
|---|---|---|---|---|---|---|---|
| 0.0 s | Ground | ground | drifts | at once | all piece | with the piece | a fill of colour points that twists slowly: `recipes:colour-points` |
| 0.5 s (beat 1) | Arabic headline | focal | snaps up | 0.5 s, on the beat | to 3.0 s | gathers away, 0.3 s | `text.motion:recipe:14`, tune its numbers; exit `text.motion:recipe:26` |
| 1.0 s (beat 2) | English line | support | pops in by word | 0.6 s, a delay between words | to 3.0 s | with the headline | `text.motion:recipe:1` |
| 1.5 s (beat 3) | Price badge (a shape and its text, one unit) | accent | bounces in | 0.6 s | to 3.5 s; a pulse on beats 5 and 6 | zooms out, 0.25 s | `layer.edge:recipe:9`; the pulse `recipes:pulse-on-beat`; exit `layer.edge:recipe:24`; the card sized to its text `recipes:card-sized-to-text` |
| 4.0 s (beat 8) | Logo | focal | cuts in | hard cut on the beat | to 5.0 s | | no transition; a short `layer.edge:recipe:5` (Zoom in) only if the cut is too hard |

Reading time check: the headline has three words, so about two seconds of hold from its landing at about 0.9 s: it is whole from 0.9 s to 3.0 s. The English line is whole from about 1.6 s. Both have 1.4 s to 2.1 s each. Reduce words, not time, if the copy grows.

## The build

1. `media.library_snapshot` first: the logo and any picture the designer brought.
2. One batch for the ground (a background layer with colour points), set the beat grid on the scene (`beat.set`), read the times (`beat.grid`).
3. One batch for the headline, one for the English line, one for the badge as a unit (a scene), with `session.validate` before each `session.batch`.
4. Place the logo on beat 8 with `layer.insert_source` and `layer.move`.

## The check

`render.look` at 0.3 s, 0.9 s, 1.7 s, 3.2 s and 4.5 s: the still at each is designed; `scene.layout` at the same times (nothing outside the canvas, no overlap by ink, nothing too small). `motion.trace` on the headline and the badge for the speed shape. `render.cost` over the whole piece to see where the heavy frames are (a blur in an entrance is a likely place; it is not measured until you ask). Tell the owner what you looked at and what you could not (the device, the cost on a phone).
