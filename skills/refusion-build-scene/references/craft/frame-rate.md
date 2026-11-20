# Frame rate: the owner's, unless the owner says otherwise

The frame rate decides how far a move steps between two pictures. Halve it and every move steps twice as far. Tags as in [timing.md](timing.md).

## Keep the project's rate

- **Do not lower the rate to match a reference.** A reference shot at 30 frames tells you its timing in seconds, not the rate your project must have. Read its timing (`media.strip` gives each frame with its time) and build it at the project's rate.
- [engine] An agent's build lowered a 60-frame project to 30 to match a reference; by the project's own keys, nine full-width bars that crossed the frame in a fifth of a second then stepped 275 to 320 px between two frames. The owner saw them stutter.
- **When the owner asks for another rate**, it is the file head's `fps`, which is theirs: tell them what it does to the fast moves, and let them change it.

[engine] The reply of an edit that lowers the rate carries the note `frame_rate_lowered`, with the rates before and after and the largest sharp step after it, and the moves that now step too far are named as `jump`.

## Fast moves at any rate

[engine] The limit of a sharp step is 2.5% of the canvas's shorter side: 27 px on a 1080-wide canvas, which is 1,620 px a second at 60 frames and 810 px a second at 30. A move faster than that needs one of:

1. **Motion blur** on the layer that moves ([motion-blur.md](motion-blur.md)).
2. **A longer travel**, so each step is shorter.
3. **A start from rest**: an ease that leaves slowly spreads the distance over more frames (see [easing.md](easing.md)).

[start] A move that is meant to read as a snap (a word that hits) can step far for one or two frames if it is blurred and settles at once; a move the eye follows across the frame should not.
