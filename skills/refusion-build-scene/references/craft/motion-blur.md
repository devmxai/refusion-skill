# Motion blur: the subject the eye follows, and what it costs

A fast move drawn sharp shows as copies: a stutter. Blur turns the copies into a streak, as a camera's shutter does. It is a tool for one job, not a finish to spread over everything. Tags as in [timing.md](timing.md).

## When a move needs it

[engine] A layer that steps more than 2.5% of the canvas's shorter side between two frames (27 px on a 1080-wide canvas) and is drawn sharp is what `scene.motion` lists and what the note `jump` names in an edit's reply. That is the move that needs blur, a longer travel, or a start from rest. A slow drift does not need it, and a still layer costs nothing with it on.

[engine] Blur is switched per layer and per motion: a layer's `motion_blur` in the project's file, `true` or the list of the motions it blurs (position, scale, rotation, anchor or opacity), so a layer can turn blurred and slide sharp. The project's switch and its sample limit are the owner's, in the file's head.

## What it costs

[engine] A blurred layer is drawn once for each sample its motion asks at that frame: as many as keep its corners within about a pixel of each other along the path, up to the limit (128 by default). A wide layer moving fast takes the most samples over the largest area. The note `blur_cost` gives the samples at the layer's fastest frame and the share of the canvas it covers.

- **Blur the subject the eye follows**: the word that hits, the object that crosses. Not the background, not every bar of a group moving together.
- **A wide, fast element** (a bar the width of the frame crossing it in a few frames) is the most expensive thing to blur. Give it a longer travel, or let it cut on the beat.
- **Measure, do not guess.** `render.cost` draws a window and says what each frame cost, stage by stage; `render.strip` shows whether the blur reads as a streak or as copies.

## The limit and the scenes

[engine] The motion blur is the project's, in every scene it holds: its switch and its limit reach every scene, one made later too, and changing them changes every scene at once (a scene keeps no setting of its own). So a lower limit on the project makes every scene's blurred layers cheaper; still, blur the subject the eye follows rather than every moving layer.
