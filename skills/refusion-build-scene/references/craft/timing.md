# Timing: numbers by role

A number here is one of three kinds. Read the tag before you lean on it.

- **[measured]** read from reference videos by the owner's team (2026-10-31: three references, one an ad with fast text, two interface animations; 24 to 33 ms frames). It is evidence, not a law: three references, and some of the measured events mix an entering element with one passing through.
- **[engine]** what a preset or recipe of the engine does today, read from its tables (`engine/motion.md` says it for each one).
- **[start]** a starting point from practice, to be judged with your eyes on the result. Change it when the piece asks.

## The shape of a good beat: hit, settle, hold, release

A beat that looks designed has four parts with four different speeds. The default look runs one speed through all of them.

1. **Hit** (fast). The element crosses most of its way at once. [measured] A word's entrance in the fast ad reference covered about 80% of its way in 3 frames at 30 fps (0.1 s), with no ease-in: the first step was already 74% of the peak speed.
2. **Settle** (a long tail). The last 20% takes longer than the first 80%. [measured] Speed fell to about a quarter in one frame, then to 0.63 of itself every frame for 8 frames; the whole entrance took 12 frames (0.4 s). The lean and the blur were gone 3 frames after the peak: they resolve with the brake, not after the word has stopped.
3. **Hold** (still). This is where the viewer reads. It is the longest part of the beat and the part most often missing. [start] Give a text its reading time (below) before anything else competes with it.
4. **Release** (fast again, or a hard cut). [measured] Exits that lead into a cut accelerate for about 7 frames, then stop hard. [start] An exit takes 60% to 70% of the entrance's length, or the element simply ends with the scene.

The engine builds the hit and the settle for a text or a layer with a channel's pace: `motion.channel_set` gives one channel (move, size, turn, lean, blur, fade) its own wait, travel and settle on a curve. [engine] Recipes 14 and 15 of the text's entrance do it: the move cruises to 81% of its way by a quarter of the time, then takes the Brake curve for the rest; blur and lean resolve by about half of the time; the text is opaque by 40% (`text.motion:recipe:14`, `text.motion:recipe:15`). A recipe is a starting point: read its numbers with `motion.channels`, then tune them.

The hold is a hold: a still stretch between two keys is a segment with the hold ease (`anim.set_segment_ease`), and the end of a piece rests on a deliberate hold, never a cut in the middle of a move.

## Lengths by character

| Character | Entrance | Tag | Fits |
|---|---|---|---|
| Snap | 0.15 s to 0.25 s | [start] | A word or an interface element in a fast piece. The inspector's steps are 0.15, 0.25, 0.35, 0.5, 0.75 and 1 s; an exact length from 0.05 s to 5 s can be set. |
| Standard | 0.35 s to 0.5 s | [start] | Most content. |
| Calm | 0.6 s and more | [start] | A reveal that should feel unhurried; a background settling. |
| A fast ad's headline | about 0.4 s in all, 80% of it in the first 0.1 s | [measured] | `text.motion:recipe:14` and `text.motion:recipe:15` take 0.5 s; a layer's `layer.edge:recipe:7` and `layer.edge:recipe:8` take 0.6 s. |

Do not give every element the same duration. The slowest thing in a piece is several times slower than the fastest; a piece whose elements all take the same time reads as one machine repeated.

## What the references say about events and holds

[measured] Across the three references: a motion event in a place lasts a median 0.27 to 0.37 s; it rises to its peak in 0.07 to 0.10 s and decays in 0.10 to 0.20 s, about twice the rise; the stillness between two events in the same place has a median of 0.25 to 0.58 s (quarter to three quarters: 0.13 s to 1.9 s). That stillness is not a reading time; it is the pace of the cuts. Read them as the rhythm of fast work, not as holds for text.

## Reading time

[start] About a third of a second per word, plus a second, once the text has landed. A familiar two-word label needs less. A long line, small type, Arabic, or text that competes with other motion needs more. Count from the frame where the text is whole and still, not from the first frame of its entrance. Do not shorten a hold to fit more in; cut words.

## Many things at once

- **Stagger.** [start] Elements of a group arrive a few frames apart, in order of importance. A delay of 0.1 s to 0.2 s between words reads as one after another; under 0.05 s as all at once (`text.motion_set` with a `span` or a delay).
- **A whole sentence** [start] takes about a tenth of a second per word, from 0.8 s to 2.5 s (`recipes:sentence-reveal` was run). One text layer whose words are the unit, never a layer per word.
- **The whole stagger of a group** [start] stays under about half a second whatever the count: more is a slow queue, not a reveal.
- **Overlap.** The next element starts before the last has finished settling. Waiting for each to stop makes a list; overlapping makes a sequence.
- **The first move** does not start at the first frame of a piece. [start] Offset it by a tenth to three tenths of a second, so the viewer has a frame of the still before things move.

## Easing is the meaning

Ease out for what arrives (it starts fast and lands softly); ease in for what leaves (it gathers speed and is gone); ease in and out for what moves between two places. Linear only for a constant drift. [start] Use at least three different curve shapes in a piece and no more than two independent moves with the same shape in one beat. The shapes a segment can take are named in `guide.read` topic `animation` (ease in, ease out, ease in out, hold, a back shape that overshoots, a spring, a bounce, an elastic band); `anim.set_segment_bezier` takes any cubic.

A move that continues through a key must not stop at it: an ease in and out on every short segment makes a chain of stops. `motion.trace` shows it as a speed graph that returns to zero at each key.

## On the beat

With music, put the hit on the beat and let the settle and the hold fill the space to the next one. [start] Anticipate the beat by about a tenth of a second so that the landing is felt on it. The grid is said once for the scene (`beat.set`); a formula reads `beat`, and a length can be said in beats so that it follows the tempo (`guide.read` topics `rhythm` and `formulas`). Put layers on beats with `beat.grid` (it gives the times) and `layer.move`.

## What the engine does not do for you today

- A clip's playback speed (a speed ramp of footage, a freeze, a reverse) is not a tool of the engine today; do not promise it. A speed-and-pause feel is made with the pace of a motion, not with the speed of a clip.
- The [measured] numbers come from three references and none of them is a hold for reading text. Say what they are when you cite them; do not present them as how professionals always do it.
