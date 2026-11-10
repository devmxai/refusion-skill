# Ready-made motion

Written by `rpro skill-reference --write` from catalog version 3, fingerprint `c1623f4685e29307`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

How a layer or a text comes in, goes out, and moves all the while it is there. Add one with `inspector.add` (the item and kind on its Add line), or give the same with `layer.motion_set` (any layer) or `text.motion_set` (the words of a text); a preset's numbers are then ordinary properties. A **preset** is one move; a **recipe** is a named look with its unit, its order, its delay and its pace set. What each does is read from the engine's tables, in the units named: for a text, ems of its size; for a layer, a share of the canvas's shorter side.

# A layer (29)

## Layer in

- **Fade** — `layer.edge:1:1`
  - It fades in, fully opaque by 100% of the motion, in place.
  - Add: `inspector.add item=library kind=layer.edge:1:1`
- **Pop** — `layer.edge:1:2`
  - It grows from 55% of its size and fades in, fully opaque by 50% of the motion.
  - Add: `inspector.add item=library kind=layer.edge:1:2`
- **Slide** — `layer.edge:1:3`
  - It comes in from the left, 45% of the canvas's shorter side away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=layer.edge:1:3`
- **Rise** — `layer.edge:1:4`
  - It comes in from below, 45% of the canvas's shorter side away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=layer.edge:1:4`
- **Slide in from the left** — `layer.edge:recipe:1`
  - The layer comes in from the left, 60% of the canvas's shorter side away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=layer.edge:recipe:1`
- **Slide in from the right** — `layer.edge:recipe:2`
  - The layer comes in from the right, 60% of the canvas's shorter side away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=layer.edge:recipe:2`
- **Drop in** — `layer.edge:recipe:3`
  - The layer comes in from above, 50% of the canvas's shorter side away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=layer.edge:recipe:3`
- **Rise in** — `layer.edge:recipe:4`
  - The layer comes in from below, 50% of the canvas's shorter side away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=layer.edge:recipe:4`
- **Zoom in** — `layer.edge:recipe:5`
  - The layer grows from 20% of its size and fades in, fully opaque by 50% of the motion.
  - Add: `inspector.add item=library kind=layer.edge:recipe:5`
- **Spin in** — `layer.edge:recipe:6`
  - The layer grows from 40% of its size, turns 180 degrees and fades in, fully opaque by 50% of the motion.
  - Add: `inspector.add item=library kind=layer.edge:recipe:6`
- **Snap in from the left** — `layer.edge:recipe:7`
  - The layer comes in from the left, 60% of the canvas's shorter side away and fades in, fully opaque by 66.67% of the motion. Lasts 0.6 s. Curve: Smooth. Paced: Move covers 81% of its way by 25% of the time (Linear), then settles (Brake); Fade covers 100% of its way by 40% of the time (Smooth), then settles (Smooth).
  - Add: `inspector.add item=library kind=layer.edge:recipe:7`
- **Snap in from the right** — `layer.edge:recipe:8`
  - The layer comes in from the right, 60% of the canvas's shorter side away and fades in, fully opaque by 66.67% of the motion. Lasts 0.6 s. Curve: Smooth. Paced: Move covers 81% of its way by 25% of the time (Linear), then settles (Brake); Fade covers 100% of its way by 40% of the time (Smooth), then settles (Smooth).
  - Add: `inspector.add item=library kind=layer.edge:recipe:8`
- **Bounce in** — `layer.edge:recipe:9`
  - The layer grows from 5% of its size and fades in, fully opaque by 50% of the motion. Lasts 0.8 s. Curve: Smooth. Paced: Size covers 100% of its way by 100% of the time (Spring Snappy), then settles (Smooth); Fade covers 100% of its way by 25% of the time (Smooth), then settles (Smooth).
  - Add: `inspector.add item=library kind=layer.edge:recipe:9`
## Layer out

- **Fade** — `layer.edge:2:1`
  - It fades out, in place.
  - Add: `inspector.add item=library kind=layer.edge:2:1`
- **Pop** — `layer.edge:2:2`
  - It shrinks to 55% of its size and fades out.
  - Add: `inspector.add item=library kind=layer.edge:2:2`
