# Design and timing

Starting points for a scene that looks designed. They are defaults, not laws: change them when the request or the look asks for it, and check the result with `render_look` and `scene_layout`.

## Plan the scene before the first batch

- **One idea per scene.** Say in one sentence what the viewer should take in. Everything on screen serves that sentence.
- **One focal element.** One thing is largest and arrives first. Support it with at most two other levels of size. Use one accent colour against a calm background.
- **Contrast first.** Text sits on a plain or darkened area, not on a busy picture. If the background is busy, add a calm shape behind the text rather than making the text smaller.
- **Margins.** Keep text away from the edges. The engine knows the safe area for the canvas: `scene_layout` reports text that reaches into it, and `guide_read` with the topic `checks` explains each check. Do not guess the numbers.
- **Format.** Read the canvas size from `scene_brief`. Change it with the project settings tool only when the user asks for another shape; a tall 9:16 canvas and a wide 16:9 one need different layouts.

## Timing

Work in frames of the project's frame rate, so every start and duration is an exact fraction (`guide_read` topic `time`).

- **Entrances** are short: about 0.3 to 0.6 s. **Exits** are shorter than entrances, or the element simply ends with the scene.
- **Reading time.** A short text needs its time to be read once the entrance has finished. As a rule of thumb, allow about a third of a second per word plus a second; lengthen it for Arabic or small text.
- **Order.** Elements arrive in the order they matter, not all at once. Stagger a group by a few frames each. Keep the stagger the same across the group.
- **Hold the end.** The last frame should be a deliberate hold, not a cut in the middle of a movement.

## Motion

- Ease out for things that arrive, ease in for things that leave. Avoid a linear move except for a constant drift. Use a spring, bounce or elastic shape sparingly, for one element that should feel alive; many at once look noisy (`guide_read` topic `animation`).
- Use the same easing and similar durations across a scene so it feels like one piece.
- Move things along one direction in a scene; do not mix a slide from the left with a slide from above for the same kind of element.
- A fast move drawn sharp looks like a stutter in the exported file. `scene_motion` lists those stretches; follow `guide_read` topic `motion` (motion blur, or a slower move).
- Do not animate everything. Static text on a moving background is often enough.

## Finishing

- Look at the first frame, the frame where the entrance has just finished, and the last frame.
- Check `scene_layout` at each of those times: nothing outside the canvas, no two texts over each other, nothing too small to read.
- Group a piece that repeats (a lower third used several times) as a scene instead of copying layers (`guide_read` topic `layers`).
