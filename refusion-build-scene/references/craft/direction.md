# Direction: from a request to a plan

Most weak work is decided before the first tool call: the agent starts building and the design is whatever the first presets give. Spend the first minutes on a plan, write it down (a few lines for a small piece, a table for a piece with several beats), and build from the plan.

## 1. Read the brief for what it fixes

| Fixed by the brief | Ask yourself | Where the answer comes from |
|---|---|---|
| The piece | An ad, a title card, a lower third, captions, an explainer, a loop for a feed? | The request; if it names none, the length and the platform |
| The canvas | 9:16, 16:9, 1:1? A tall and a wide canvas are different layouts, not one scaled. | `scene.brief` (read it; change the canvas only if asked) |
| The length | How many seconds, and how many beats of story fit in it? | The request; the music if there is one |
| The language | Arabic, English, both? Right-to-left words inside left-to-right text? | The request; read [arabic-and-text.md](arabic-and-text.md) |
| The energy | Calm, steady, fast? It sets every number in [timing.md](timing.md). | The request's words and the platform (a feed ad is fast; a product tour is calm) |
| The material | What did the designer bring? Pictures, clips, sounds, drawings. | `media.library_snapshot` before you plan: the designer's own material comes first |
| The rhythm | Is there music or a beat? | The project's beat grid (`beat.grid`); if none and the piece is musical, ask for the tempo |

If something is missing, choose a sensible default, say it, and ask at most one question, only when the answer changes the whole piece.

## 2. One idea, one focal element

- Say in one sentence what the viewer should take in. Everything on screen serves that sentence; what does not is cut.
- One thing is largest and arrives first. Give the rest at most two other levels of size. The element that moves first is read as the most important, so order arrivals by importance, not by the order you made the layers.
- Two focal points at most per beat, so the eye has somewhere to travel; never one text floating alone in empty space, never five things shouting.
- One accent colour against a calm ground. Text sits on a plain or darkened area, never on a busy picture: if the picture is busy, put a calm shape under the text instead of shrinking the text.

## 3. Choose a direction, then its means

Pick one of the directions in [styles.md](styles.md) (or name your own in two lines) so that type, colour, motion character and transitions agree. Then choose the engine's means from [choosing.md](choosing.md) and the index in [engine/INDEX.md](../engine/INDEX.md): the preset, recipe, look, effect or transition that already does the job, before writing keys by hand.

## 4. Write the plan

For a piece with more than one beat, one row per element:

| Beat (time) | Element | Role | Verb | Arrives | Holds | Leaves | Means |
|---|---|---|---|---|---|---|---|
| 0.0 s–1.2 s | Headline | focal | snaps up | on beat 1, 0.3 s | until beat 3 | accelerates out, 0.2 s | `text.motion:recipe:14`, then tune its numbers |

- **Role:** focal, support, accent, ground. A beat with no focal element is not designed yet.
- **Verb:** name how it moves in one word (snaps, drops, draws, grows, drifts, types, locks in). If you cannot name the verb, the element is not designed yet. Different roles get different verbs; one verb for everything is the default look.
- **Arrives, holds, leaves:** three separate numbers from [timing.md](timing.md). The hold is where the viewer reads; it is not the leftover.
- **Means:** the exact preset, recipe or tool, so the build is a transcription of the plan.

Check the plan before building: Is anything arriving at the same instant as something else for no reason? Does every element have a different job? Does the last frame rest on purpose?

## 5. Units, then batches

Split the plan into design units (a title and its line, a banner, an icon, a lower third): each is one scene built in one batch and placed as one layer (`guide.read` topics `units` and `recipes`). The background that lasts and a global adjustment layer stay on the main timeline. One batch for one idea, `session.validate` first, then `session.batch`; the owner can take it back in one step.

## 6. Design the still before the motion

Build the resting frame first and look at it (`render.look`): type, size, colour, margins, contrast. Fix the still before any motion exists. Motion cannot rescue a poor layout; it only makes it poor for longer.