- **Slide** — `layer.edge:2:3`
  - It goes off toward the left, 45% of the canvas's shorter side away and fades out.
  - Add: `inspector.add item=library kind=layer.edge:2:3`
- **Rise** — `layer.edge:2:4`
  - It goes off toward below, 45% of the canvas's shorter side away and fades out.
  - Add: `inspector.add item=library kind=layer.edge:2:4`
- **Slide out to the left** — `layer.edge:recipe:21`
  - The layer goes off toward the left, 60% of the canvas's shorter side away and fades out.
  - Add: `inspector.add item=library kind=layer.edge:recipe:21`
- **Slide out to the right** — `layer.edge:recipe:22`
  - The layer goes off toward the right, 60% of the canvas's shorter side away and fades out.
  - Add: `inspector.add item=library kind=layer.edge:recipe:22`
- **Drop out** — `layer.edge:recipe:23`
  - The layer goes off toward below, 50% of the canvas's shorter side away and fades out.
  - Add: `inspector.add item=library kind=layer.edge:recipe:23`
- **Zoom out** — `layer.edge:recipe:24`
  - The layer shrinks to 20% of its size and fades out.
  - Add: `inspector.add item=library kind=layer.edge:recipe:24`
- **Spin out** — `layer.edge:recipe:25`
  - The layer shrinks to 40% of its size, turns 180 degrees and fades out.
  - Add: `inspector.add item=library kind=layer.edge:recipe:25`
- **Gather out to the left** — `layer.edge:recipe:26`
  - The layer goes off toward the left, 60% of the canvas's shorter side away and fades out. Lasts 0.45 s. Curve: Smooth. Paced: Move covers 100% of its way by 100% of the time (Gather), then settles (Smooth); Fade after waiting 30% of the time covers 100% of its way by 100% of the time (Smooth), then settles (Smooth).
  - Add: `inspector.add item=library kind=layer.edge:recipe:26`
## Layer loop

- **Wave** — `layer.edge:3:11`
  - Round and round all the while it is there, it moves up and down by 1.8% of the canvas's shorter side.
  - Add: `inspector.add item=library kind=layer.edge:3:11`
- **Wiggle** — `layer.edge:3:12`
  - Round and round all the while it is there, it turns 7 degrees either way.
  - Add: `inspector.add item=library kind=layer.edge:3:12`
- **Pulse** — `layer.edge:3:13`
  - Round and round all the while it is there, it swells and shrinks by 10% of its size.
  - Add: `inspector.add item=library kind=layer.edge:3:13`
- **Sway** — `layer.edge:3:14`
  - Round and round all the while it is there, it moves from side to side by 1.2% of the canvas's shorter side.
  - Add: `inspector.add item=library kind=layer.edge:3:14`
- **Flicker** — `layer.edge:3:15`
  - Round and round all the while it is there, it lets its opacity fall by up to 85%.
  - Add: `inspector.add item=library kind=layer.edge:3:15`
- **Jitter** — `layer.edge:3:16`
  - Round and round all the while it is there, it moves up and down by 0.4% of the canvas's shorter side, moves from side to side by 0.4% of the canvas's shorter side and turns 1.2 degrees either way.
  - Add: `inspector.add item=library kind=layer.edge:3:16`

# A text (38)

## Text in

- **Fade** — `text.motion:1:1`
  - It fades in, fully opaque by 100% of the motion, in place.
  - Add: `inspector.add item=library kind=text.motion:1:1`
- **Pop** — `text.motion:1:2`
  - It grows from 55% of its size and fades in, fully opaque by 50% of the motion.
  - Add: `inspector.add item=library kind=text.motion:1:2`
- **Slide** — `text.motion:1:3`
  - It comes in from the left, 0.9 em away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=text.motion:1:3`
- **Rise** — `text.motion:1:4`
  - It comes in from below, 0.9 em away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=text.motion:1:4`
