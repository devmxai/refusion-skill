# The defaults to catch in yourself

These are the things an agent does when nobody is steering it. Each one is not wrong alone; the trouble is doing it everywhere. Before you build, read the list against your plan; before you report, read it against the result.

| The default | Why the result reads as machine-made | Do this instead |
|---|---|---|
| One curve on every move (ease out, everywhere) | Nothing has a character; weight and mood are the same for a headline and a footnote. | Vary the shape by role, at least three in a piece ([timing.md](timing.md)). Segments: `anim.set_segment_ease`, `anim.set_segment_bezier`; a motion's own pace: `motion.channel_set`. |
| One duration on every element | The piece has one speed, so it has no accent. | Durations by role; the slowest several times the fastest. |
| Everything arrives together, or all from the same side | There is no order, so no hierarchy. | Arrivals by importance, overlapped; a direction per kind of element ([choreography.md](choreography.md)). |
| Entrance only: no planned hold, no planned leave | The viewer has no time to read, and the end is a cut mid-move. | Plan hit, settle, hold, release for every element, and a deliberate rest on the last frame. |
| The first preset, untouched | The preset is a starting point; its numbers are not your design. | Read its numbers (`motion.channels`, `scene.snapshot`), then change them with `property.set` or `motion.channel_set`; combine an entrance with a different loop. |
| Every element animated | Nothing is still, so nothing is emphasised. | Static text on a moving ground is often enough. Animate the focal element and one more. |
| A layer for every word, or a flat build of twenty rows | The owner cannot edit it; a unit cannot be reused. | A sentence is one text layer (`text.motion_set`); units are scenes (`guide.read` topic `units`); `layer.precompose` when `scene.layout` says `crowded_main_timeline`. |
| Keys where a formula would follow | The motion breaks when the tempo, the text or the length changes. | A formula for what follows the beat, another layer or a text's size (`guide.read` topic `formulas`); keys for a move no formula says. |
| Everything centred and equal | The eye is led nowhere. | Lead the eye: anchor to edges, split the frame into zones, make hero text fill 60% to 80% of the width of the frame [start]. A video frame is not a web page. |
| Text on a busy picture | It cannot be read and the fix (smaller text) makes it worse. | A calm or darkened shape under the text; contrast first. |
| Accent colour everywhere | The accent stops being one. | One accent hue; two visible uses on a screen at most [start]. Tint blacks and whites toward the accent rather than pure `#000` and `#fff`. |
| Every transition a dissolve | A dissolve says "continues"; used for every cut it says nothing. | Choose by meaning ([choreography.md](choreography.md)). |
| Glow, blur or a look to hide a flaw | The flaw is still there, soft. | Fix the cause first: type and layout before glow, path and timing before blur, the match between two states before a flash. |
| A line or a shape with no job | Decoration reads as clutter. | Name its anchors and its job; cut it if it has none. |
| Trusting a number without looking | The numbers in a reply are not the picture. | `render.look`, `render.strip`, `motion.trace` ([checks.md](checks.md)). |
| Naming an effect, an id or a duration from memory | The engine changes; your memory does not. | Read [engine/INDEX.md](../engine/INDEX.md), then `library.catalog` and `effect.catalog` for the build that answers. |
| The same stagger, direction and ambient motion in every scene | The scenes blur into one. | Give each scene its own rhythm; one section may be still. |
| Saying it is done because the call succeeded | A clean check is not a verdict on taste, and a tool's success is not a picture. | Look, then say what you looked at and what you could not look at. |
