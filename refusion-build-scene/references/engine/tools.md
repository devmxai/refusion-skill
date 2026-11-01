# Tools an agent is offered

Written by `rpro skill-reference --write` from catalog version 2, fingerprint `18c5e4330715a936`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

175 tools in 29 families. A tool's arguments, its reasons for refusal and an example are its own page: `guide.read` with `tool:<name>`.

## Families

`anim` (14) · `asset` (4) · `audio` (2) · `beat` (3) · `camera` (1) · `caption` (16) · `composition` (5) · `effect` (8) · `export` (5) · `font` (4) · `guide` (1) · `history` (3) · `inspector` (4) · `layer` (31) · `library` (2) · `marker` (4) · `mask` (7) · `media` (7) · `motion` (3) · `path` (5) · `project` (3) · `property` (9) · `render` (5) · `scene` (5) · `session` (4) · `text` (11) · `transition` (6) · `transport` (1) · `vector` (2)

Notes: **asks** means the owner is asked on the device for each call of a remote agent; **not in a scene** means the engine refuses the tool on a layer inside a scene.

## anim

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `anim.set_value_at_time` | edit | layer | Set a property's value at a time (absent: the playhead). |  |
| `anim.insert_keyframe` | edit | layer | Insert a keyframe on a property track, at a time (the edit head when absent) with a value (the property's value there when absent); on a property that is not… |  |
| `anim.delete_keyframe` | edit | layer | Delete a property's keyframe, named by its composition time (the edit head when absent); the property's other keys stay. |  |
| `anim.move_keyframe` | edit | layer | Move a property's keyframe from the composition time `from` to the composition time `to`. |  |
| `anim.set_spatial_tangents` | edit | layer | Set the spatial tangents of one segment of a position's path: the outgoing tangent of the segment's first keyframe (`out_tangent`) and the incoming tangent of… |  |
| `anim.shift_time` | edit | layer | Shift every keyframe of a property's track by `delta`, a time that may be negative, so the whole motion happens earlier or later; the keys keep their values. |  |
| `anim.scale_time` | edit | layer | Scale the times of a property's keyframes about `anchor`, a composition time, by `factor`, a positive fraction: 2 makes the motion twice as long about that… |  |
| `anim.toggle_keyframing` | edit | layer | Turn keyframing on or off for a property. |  |
| `anim.set_key_interpolation` | edit | - | Set the interpolation of one or both sides of keyframe `key`, else of the selected keyframes. |  |
| `anim.set_key_tangent_mode` | edit | - | Set how the two sides of keyframe `key`, else of the selected keyframes, relate in time: apart, continuous (the two sides on one line, so the speed has no… |  |
| `anim.set_key_ease` | edit | - | Set the speed and influence of one or both sides of keyframe `key`, else of the selected keyframes, as the curve editor's handles do: the speed the value has… |  |
| `anim.set_segment_ease` | edit | - | Give the motion between keyframes a named shape (linear, ease in: starts slowly, ease out: ends slowly, ease in out, hold, back in and out, or a spring, a… |  |
| `anim.set_segment_bezier` | edit | - | Give the motion between keyframes a cubic Bézier (x1, y1, x2, y2), the form of CSS cubic-bezier(): the curve leaves the first keyframe towards (x1, y1) and… |  |
| `anim.set_key_spatial_mode` | edit | - | Set how the motion path of a position passes through keyframe `key`, else the selected keyframes: linear (straight), bezier (free handles), continuous (handles… |  |

## asset

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `asset.catalog` | read | - | Read the built-in asset pack, which comes with the engine and needs no network and no file: icons (arrows, interface, social, media, symbols, mouse and hand… |  |
| `asset.insert` | edit | scene | Put an asset of the built-in pack into the project, in one history step with the revision checked. |  |
| `asset.fetch` | edit | - | Start fetching a file from the internet for the project: a picture, a drawing (SVG), a sound or a short video, from an https address of the public internet. |  |
| `asset.fetch_status` | read | - | Read a fetch `asset.fetch` started, waiting up to `wait_ms` for it to end or to change: downloading (with the bytes so far), failed (with why), ready (the file… |  |

## audio

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `audio.formats` | read | - | Read the sound formats the engine reads and the ones it refuses by name. |  |
| `audio.snapshot` | read | - | Read how the sound of the project's layers stands: for each layer that plays a source with sound (an audio layer, or a video whose file has sound) its name… |  |

## beat

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `beat.grid` | read | inside a scene | Read the beat grid of the scene the `target` names (absent: the project's own, or the scene the owner has open): `present` is 1 when it has one, then `bpm`… |  |
| `beat.set` | edit | inside a scene | Give a scene a beat grid (the `target` scene; absent: the project's own, or the scene the owner has open), or change the numbers of the one it has, in one… |  |
| `beat.clear` | edit | inside a scene | Take a scene's beat grid away (the `target` scene; absent: the project's own, or the scene the owner has open), in one history step with the revision checked. |  |

## camera

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `camera.frame_layer` | edit | layer | Put a camera (the target, else the one that is active at the edit head) where a layer fills its frame, less a margin, as Framing does in Apple Motion. | not in a scene |

## caption

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `caption.create` | edit | - | Insert an empty caption layer on a new top track and select it. | not in a scene |
| `caption.import` | edit | - | Insert a caption layer (see caption.create) with the cues of a subtitle file's text: SubRip (SRT), WebVTT or typed JSON. | not in a scene |
| `caption.edit` | edit | layer | Change the cues of a caption layer (the target, else the selected layer) in one history step with the revision checked: insert a cue, delete one, replace a… | not in a scene |
| `caption.bind_source` | edit | layer | Bind a caption layer (the target, else the selected layer) whose document keeps composition time (one made by caption.create without a source, or by… | not in a scene |
| `caption.add` | edit | layer | Add a sentence to a caption layer (the target, else the selected layer) at the playhead: empty, on from the playhead to where the next sentence begins, at most… | not in a scene |
| `caption.duplicate` | edit | layer | Copy the chosen sentence (`caption.select`; the sentence of the words when words are chosen) to the playhead of a caption layer (the target, else the selected… | not in a scene |
| `caption.delete` | edit | layer | Delete what is chosen (`caption.select`) in a caption layer (the target, else the selected layer): the sentences (the time they were on is left empty… | not in a scene |
| `caption.split` | edit | layer | Split the sentence of a caption layer (the target, else the selected layer) that is on at the playhead between the two words around the playhead: a sentence… | not in a scene |
| `caption.merge` | edit | layer | Join the chosen sentence of a caption layer (the target, else the selected layer) with the one after it, or all the chosen sentences into the first of them… | not in a scene |
| `caption.snapshot` | read | layer | Read a caption layer (the target, else the selected layer): its language, its source, its cues (id, window, speaker, text) and the words of all cues (the cue… | not in a scene |
| `caption.style_catalog` | read | layer | Read the looks a caption layer (the target, else the selected layer) can be given, in the order they are offered: each look's id (`styles`) and name (`names`)… | not in a scene |
| `caption.trim` | edit | layer | Trim the chosen sentence or word of a caption layer (the target, else the selected layer) at the playhead: `edge` 1 moves its start there, 2 moves its end… | not in a scene |
| `caption.roles` | read | layer | Read the colours of a caption layer's words by what is being said (the target, else the selected layer) that a person can set: for each row `i`, the role… | not in a scene |
| `caption.role_set` | edit | layer | Give aspect `aspect` of role `role` of a caption layer (the target, else the selected layer) the colour `color`: a colour of the letters of the words in that… | not in a scene |
| `caption.role_clear` | edit | layer | Take aspect `aspect` of role `role` of a caption layer (the target, else the selected layer) away: the role sets no such colour any more, so the words in that… | not in a scene |
| `caption.style_apply` | edit | layer | Give a caption layer (the target, else the selected layer) the look `style`: its family for Latin letters and its family for Arabic letters, its weight, its… | not in a scene |

## composition

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `composition.create` | edit | - | Make a scene: a composition of the project's own, empty, with its own canvas, rows and layers, for layers of other compositions to show… |  |
| `composition.rename` | edit | scene | Give the scene the target names another name. |  |
| `composition.delete` | edit | scene | Take the scene the target names out of the project, with its layers and their animation. |  |
| `composition.duplicate` | edit | scene | Make a copy of the scene the target names, called `name`: its canvas, length, rows and layers with their effects, masks, mattes, parents, transitions and… |  |
| `composition.snapshot` | read | scene | Read one composition of the project as `scene.snapshot` reads the project's root: its canvas, rows, layers (kind, span, row, z_order) with each layer's… |  |

## effect

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `effect.catalog` | read | - | Read the effect kinds the engine offers: each one's name, label, category, the version of its algorithm, how many pictures it reads, the space it computes in… |  |
| `effect.add` | edit | layer | Add an effect of a catalog kind to a layer's chain (the target, else the selected layer), at a position or at the end. |  |
| `effect.remove` | edit | layer | Remove an effect from a layer's chain, with its settings and keys. |  |
| `effect.move` | edit | layer | Move an effect to another place in the layer's chain; the chain applies its effects in order. |  |
| `effect.set_enabled` | edit | layer | Turn an effect on or off; an off effect stays in the chain with its settings and is not applied. |  |
| `effect.duplicate` | edit | layer | Copy an effect, with its settings and keys, to the place after it in the chain; the copy has an id of its own. |  |
| `effect.look` | edit | layer | Add a look, a ready-made chain of effects with its values, to the end of a layer's chain (the target, else the selected layer), as one history step. |  |
| `effect.set_region` | edit | layer | Limit an effect to a place of its layer: it shows inside what the masks named cover together (each by its own mode; a mask in the Region mode cuts nothing of… |  |

## export

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `export.start` | call | - | Start exporting the open project to MP4 (H.264 or HEVC as `codec` says, at the size and frame rate chosen from what `export.presets` offers, and the video bit… | asks |
| `export.cancel` | call | - | Ask the running export to stop. |  |
| `export.status` | read | - | Where an export is: preparing, running (frames done of total), publishing, done (the file's size and frames, whether it replaced a file, whether it appeared in… |  |
| `export.presets` | read | - | What the open project can be exported as, and what one choice comes to. |  |
| `export.open_destination` | call | - | Get a destination handle for a file name inside the open project's exports folder, for `export.start`. |  |

## font

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `font.catalog` | read | - | Read the families a text layer can be given that answer `query`, best first, as parallel lists: the family name, where it comes from (0 a generic family the… |  |
| `font.import_asset` | edit | - | Import a font file into the project through a native access handle: the project keeps a copy under the file's fingerprint and carries it with the project, so a… |  |
| `font.assets` | read | - | Read the project's font assets: each one's id, what it is (name, families, faces, size) and whether its file is usable: gone from the project's folder, or… |  |
| `font.resolve` | read | - | Say where a family name comes from, as a text layer asking for it would find it: a generic family (the device chooses), a project font asset, the engine's own… |  |

## guide

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `guide.read` | call | - | Read the engine's guide for an agent: how to work on a project (read, check, apply, look, mend), how time, layers, animation and text are written, what the… |  |

## history

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `history.undo` | call | - | Undo the last recorded step: the project returns to the state before it, with its revision raised. |  |
| `history.redo` | call | - | Redo the step the last undo took back, if no edit has been made since. |  |
| `history.state` | read | - | Read the undo chain: whether a step can be taken back or made again, which tool made each step (its number), and how many steps it holds and how many were let… |  |

## inspector

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `inspector.read` | read | layer | Read a layer's inspector (the target, else the selected layer): the items it uses now, in the order they are shown, a section's rows together (`section_codes`… |  |
| `inspector.catalog` | read | layer | Read what the track's plus can add to a layer (the target, else the selected layer), narrowed by `query` (empty: all): the Appearance items the layer does not… |  |
| `inspector.add` | call | layer | Add an item of `inspector.catalog` to a layer (the target, else the selected layer), in one history step, with a value that shows: a gradient makes the fill a… |  |
| `inspector.remove` | call | layer | Take an item of `inspector.read` away from a layer (the target, else the selected layer), in one history step: an effect or a mask (named by `instance`) is… |  |

## layer

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `layer.trim_in` | edit | layer | Move a layer's in-point to a composition time, inward (the layer starts later and is shorter) or outward (earlier and longer). |  |
| `layer.trim_out` | edit | layer | Move a layer's out-point to a composition time: earlier makes the layer shorter, later longer. |  |
| `layer.duplicate` | edit | layer | Copy a layer with its animation by the project mode's rule. |  |
| `layer.split` | edit | layer | Split a layer at a composition time into two layers. |  |
| `layer.delete` | edit | layer | Remove a layer and its animation, leaving a gap. |  |
| `layer.insert_text` | edit | inside a scene | Insert a text layer on a new top track and select it. |  |
| `layer.insert_background` | edit | inside a scene | Insert a background (a colour or a gradient over the canvas) on a new top track and select it. |  |
| `layer.set_anchor_preset` | edit | layer | Set a layer's anchor to one of nine places of its box, `preset` 0 to 8 row by row from the top left (4 is the middle). |  |
| `layer.insert_source` | edit | - | Insert a source already in the media library (`target` is its source id, from `media.library_snapshot`) as a layer at `start` (absent: the edit head). |  |
| `layer.move` | edit | layer | Move a layer to a composition time and, optionally, another track or a new row at a place in the stack (its row is its place in the picture: a layer on a row… |  |
| `layer.insert_vector` | edit | - | Insert the drawing of an SVG file as a vector layer: its parts keep their paths, fills and strokes, centred on the canvas (shrunk to fit when larger) on a new… |  |
| `layer.insert_adjustment` | edit | inside a scene | Insert an adjustment layer on a new top track and select it: it has no picture of its own, its effects act on everything drawn under it over the whole canvas… |  |
| `layer.set_matte` | edit | layer | Make another layer's picture the track matte of a layer (the target, else the selected layer): the matte layer is drawn as it stands, with its own transform… |  |
| `layer.clear_matte` | edit | layer | Take a layer's track matte away (the target, else the selected layer); refused when it has none. |  |
| `layer.set_motion_blur` | edit | layer | Turn motion blur on or off for one of a layer's motions (the target, else the selected layer): its position, scale, rotation, anchor or opacity, each apart… |  |
| `layer.insert_null` | edit | inside a scene | Insert a null layer on a new top track and select it: a transform that is never drawn (a 100 pixel box shows where it is on the canvas), for other layers to be… |  |
| `layer.set_parent` | edit | layer | Make another layer the parent of a layer (the target, else the selected layer), or free it. |  |
| `layer.insert_camera` | edit | inside a scene | Insert a camera on a new top track and select it: the view the composition is seen through, a frame the size of the canvas with a transform of its own (it is… |  |
| `layer.motion` | read | layer | Read how the layer (the target, else the selected layer) comes in and goes out, and what it can: the presets (`presets`, with their names), the functions, and… |  |
| `layer.motion_set` | edit | layer | Give the layer (the target, else the selected layer) a way of coming in (`phase` 1), going out (`phase` 2) or going round and round all the while it is there… |  |
| `layer.reseed` | edit | layer | Give the formulas of a layer (the target, else the selected layer) the noise of the layer's own number, in one history step with the revision checked. |  |
| `layer.motion_clear` | edit | layer | Take the way the layer (the target, else the selected layer) comes in (`phase` 1), goes out (`phase` 2) or goes round (`phase` 3) away, in one history step… |  |
| `layer.insert_composition` | edit | inside a scene | Put a layer that shows the scene `composition` into the composition the target names (the project's own when absent), on a new top track, from `start` for… |  |
| `layer.ungroup` | edit | layer | Put the layers of the scene the target layer shows back among the layers of its own composition, and take the layer that showed the scene away: the picture… |  |
| `layer.precompose` | edit | inside a scene | Make a scene of chosen layers and show it in their place: with neither `from` nor `to`, the layers chosen (the selected layer alone when no other is chosen… |  |
| `layer.add_fill_stop` | edit | layer | Add a stop to the gradient of a background, a shape, a text or a caption layer, or to the colour ramp of an evolving field (up to eight), after another (named… |  |
| `layer.add_fill_point` | edit | layer | Add a colour point to the points fill of a background or a shape layer after another (named by its id): the new point goes between that one and the next… |  |
| `layer.remove_fill_point` | edit | layer | Remove a colour point of the points fill of a background or a shape layer, named by its id; it keeps at least one. |  |
| `layer.remove_fill_stop` | edit | layer | Remove a stop of the gradient of a background, a shape, a text or a caption layer, or of the colour ramp of an evolving field, named by its id; it keeps at… |  |
| `layer.insert_shape` | edit | inside a scene | Insert a shape (rectangle, ellipse, polygon, star or line) at the canvas centre on a new top track and select it. |  |
| `layer.insert_path` | edit | inside a scene | Insert a path layer on a new top track at a canvas point, with its first node there, and select it. |  |

## library

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `library.catalog` | read | - | Read what the engine offers to add, as one list whatever the kind: the effects, the looks (ready-made chains of effects), the transitions, and the ready-made… |  |
| `library.look` | read | - | Look at what the library's cards show: the engine draws a page of its effects (`kind` 1) or its transitions (`kind` 2) on one sheet, a JPEG for you to look at… |  |

## marker

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `marker.list` | read | inside a scene | Read the markers of the composition the `target` names (absent: the project's own, or the open scene): for each its id, name, colour (a number of… |  |
| `marker.add` | edit | layer or scene | Add a marker, in one history step with the revision checked: a time, a length (0 for a point), a name and a colour. |  |
| `marker.edit` | edit | inside a scene | Change a marker, by its id, in the composition the `target` names (absent: the project's own) and in one history step with the revision checked: where it… |  |
| `marker.remove` | edit | inside a scene | Take a marker away, by its id, from the composition the `target` names (absent: the project's own), in one history step with the revision checked; an undo… |  |

## mask

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `mask.add` | edit | layer | Add a mask to a layer (the target, else the selected layer): a rectangle or an ellipse in the layer's own space, centred on its content at half its size, with… |  |
| `mask.remove` | edit | layer | Remove a mask from a layer, with its properties and keys. |  |
| `mask.move` | edit | layer | Move a mask to another place in the layer's masks; they combine in order. |  |
| `mask.set_shape` | edit | layer | Give a mask another shape (a rectangle or an ellipse), keeping its position, size and the rest. |  |
| `mask.set_mode` | edit | layer | Change how a mask combines with the masks before it: add (union), subtract, intersect or difference; or make it a Region, which cuts nothing of the layer and… |  |
| `mask.set_inverted` | edit | layer | Invert a mask so that what shows is outside its shape (`inverted` true), or put it back so that what shows is inside it (false). |  |
| `mask.set_enabled` | edit | layer | Turn a mask on (`enabled` true) or off (false); an off mask stays on the layer with its properties and keys and is not applied. |  |

## media

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `media.library_snapshot` | read | - | Read the project's media library: every source the project holds, whatever it is: its id, its kind (1 video, 2 picture, 3 sound, 4 drawing), what the pool… |  |
| `media.import_source` | edit | - | Register a source in the media library through a native access handle; the handle is its id. |  |
| `media.remove_source` | edit | - | Remove a source from the media library; refused while a layer uses it. |  |
| `media.set_info` | edit | - | Name a source of the media library and give it tags and a note: what the pool shows and what an agent finds it by. |  |
| `media.strip` | call | - | Draw frames of a video of the media library, the way `render.strip` draws the project: from `time` (in the source's own time; the frame of the source's grid… |  |
| `media.open_file` | call | - | Open a file inside the open project's folder (or the owner's extra folder) and get the source handle `media.import_source` takes. | asks |
| `media.look` | read | - | Look at the designer's material: the engine draws the pictures of the pool's sources on one sheet, a JPEG for you to look at, four tiles to a row and up to 12… |  |

## motion

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `motion.trace` | call | - | Read the motion of one layer frame by frame as numbers and as a picture, so an ease is read as a curve and not guessed from a few pictures. |  |
| `motion.channels` | read | layer | Read the shapes the channels of a way of coming in or going out have, so a client sees what `motion.channel_set` has made before it changes it: the layer (the… |  |
| `motion.channel_set` | edit | layer | Give one channel of a way of coming in or going out a shape of its own, or take the shape away, in one history step with the revision checked. |  |

## path

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `path.insert_node` | edit | layer | Insert a node, with its handles, into a path layer (the target, else the selected layer). |  |
| `path.move_node` | edit | layer | Move node `index` (from zero) of a path layer to `point`, in the layer's own space; its handles keep their offsets from it. |  |
| `path.set_node_handles` | edit | layer | Give a node of a path layer its two handles, as offsets from the node: equal and opposite for a smooth node, apart for a corner, zero for no curve on that side. |  |
| `path.delete_node` | edit | layer | Delete node `index` (from zero) of a path layer; the path closes up around the gap, the nodes beside it joined. |  |
| `path.set_closed` | edit | layer | Close a path layer back to its first node, or open it. |  |

## project

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `project.set_settings` | edit | - | Change the project's canvas size (`width` and `height` in pixels) and frame rate (`fps`, an exact fraction such as 30000/1001); refused while the project plays. |  |
| `project.fit_to_source` | edit | - | Make the project's canvas size and frame rate those of a source in its media library, as the engine reads them: the size the source is shown at (a source… |  |
| `project.set_motion_blur` | edit | - | Set the project's motion blur: its switch (off, every layer is drawn at the frame's instant whatever its own switches, and each keeps them for when it is on… |  |

## property

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `property.schema` | read | - | Read the properties each kind of layer declares: path, value kind, default, range, step, unit and whether it can be animated. |  |
| `property.set` | edit | layer | Set a property's value, of any kind: a static property takes it; an animated one takes it as the key at `time`; a text property (the content, the font family)… |  |
| `property.set_shown` | edit | layer | Set a number of a layer (a component of a pair as `path.0` or `path.1`) to a value as it is shown, the space the inspector, the sliders and their rulers use: a… |  |
| `property.set_text` | edit | layer | Set a text property of a layer (the content of a text layer, its font family) to a text. |  |
| `property.expression` | read | layer | Read the formula that drives a property of a layer (the target, else the selected layer; `path` is the property as `property.schema` lists it), and the… |  |
| `property.expression_set` | edit | layer | Bind a formula to a property of a layer, in one history step with the revision checked: from then on the property is read as the formula's result in the… |  |
| `property.expression_bake` | edit | layer | Turn the formula of a property of a layer into keys, in one history step with the revision checked: the formula is worked out at the project's frames (every… |  |
| `property.expression_detach` | edit | layer | Take the formula away from a property of a layer and keep the value it gave at the playhead as the property's value, in one history step with the revision… |  |
| `property.expression_clear` | edit | layer | Take the formula away from a property of a layer, in one history step with the revision checked: the property is read as its keys again, with the values they… |  |

## render

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `render.frame` | call | - | Draw the project at a composition time into a PNG, with the evaluator and the render graph the display uses: the layers that show at the time over the video… |  |
| `render.look` | call | - | Draw the project as a small picture for you to look at: a JPEG of the project at a composition time, or a sheet of up to 12 times evenly spaced from `time` to… |  |
| `render.strip` | call | - | Draw a window of the project frame by frame as one lossless PNG sheet to look at: the frames from `time` (the project frame that holds it) for `frames` tiles… |  |
| `render.compare` | call | - | Set the project against a reference video of the media library, frame by frame: for each frame of a window, one row of three pictures drawn at the same size… |  |
| `render.cost` | call | - | Measure what each frame of a window costs to draw, so a heavy place is found by a number and not guessed from a picture. |  |

## scene

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `scene.snapshot` | call | layer | Read the project at its current revision: canvas, lanes, layers (kind, span, lane, z_order, source), each layer's properties valued at a composition time with… |  |
| `scene.brief` | call | scene | Read the open project in one short answer: its canvas, frame rate and length, its revision and session generation, how many layers there are of each kind, and… |  |
| `scene.layout` | call | scene | Read where the layers drawn at a composition time are on the canvas, in canvas pixels (the box of each layer's content moved by every transform above it, the… |  |
| `scene.motion` | call | scene | Read, along the whole composition, where a layer moves far between two frames and is drawn sharp: it then shows as separate copies, not as a movement, and the… |  |
| `scene.survey` | read | scene | Read how the composition's motion is made, counted from the session and not drawn: what a piece does by habit, before you look at it. |  |

## session

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `session.handshake` | read | - | Read the engine's version, what it can do on this device (each capability available or not, with the engine's reason when not), the project's revision and the… |  |
| `session.batch` | call | - | Apply several edits as one transaction: in order, all or none, one revision, one report per item. |  |
| `session.validate` | call | - | Run a batch and undo it: the reports it would give or the first item that stops it, with the project and its revision unchanged. |  |
| `session.events` | read | - | Read what changed in the session after a sequence number: kind, revision, generation and cause of each event, never state. |  |

## text

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `text.document_snapshot` | read | layer | Read the document of a text layer (the target, else the selected layer): its content (UTF-8), its paragraphs (the lines the content is made of, with the line… |  |
| `text.replace_range` | edit | layer | Replace the bytes `start..end` of a text layer's content (the target, else the selected layer) with `text`, in one history step with the project revision… |  |
| `text.layout_snapshot` | read | layer | Read how a text layer's text is laid out in its box now (the target, else the selected layer), as the picture lays it out: the box's width and height in… |  |
| `text.style_set` | edit | layer | Change the style of the bytes `start..end` of a text layer's content (the target, else the selected layer) in one history step with the project revision… |  |
| `text.anchor_set` | edit | layer | Add, move or remove an anchor of a text layer's document (the target, else the selected layer) in one history step with the revision checked. |  |
| `text.motion` | read | layer | Read how the words and letters of a text layer or a caption layer (the target, else the selected layer) come in and go out, and what can be offered: the… |  |
| `text.motion_set` | edit | layer | Give the words or letters of a text layer or a caption layer (the target, else the selected layer) a way of coming in (`phase` 1), going out (`phase` 2) or… |  |
| `text.motion_clear` | edit | layer | Take the way of coming in (`phase` 1) or going out (`phase` 2) away from the text of a text layer or a caption layer (the target, else the selected layer)… |  |
| `text.motion_paste` | edit | layer | Give a text layer or a caption layer (the target, else the selected layer) the animation the engine's motion clipboard holds (`text.motion_copy`), over its own… |  |
| `text.paste` | edit | layer | Replace the bytes `start..end` of a text layer's content (the target, else the selected layer) with what the engine's clipboard holds (text.copy), in one… |  |
| `text.paragraph_set` | edit | layer | Change what the paragraphs a range of a text layer's content touches (the target, else the selected layer) set of the paragraph layout, in one history step… |  |

## transition

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `transition.add` | edit | layer | Put a transition on the cut where a layer (the target, else the selected layer) ends and the layer that follows it on its row begins: a kind (the default is… |  |
| `transition.remove` | edit | layer | Take a transition away (by id, else the one out of the target layer). |  |
| `transition.set_timing` | edit | layer | Change a transition's length (in frames, at most 5 seconds; one saved longer keeps its length until it is changed), where it lies about its cut, or its… |  |
| `transition.set_kind` | edit | layer | Make a transition another kind of the catalog. |  |
| `transition.set_param` | edit | layer | Change one setting of a transition's kind (its strength, the motion blur, a spin's pulse, pivot, edges and direction, a dip's hold): by the key… |  |
| `transition.catalog` | read | - | Read the transition kinds the engine offers: each one's name, label, category and the version of its algorithm. |  |

## transport

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `transport.snapshot` | read | - | Read the transport, the timeline's geometry and which tools are available at this moment. |  |

## vector

| Tool | Use | Target | What it does | Notes |
|---|---|---|---|---|
| `vector.set_item` | edit | layer | Change the fill colour, the stroke colour or the stroke width of one part of a vector layer (the target, else the selected layer). |  |
| `vector.items` | read | layer | Read the parts of a vector layer (the target, else the selected layer), in drawing order: each part's name, how many paths and nodes it has, what fills it (a… |  |

## Not offered to an agent (57)

Do not look for another way to do these: they are the owner's, and each has the engine's reason.

- `transport.play`: the transport and the playhead are the owner's: playing, pausing and seeking move what the owner is looking at, and are not an edit that a history step can…
- `transport.pause`: the transport and the playhead are the owner's: playing, pausing and seeking move what the owner is looking at, and are not an edit that a history step can…
- `transport.seek`: the transport and the playhead are the owner's: playing, pausing and seeking move what the owner is looking at, and are not an edit that a history step can…
- `project.create`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `project.open`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `project.save`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `project.save_as`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `cache.status`: the cache of generated files is the engine's housekeeping, shown to the owner; clearing it cannot be taken back
- `cache.prune`: the cache of generated files is the engine's housekeeping, shown to the owner; clearing it cannot be taken back
- `cache.clear`: the cache of generated files is the engine's housekeeping, shown to the owner; clearing it cannot be taken back
- `project.set_autosave`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `project.close`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `project.forget`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `font.remove_asset`: takes a font out of the project, and a text layer that asked for one of its families is left unresolved: the owner decides which fonts the project carries; not…
- `layer.set_pivot_shown`: a view of the owner's interface (what the canvas shows or catches, the timeline's compact view, a slider's ruler, the bottom bar), not part of the project: the…
- `layer.set_motion_path`: a view of the owner's interface (what the canvas shows or catches, the timeline's compact view, a slider's ruler, the bottom bar), not part of the project: the…
- `context.nav`: a view of the owner's interface (what the canvas shows or catches, the timeline's compact view, a slider's ruler, the bottom bar), not part of the project: the…
- `text.motion_copy`: the owner's selection or clipboard (what they chose to edit, what they copied): an agent builds a text or a motion with the edit tools instead
- `gallery.access`: the device's gallery of the person's videos and pictures, reached by the system's permission and the person's own choice, one item at a time: not an agent's to…
- `gallery.request_access`: the device's gallery of the person's videos and pictures, reached by the system's permission and the person's own choice, one item at a time: not an agent's to…
- `gallery.list`: the device's gallery of the person's videos and pictures, reached by the system's permission and the person's own choice, one item at a time: not an agent's to…
- `gallery.toggle`: the device's gallery of the person's videos and pictures, reached by the system's permission and the person's own choice, one item at a time: not an agent's to…
- `gallery.take`: the device's gallery of the person's videos and pictures, reached by the system's permission and the person's own choice, one item at a time: not an agent's to…
- `gallery.preview_open`: the device's gallery of the person's videos and pictures, reached by the system's permission and the person's own choice, one item at a time: not an agent's to…
- `gallery.preview_close`: the device's gallery of the person's videos and pictures, reached by the system's permission and the person's own choice, one item at a time: not an agent's to…
- `media.pool_preview_open`: a preview or an audition that the owner's interface asks for, drawn on a shared image or played on the device's output: `media.look` and `render.look` show an…
- `asset.preview_open`: a preview or an audition that the owner's interface asks for, drawn on a shared image or played on the device's output: `media.look` and `render.look` show an…
- `library.preview_open`: a preview or an audition that the owner's interface asks for, drawn on a shared image or played on the device's output: `media.look` and `render.look` show an…
- `library.preview_close`: a preview or an audition that the owner's interface asks for, drawn on a shared image or played on the device's output: `media.look` and `render.look` show an…
- `media.audition`: a preview or an audition that the owner's interface asks for, drawn on a shared image or played on the device's output: `media.look` and `render.look` show an…
- `media.audition_state`: a preview or an audition that the owner's interface asks for, drawn on a shared image or played on the device's output: `media.look` and `render.look` show an…
- `media.pool_preview_close`: a preview or an audition that the owner's interface asks for, drawn on a shared image or played on the device's output: `media.look` and `render.look` show an…
- `caption.select`: the owner's selection or clipboard (what they chose to edit, what they copied): an agent builds a text or a motion with the edit tools instead
- `text.copy`: the owner's selection or clipboard (what they chose to edit, what they copied): an agent builds a text or a motion with the edit tools instead
- `text.edit_copy`: the owner's selection or clipboard (what they chose to edit, what they copied): an agent builds a text or a motion with the edit tools instead
- `property.ruler`: a view of the owner's interface (what the canvas shows or catches, the timeline's compact view, a slider's ruler, the bottom bar), not part of the project: the…
- `canvas.set_snap`: a view of the owner's interface (what the canvas shows or catches, the timeline's compact view, a slider's ruler, the bottom bar), not part of the project: the…
- `canvas.set_fidelity`: a view of the owner's interface (what the canvas shows or catches, the timeline's compact view, a slider's ruler, the bottom bar), not part of the project: the…
- `timeline.seek_to_layer`: the transport and the playhead are the owner's: playing, pausing and seeking move what the owner is looking at, and are not an edit that a history step can…
- `timeline.strip`: a view of the owner's interface (what the canvas shows or catches, the timeline's compact view, a slider's ruler, the bottom bar), not part of the project: the…
- `timeline.step_frame`: the transport and the playhead are the owner's: playing, pausing and seeking move what the owner is looking at, and are not an edit that a history step can…
- `timeline.seek_to_key`: the transport and the playhead are the owner's: playing, pausing and seeking move what the owner is looking at, and are not an edit that a history step can…
- `library.create`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `library.open`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `library.list`: reads or stops a copy of media or a package of the owner's library, which an agent working on the open project has no part in
- `library.rename`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `library.delete`: deletes a project of the owner's library with its folder: it cannot be taken back, so only the owner, on the device, does it
- `library.duplicate`: opens, creates, saves, renames, copies or closes a project of the owner's library, or sets how the session saves: the owner's own work, not an edit of the…
- `library.add_media`: reads or writes a file of the owner's device outside the project's folder, at a place the owner chose with the system's picker: an agent has no picker and…
- `library.media_status`: reads or stops a copy of media or a package of the owner's library, which an agent working on the open project has no part in
- `library.export_package`: reads or writes a file of the owner's device outside the project's folder, at a place the owner chose with the system's picker: an agent has no picker and…
- `library.import_package`: reads or writes a file of the owner's device outside the project's folder, at a place the owner chose with the system's picker: an agent has no picker and…
- `library.package_status`: reads or stops a copy of media or a package of the owner's library, which an agent working on the open project has no part in
- `library.package_cancel`: reads or stops a copy of media or a package of the owner's library, which an agent working on the open project has no part in
- `library.media_cancel`: reads or stops a copy of media or a package of the owner's library, which an agent working on the open project has no part in
- `account.snapshot`: the account of the person using the app and the platform's gate on the app: not the project's, and not an agent's
- `app.gate`: the account of the person using the app and the platform's gate on the app: not the project's, and not an agent's