- **Track** — `text.motion:1:5`
  - It each unit starts 0.35 em further from the middle for each place it stands away from it, the look of letter spacing closing in and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=text.motion:1:5`
- **Words pop** — `text.motion:recipe:1`
  - Moves each word: grows from 55% of its size and fades in, fully opaque by 50% of the motion. One after another, in reading order. 0.08 s between units.
  - Add: `inspector.add item=library kind=text.motion:recipe:1`
- **Letters rise** — `text.motion:recipe:2`
  - Moves each letter: comes in from below, 0.9 em away and fades in, fully opaque by 66.67% of the motion. One after another, in reading order. 0.04 s between units.
  - Add: `inspector.add item=library kind=text.motion:recipe:2`
- **Letters fade** — `text.motion:recipe:3`
  - Moves each letter: fades in, fully opaque by 100% of the motion. One after another, in reading order. 0.04 s between units.
  - Add: `inspector.add item=library kind=text.motion:recipe:3`
- **Typewriter** — `text.motion:recipe:4`
  - Moves each letter: fades in, fully opaque by 100% of the motion. One after another, in reading order. 0.04 s between units. With a blinking caret, typed in steps.
  - Add: `inspector.add item=library kind=text.motion:recipe:4`
- **Slide in from the left** — `text.motion:recipe:5`
  - Moves the whole text as one: comes in from the left, 0.9 em away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=text.motion:recipe:5`
- **Slide in from the right** — `text.motion:recipe:6`
  - Moves the whole text as one: comes in from the right, 0.9 em away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=text.motion:recipe:6`
- **Drop in** — `text.motion:recipe:7`
  - Moves the whole text as one: comes in from above, 0.9 em away and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=text.motion:recipe:7`
- **Zoom in** — `text.motion:recipe:8`
  - Moves the whole text as one: grows from 20% of its size and fades in, fully opaque by 50% of the motion.
  - Add: `inspector.add item=library kind=text.motion:recipe:8`
- **Spin in** — `text.motion:recipe:9`
  - Moves the whole text as one: grows from 40% of its size, turns 180 degrees and fades in, fully opaque by 50% of the motion.
  - Add: `inspector.add item=library kind=text.motion:recipe:9`
- **Centre out** — `text.motion:recipe:10`
  - Moves each word: grows from 55% of its size and fades in, fully opaque by 50% of the motion. One after another, from the middle outward. 0.08 s between units.
  - Add: `inspector.add item=library kind=text.motion:recipe:10`
- **Track in** — `text.motion:recipe:11`
  - Moves each letter: each unit starts further from the middle, the look of letter spacing closing in and fades in, fully opaque by 66.67% of the motion. One after another, in reading order.
  - Add: `inspector.add item=library kind=text.motion:recipe:11`
- **Letters rise from a blur** — `text.motion:recipe:13`
  - Moves each letter: comes in from below, 0.9 em away, is blurred by 0.14 em while it moves and fades in, fully opaque by 66.67% of the motion. One after another, in reading order. 0.04 s between units.
  - Add: `inspector.add item=library kind=text.motion:recipe:13`
- **Lean in from the left** — `text.motion:recipe:12`
  - Moves the whole text as one: comes in from the left, 0.9 em away, leans 25 degrees while it moves and fades in, fully opaque by 66.67% of the motion.
  - Add: `inspector.add item=library kind=text.motion:recipe:12`
- **Letters snap up from a blur** — `text.motion:recipe:14`
  - Moves each letter: comes in from below, 0.9 em away, is blurred by 0.14 em while it moves and fades in, fully opaque by 66.67% of the motion. One after another, in reading order. 0.04 s between units. Each takes 0.5 s. Paced: Move covers 81% of its way by 25% of the time (Linear), then settles (Brake); Blur covers 100% of its way by 45% of the time (Ease Out), then settles (Smooth); Fade covers 100% of its way by 40% of the time (Smooth), then settles (Smooth).
  - Add: `inspector.add item=library kind=text.motion:recipe:14`
- **Snap in leaning from the left** — `text.motion:recipe:15`
  - Moves the whole text as one: comes in from the left, 5 em away, leans 25 degrees while it moves, is blurred by 0.2 em while it moves and fades in, fully opaque by 66.67% of the motion. Each takes 0.5 s. Paced: Move covers 81% of its way by 25% of the time (Linear), then settles (Brake); Lean covers 100% of its way by 50% of the time (Ease Out), then settles (Smooth); Blur covers 100% of its way by 45% of the time (Ease Out), then settles (Smooth); Fade covers 100% of its way by 40% of the time (Smooth), then settles (Smooth).
  - Add: `inspector.add item=library kind=text.motion:recipe:15`
