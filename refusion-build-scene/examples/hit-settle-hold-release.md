# Example: hit, settle, hold, release (one headline)

**Status:** a plan with the engine's means named. Its ids exist in this build; the numbers are tagged as in [timing.md](../references/craft/timing.md). It has not been run and looked at on a device: build it, look, and adjust.

**The brief:** a 9:16 fast ad; a three-word Arabic headline must land with energy, be read comfortably, and leave without dragging. 120 beats a minute (a beat every 0.5 s).

## The plan

| Part | Time | What happens | Number | Tag |
|---|---|---|---|---|
| Hit | beat 1 (0.5 s) | The headline crosses most of its way at once, leaning and blurred | about 80% of the way in the first 0.1 s | [measured] |
| Settle | 0.6 s to 0.9 s | The last 20% takes the longer tail; the lean and the blur clear as it brakes | about 0.4 s in all | [measured] |
| Hold | 0.9 s to 3.0 s | Still. The words are read. | three words: about 2 s | [start] |
| Release | beat 6 (3.0 s) | Gathers speed to the left and is gone | 0.25 s to 0.3 s | [start], [measured] for the shape |
| Rest | 3.3 s to 4.0 s | Only the ground moves, slowly | | |

## The means

1. The headline is one text layer. `text.motion:recipe:15` (Snap in leaning from the left) is the nearest recipe: its move cruises to 81% of its way by a quarter of its time and then brakes, blur and lean clear by about half, the text is opaque by 40% of the time. Add it with `inspector.add` (`item=library`, `kind=text.motion:recipe:15`), or give the same with `text.motion_set` in a batch.
2. Read what it does: `motion.channels` for its pace, `scene.snapshot` for its numbers. Change the duration and the distance to the piece with `property.set`; change a channel's pace with `motion.channel_set`.
3. Release: `text.motion:recipe:26` (Gather out to the left), with its length shortened to the 0.25 s to 0.3 s the plan asks.
4. Put the hit on the beat: get the times with `beat.grid` (`beat.set` first if the scene has none) and place the layer with `layer.move`.
5. Hold: do not key anything between the settle and the release.

## The check

- `motion.trace` on the headline around beat 1, with `explain`: the speed graph should show one fast bell and a long tail, not a bell and a second bump; the move should have crossed about 80% of its distance by 0.1 s after the start; blur and lean should be gone with the tail.
- `render.strip` over 0.5 s to 1.0 s: no word torn from its line; Arabic letters stay joined (move Arabic by word).
- `render.look` at 1.5 s: the headline is whole, still and readable; at 3.2 s: nothing of it left.
- If the hold feels long or short, change the words before you change the hold ([timing.md](../references/craft/timing.md)).
