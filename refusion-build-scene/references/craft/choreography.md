# Choreography: how the parts move together

Timing says how long one thing takes. Choreography says how several things share the screen and the beat. Most of the "amateur" feel of a generated piece is here: everything arrives together, from the same side, with the same curve, and nothing is tied to anything else.

## Order is hierarchy

- The element that moves first is read as the most important. Order arrivals by importance: the focal element, then what supports it, then the accent. The order of your batch is not the order of the story.
- Overlap the arrivals: the next starts while the last is still settling ([timing.md](timing.md): the whole stagger of a group stays under about half a second).
- Give each role its own verb and its own curve family. If the headline snaps and the supporting line also snaps in the same way, the headline stops being the headline.
- One direction of entry per kind of element in a scene (all labels from the left, all numbers from below). Mixing a slide from the left and a drop from above for the same kind of element reads as noise. Vary the direction between kinds, and between scenes, so scene two does not repeat scene one.

## One grid for everything that has a beat

When there is music, say the rhythm once (`beat.set` for the scene) and let everything read it. A formula on a scale, a length said in beats, a layer placed on a beat with the times `beat.grid` gives, a marker (`marker.add`) for a moment that is not on the grid: all of these follow the tempo when it changes; hand-typed times do not. See `guide.read` topics `rhythm` and `formulas`, and `recipes:pulse-on-beat`, `recipes:enter-on-beats`, `recipes:appear-from-marker`.

- Put the hit on a beat or a half beat. Put the hold across the space to the next one. Put the cut on a downbeat.
- Do not hit on every beat. A pulse on each beat is a metronome; hit on the beats that carry meaning and let the others pass.
- Vary the rhythm between scenes (the stagger, the entry axis, the ambient motion), so the piece has sections.

## Shapes, text and transitions as one movement

- **A shape that frames or supports a text moves with the text, not after it.** It arrives with or just before the text (a frame or two), uses the same family of curve, and shares its direction. A background card that lands after the words it holds looks like a mistake. Make the pair one unit (a scene) so they come in and go out as one.
- **A shape that is a decoration must be able to say what it is for**: its start, its end (a real element, not empty space) and its job (reveal, route, emphasise, separate). A line the frame can lose without losing meaning is cut. `recipes:draw-on` draws a line on along its stroke.
- **A transition continues the motion that leaves.** If the outgoing title slides out to the left (`layer.edge:recipe:21`), a transition that moves left (`transition:10`, `transition:20`, `transition:40`) carries the same direction and speed into the next scene; a dissolve (`transition:1`) breaks it. Match the direction, the speed and the moment: the cut on a beat.
- **Choose the transition by what it means, not by what is there.** A dissolve says "this continues"; a push or a slide says "the same surface moves"; a whip says energy; a dip to black or white says "a breath, then a new part"; a hard cut says "wake up" and is the right choice on a beat in a fast piece. A piece of five or six scenes wants one or two noticeable transitions, at the hero moment and at the end; all of them noticeable flattens each.
- **A transition's length belongs to the pace of the piece**: in a fast piece, a motion transition of 0.3 s to 0.5 s [start]; a calm piece can take a second. Cost: the engine says `unmeasured` until a phone has measured it, so look at the result on the device before promising it plays smoothly.

## Depth and ambient motion

- Three layers at least in a scene: a ground (a fill with life, not flat black), the content, and a small accent. A ground that does not move at all feels empty during the staggered entrance; a living fill is a fill with colour points or an evolving field (`recipes:colour-points`, `recipes:evolving-field`).
- **One ambient motion per scene**, shared by what is ambient (a slow drift, a breath, a loop): `layer.edge:3:11` to `layer.edge:3:16` for a layer, `text.motion:3:11` to `text.motion:3:16` for the words of a text. Stillness after motion is strong; not every scene needs a slow zoom.

## Text on a beat, and on speech

- A sentence is one text layer whose words are the unit; its reveal is a span or a delay, the same for every sentence in a scene.
- Captions follow speech: their timing belongs to the speech, not to the layout. Match a spoken line with a caption layer (`caption.create`), do not stretch a caption to fill space.

## Repeating pieces

A piece used again (a lower third for each speaker, a banner twice) is a scene shown several times, not copied layers. When one use must differ, `composition.duplicate` the scene first and edit the copy.