- **Words bounce in** — `text.motion:recipe:16`
  - Moves each word: grows from 5% of its size and fades in, fully opaque by 50% of the motion. One after another, in reading order. 0.08 s between units. Each takes 0.75 s. Paced: Size covers 100% of its way by 100% of the time (Spring Snappy), then settles (Smooth); Fade covers 100% of its way by 25% of the time (Smooth), then settles (Smooth).
  - Add: `inspector.add item=library kind=text.motion:recipe:16`
## Text out

- **Fade** — `text.motion:2:1`
  - It fades out, in place.
  - Add: `inspector.add item=library kind=text.motion:2:1`
- **Pop** — `text.motion:2:2`
  - It shrinks to 55% of its size and fades out.
  - Add: `inspector.add item=library kind=text.motion:2:2`
- **Slide** — `text.motion:2:3`
  - It goes off toward the left, 0.9 em away and fades out.
  - Add: `inspector.add item=library kind=text.motion:2:3`
- **Rise** — `text.motion:2:4`
  - It goes off toward below, 0.9 em away and fades out.
  - Add: `inspector.add item=library kind=text.motion:2:4`
- **Track** — `text.motion:2:5`
  - It each unit starts 0.35 em further from the middle for each place it stands away from it, the look of letter spacing closing in and fades out.
  - Add: `inspector.add item=library kind=text.motion:2:5`
- **Words pop out** — `text.motion:recipe:21`
  - Moves each word: shrinks to 55% of its size and fades out. One after another, in reading order. 0.08 s between units.
  - Add: `inspector.add item=library kind=text.motion:recipe:21`
- **Letters fade out** — `text.motion:recipe:22`
  - Moves each letter: fades out. One after another, in reading order. 0.04 s between units.
  - Add: `inspector.add item=library kind=text.motion:recipe:22`
- **Slide out to the left** — `text.motion:recipe:23`
  - Moves the whole text as one: goes off toward the left, 0.9 em away and fades out.
  - Add: `inspector.add item=library kind=text.motion:recipe:23`
- **Slide out to the right** — `text.motion:recipe:24`
  - Moves the whole text as one: goes off toward the right, 0.9 em away and fades out.
  - Add: `inspector.add item=library kind=text.motion:recipe:24`
- **Zoom out** — `text.motion:recipe:25`
  - Moves the whole text as one: shrinks to 20% of its size and fades out.
  - Add: `inspector.add item=library kind=text.motion:recipe:25`
- **Gather out to the left** — `text.motion:recipe:26`
  - Moves the whole text as one: goes off toward the left, 1.5 em away and fades out. Each takes 0.5 s. Paced: Move covers 100% of its way by 100% of the time (Gather), then settles (Smooth); Fade after waiting 30% of the time covers 100% of its way by 100% of the time (Smooth), then settles (Smooth).
  - Add: `inspector.add item=library kind=text.motion:recipe:26`
## Text loop

- **Wave** — `text.motion:3:11`
  - Round and round all the while it is there, it moves up and down by 0.18 em.
  - Add: `inspector.add item=library kind=text.motion:3:11`
- **Wiggle** — `text.motion:3:12`
  - Round and round all the while it is there, it turns 7 degrees either way.
  - Add: `inspector.add item=library kind=text.motion:3:12`
- **Pulse** — `text.motion:3:13`
  - Round and round all the while it is there, it swells and shrinks by 10% of its size.
  - Add: `inspector.add item=library kind=text.motion:3:13`
- **Sway** — `text.motion:3:14`
  - Round and round all the while it is there, it moves from side to side by 0.12 em.
  - Add: `inspector.add item=library kind=text.motion:3:14`
- **Flicker** — `text.motion:3:15`
  - Round and round all the while it is there, it lets its opacity fall by up to 85%.
  - Add: `inspector.add item=library kind=text.motion:3:15`
- **Jitter** — `text.motion:3:16`
  - Round and round all the while it is there, it moves up and down by 0.04 em, moves from side to side by 0.04 em and turns 1.2 degrees either way.
  - Add: `inspector.add item=library kind=text.motion:3:16`

