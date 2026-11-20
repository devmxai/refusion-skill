# Handoffs: one scene to the next

A piece is felt at its seams. Where one scene ends and the next begins, the eye either keeps going or stumbles. Tags as in [timing.md](timing.md): **[measured]**, **[engine]**, **[start]**.

## Three ways across, chosen on purpose

1. **A transition on the cut.** It says how the two belong together (see the meanings in [choreography.md](choreography.md)). [engine] A `transition` on the layer that goes out puts one on the cut where it ends and the next layer on **its row** begins: both on one row (their `track`), the second starting exactly where the first ends. It is refused when they are on two rows (`not_same_row`) or do not touch (`not_adjacent`). The kinds and their lengths are in `transition.catalog`.
2. **An overlap.** The next scene begins a few frames before the first ends, on the row above, so its entrance plays over the last moment of the one leaving. Nothing new is needed: it is two layers and their times. [start] 4 to 8 frames at 30 fps for a quick handover, 12 to 20 for a calm one. The leaving scene should already be moving out (its release) when the next one hits.
3. **A hard cut, meant.** On a beat, in a fast piece, a straight cut is the strongest choice. It is a decision: say so in your plan.

A cut that is none of these (two scenes end to end, on two rows, nothing moving across the seam) reads as a jump. [engine] The engine says so in the reply of the edit that made it: the note `hard_handoff`, with the time of the cut and whether a transition can go there.

## Carry the motion across

- **Match the direction and the speed.** The element that leaves to the left and the one that arrives from the right at the same speed read as one movement. [engine] `motion.trace` gives both speeds in numbers: compare the last frames of the one leaving with the first of the one coming.
- **Match the moment.** The handover lands on a beat when the piece has one (the scene's `beat`), and the new scene's first hit comes on it.
- **A match cut** keeps a shape, a colour or a position across the seam: the circle that ends one scene is the circle that starts the next. Build both sides so the shared element sits at the same place on the frame of the cut, and check it with `render.strip` over the seam.

## What the engine does not do yet

[engine] A sequence of scenes that overlap by a stated amount, kept when one is retimed, is not built (SUPERPOWER ME-B3). Today an overlap is two layer times you keep yourself: when you change one scene's length, move the next.
