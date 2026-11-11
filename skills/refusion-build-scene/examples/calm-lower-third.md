# Example: a calm lower third

**Status:** a plan with the engine's means named; its ids exist in this build. The batch it starts from, `recipes:lower-third`, was run and looked at; the changes named here were not.

**The brief:** "A lower third for the speaker, name and title, 16:9, four seconds. Calm and clean."

## Direction

Calm product interface ([styles.md](../references/craft/styles.md), direction 1). The name is focal; the title supports. A thin bar anchors the pair to the left edge. Everything is one unit: it comes in and goes out as one.

## The plan

| Time | Element | Role | Verb | Arrives | Holds | Leaves | Means |
|---|---|---|---|---|---|---|---|
| 0.2 s | Bar | support | draws | 0.4 s | to 3.5 s | with the unit | the bar of `recipes:lower-third` |
| 0.35 s | Name | focal | rises | 0.5 s, ease out | to 3.5 s | 0.3 s, ease in | `text.motion:1:4` (Rise) in, `text.motion:2:1` (Fade) out |
| 0.55 s | Title | support | fades | 0.4 s | to 3.5 s | with the name | `text.motion:1:1` (Fade) in |

The name takes the longer entrance because it matters more; the title starts after it and finishes just after it (overlap, not a queue). Leaving takes about 60% of arriving. The unit as a whole slides out with `layer.edge:recipe:21` on the layer that shows the scene.

## The build

One batch for the unit (a scene with its own canvas, about 1080 by 300, `guide.read` topic `units`) and the layer that shows it on the main timeline. Used for each speaker: a scene shown several times; `composition.duplicate` first when a use must differ.

## The check

`render.look` at 0.3 s, 0.8 s, 2.0 s, 3.7 s. `scene.layout` at 2.0 s: the text is inside the safe margins and large enough for the canvas. `motion.trace` on the name: one bell, no stop. In Arabic, move by word and look at the joined letters.
