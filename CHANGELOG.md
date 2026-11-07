# Changelog

## 0.2.25 (2026-11-07)

- A video in a shape: `slot.fill` takes a video of the library too. It plays inside the shape from its start at the project's pace, with no sound, takes the shape's motion, effects and framing, and holds its last frame past its own end. `fill.kind` says `Video` (9). What `slot.set` says a shape takes (`accepts`) is what is wanted and refuses nothing; `slot_video_later` and `slot_refuses_image` are gone, and a video that declares no length is refused with `source_has_no_length`. Projects with a video in a shape are schema 69.

## 0.2.24 (2026-11-07)

- Replace on any shape: `slot.fill` takes any shape as it is (an imported picture is one), with nothing marked first. The first Replace makes it an asset named after its layer, keeps what it showed for `slot.clear`, and lays the picture to cover it. `slot.set`'s name, description and must-fill are optional: they say which shapes are the assets, and lock nothing. `not_replaceable` is for a layer that is not a shape.

## 0.2.23 (2026-11-07)

- Media slots, for templates: `slot.set` makes a shape a place kept for the owner's own picture, with a name, a description, what it takes, whether it must be filled, a group and an order, proportions, a focus and how a picture sits. `slot.fill` puts a picture of the project's library in. Only the content changes: the shape's keys, effects, masks, matte, parent, motion and timing are what the picture takes. `slot.clear` gives the designed look back as it was, and `slot.remove` makes it a plain shape again. `slot.list` reads every slot of the project and its scenes, and `missing` counts those that must be filled and are empty. The framing inside the frame is the layer's `paint.offset`, `paint.scale` and `paint.rotation`. A video is refused (`slot_video_later`) for now. In the editor, an empty slot shows a dashed frame with a picture sign. `slot.fill` also replaces the picture of an ordinary picture layer (an imported picture): only the picture changes, laid to cover its box; `not_replaceable` for a layer that is neither. `export.presets` (version 4) names the slots that must be filled and are empty (`empty_slots`, `empty_slot_names`, `empty_slots_notice`); they never stop an export.

## 0.2.22 (2026-11-07)

- File names: a transition's add-on file is now `.rft` (the `file_name` of `addon.export`) and a project's package `.rfp`, one short family of Refusion's own. A file an older build named `.rtx` or `.rproj` is read as it always was, since the engine knows a file by its content, never by its name.

## 0.2.21 (2026-11-06)

- Camera shots, as a dialogue between two is filmed: `camera.frame_layer` (version 4) takes `shot` `cut` or `move` (and `length` for a move; the engine's one second when absent): the camera is cut at `time` into a piece of its own on its row, named `Shot: ` and the layer's name, that holds the layer framed (`cut`) or moves to it from the shot before, easing in and out in a straight line (`move`); nothing before `time` changes. `margin` is now optional (the engine's 0.08). Refused for a shot: `layer_not_showing`, `camera_moves_after`, `camera_driven`, `move_past_camera_end`, `unknown_shot`, `length_without_move`. The report says the shot, the piece, the camera it was cut from, where it begins and where the framing is reached.
- A Sequence's length is made of what is seen or heard: a camera, a null or an adjustment layer that runs past the last clip no longer makes it (or its file) longer. `layer.insert_camera` (version 3) without a `duration` runs to the end of the composition (`start` 0 for the whole project), and a camera that ends at the Sequence's end follows it as clips come and go.
- A layer inserted past the end makes the Sequence as long as it at once; a project opened gets its length before anything reads it.
- The canvas is the stage: a camera's frame is kept on its composition's canvas (never larger than it, held inside, zoomed in the least when turned), in the picture, the file and the editor alike; values past it are drawn kept on it and `transport.snapshot`'s `camera_notice` says `camera_on_stage`; the canvas gestures and `camera.frame_layer` (version 5) write values that keep it there. `layer.insert_camera` is version 4. A world larger than the screen is built as a scene with a larger canvas and its own camera.

## 0.2.20 (2026-11-06)

- `layer.insert_source` (version 3): with no `track` and no `new_row`, a video or a photo goes on the main track (the bottom row, which has no gaps) at the cut nearest `start` (before the clip `start` falls in when it is in its first half, after it otherwise; after the last clip), and the clips from there make way; put in at `edit_head`, it takes the edit head to its end, so pictures put in one after another follow in order. A sound keeps its rows. To lay a picture over another (an overlay), name `track` or `new_row`.
- `timeline.close_gap` (new): closes a gap of the main track at a time (exact, or `edit_head`): the clips after it come back by its length, nothing else moves. A clip lifted from the main track to a row above now stays a layer at its time and nothing else moves (the main track keeps a gap there, which the layer covers); deleting or shortening a clip of the main track still closes up behind it.
- A Sequence's length is now the end of its last layer, on any row: it grows and it shrinks with every edit and is taken when a project opens, so the play stops on the last frame and an export has no black at its end. A scene (Composition) keeps the length it was given.
- Playback: a video covered by an opaque full-frame picture above it is not decoded (and not marked as waiting on the timeline); the decoders of the layers that take the display are made ready before they do, the changes of coverage included.

## 0.2.19 (2026-11-05)

- The add-ons of the person's platform account (`addon.account_state`, `addon.account_sync`, `addon.account_upload`, `addon.account_delete`): an add-on installed on a device where someone is signed in is kept in their account (private, never shown to anyone), and every device signed in to it brings it and installs it by the same checks as a file; one removed from the account is taken off the devices; one the person takes off a device is not brought back there until they install it. The quota is the platform's. These are the person's own tools, not an agent's: an add-on an agent installs with the owner's yes is kept in the account by the engine itself.

## 0.2.18 (2026-11-05)

- A transition add-on may draw its wipe from a picture its package brings: the node `matte.image` (`image`, the picture's place in the package, which `addon.json` lists under `assets` with an `image/` type; `invert`) reveals the incoming shot where the picture is dark first and where it is bright last; `transition.def.schema` describes it. Such a transition is made by an author's package (`rpro addon pack`); a definition given as text alone cannot bring a picture, and `addon.inspect` refuses it with the reason. A project that uses one carries its pictures, so it opens with them on a device that has not installed the add-on.

## 0.2.17 (2026-11-05)

- `transition.catalog` (version 4) names, for each transition, the add-on that brings it when it is installed on this device (`addons`: its id; empty for a built-in and for one only a project carries): what `addon.export` and `addon.remove` take. On the phone, the person shares their transitions as `.rtx` files and opens one sent to them with Refusion, which shows its name, maker, licence and an engine-drawn preview before it is installed.

## 0.2.16 (2026-11-05)

- Add-ons: a transition of one's own travels as a file. A transition is installed, listed, removed and kept as an add-on, a package (`.rtx`) whose first entry is its manifest (`addon.json`: kind, id, version, name, maker, licence; the format is `schema/addon.schema.json`) and whose entry is its definition (`transition.json`). `addon.inspect` reads a package (a file's handle, or the manifest's and the definition's texts for an agent) and checks it whole, as an install would, and keeps it under a number (`staged`); `addon.install` installs it, with the owner's yes for an agent; `addon.list`, `addon.remove` (the owner's alone) and `addon.export` (to a file the owner chose). They replace `transition.def.validate`, `transition.def.install`, `transition.def.list` and `transition.def.remove`, which are gone; `transition.def.export`, `transition.def.preview` and `transition.def.save_from` stay (`save_from` now keeps the add-on it makes, `staged`, for `addon.install`). A licence is required. Refused with the reason: a truncated or altered file, a project's package, a kind this app does not read, a manifest and a definition that name different versions, the same version with other content, an older version, more than an add-on may hold. `designing-a-transition.md` takes the new path. Authors: `rpro addon pack <folder>` makes the file and checks it.

## 0.2.15 (2026-11-05)

- The end of a scrub lands on the picture the scrub last showed: `transport.scrub_end`, and a pan that ends (`timeline.pan_end`, at once or after its carry), put the playhead on the first frame of the instant that picture shows, when it is within 0.4 s of where the scrub was (farther, where it was), and that instant is then shown at its exact frame, so the picture does not jump back or forward at the release. The transport reports where it landed. To be at an exact time, use `transport.seek`.

## 0.2.14 (2026-11-05)

- Transitions of one's own. `transition.def.export` reads the text of any transition the engine holds (a built-in's too); `transition.def.validate` checks a definition's text as an install would and says how it stands (`standing`: `new`, `newer` than the one held, or the `same`), writing nothing; `transition.def.list` reads the definitions that are not built in, where each is from (`installed`, `embedded` in a project, `placeholder`) and how many transitions of the open project use it. `transition.def.install` asks the owner on the device for each definition (its name and version) and installs it on their yes; `transition.def.remove` is the owner's alone. An installed definition is added by its id like a built-in, and a project that uses one carries its text, so it opens with it on a device that does not have it. A project naming a definition this engine has nowhere opens with that transition shown as a cut (the cut's own frame half of each picture) and saves it back as it was read; one saved by the version held with other content is drawn by the one held and said so. Refused with a reason: an id in `pro.refusion.`, a definition that declares a code, a former code or name or replaces something, a version older than the one held, the same version with other content (raise the version), more than 256 KiB.
- `transition.def.preview` draws a definition, installed or not, on a transition of the open project as a strip of 2 to 24 frames (as `transition.set_kind` would make it, in the drawing only: nothing changes, nothing is installed). `transition.def.save_from` makes a definition from a transition as it is set (its settings, length and curve as its own, under the name given, in `mine.` unless an id is given; saving again under the same name makes its next version), and installs nothing. A new craft page, `designing-a-transition.md`: what a cut asks of a transition and the path through these tools.
- The transition table of the craft (`choosing.md`) names the thirteen transitions of 0.2.12 and 0.2.13 by what a cut should say.

## 0.2.13 (2026-11-05)

- Six more transitions: Flash (a burst of light hides the change: `strength` in stops, `cut` the share of the time the change takes about the middle), Blur Dissolve (the shots blur as they cross, `blur` a percentage of the frame's longer side), Light Leak (a warm light sweeps across as they dissolve, `strength`), Glitch (slices that jump sideways with the colours read apart, `strength`, `split`), Swirl (both shots twist about a point, `twist` in degrees, centre) and Ripple (rings run out from a point, `height`, centre). Add them by name (`pro.refusion.flash`, `pro.refusion.blur_dissolve`, `pro.refusion.light_leak`, `pro.refusion.glitch`, `pro.refusion.swirl`, `pro.refusion.ripple`) or code (107 to 112); both shots are shown across the whole transition, and each look is strongest in its middle and gone at its ends.

## 0.2.12 (2026-11-05)

- Seven new transitions that change from one shot to the next along a matte, a field the change's edge crosses: Wipe (a straight edge, `angle`), Clock Wipe (a hand that turns once round a point, `start`, `direction`, centre), Blinds (bands each crossed at once, `angle`, `count`), Iris (a circle that opens from a point or closes to it, `direction`, centre), Shape Reveal (a circle, square, diamond, star or hexagon that grows from a point, `shape`, `rotation`, centre), Luma Fade (the next shot appears in its brightest places first, or its darkest, `order`) and Noise Dissolve (grains, `grain`). Each has `softness` (the edge, a percentage of its travel); the wipes, the iris and the shape have `glow` (light along the edge). Add them by their name (`pro.refusion.wipe`, `pro.refusion.clock`, `pro.refusion.blinds`, `pro.refusion.iris`, `pro.refusion.shape_reveal`, `pro.refusion.luma_fade`, `pro.refusion.noise_dissolve`) or their code (100 to 106) with `transition.add`; both pictures are shown across the whole transition, as in a dissolve.

## 0.2.11 (2026-11-05)

- Spin (version 1.3.0): the turn (`strength`) takes any angle from 45 to 1440 degrees again, not only whole turns; the next picture always ends upright, whatever the turn. A project saved with an earlier version opens with its turn as it was saved.

## 0.2.10 (2026-11-04)

- Spin, Zoom In and Zoom Out (version 1.2.0) change from one shot to the next across a seam, not a mix everywhere at once: the next shot takes the place of the first inside an edge that runs across the canvas while the blur is drawn, so the streaks of the blur carry the first shot's colours across the edge into the next one's, as a smear dragged over two pictures laid side by side does. Zoom In opens an iris from the pivot out (`seam` `iris_out`), Zoom Out closes one from the edges in (`iris_in`), Spin opens a fan from the ray at `seam_angle` degrees (`fan`); the setting `seam` takes `none` for the mix they had before, and `softness` (a percentage of the seam's travel) sets how soft its edge is. A seam is put across the blur's streaks, never along them: an iris for a zoom, a fan for a turn. A project saved by an older version opens with `seam` `none` and draws as it was saved. A transition may now have up to twelve settings.

## 0.2.9 (2026-11-04)

- `project.set_color_mix` sets the space the keys of colours are mixed in across the project: 0 the display numbers as they are (what projects before this release mixed in; they keep it), 1 linear light, 2 OKLab (the default of every project made now). Between two keys of a colour the colour passes through that space: in display blue and yellow, green and magenta, red and cyan meet at a dark grey; in OKLab they keep a colour. No key changes. It covers the keys of colour properties only (not the colours between the stops of one gradient, nor the dissolve of a transition). `scene.brief` (version 2) now says which space the project is in (`color_mix`: `display`, `linear` or `perceptual`): read it before judging how a colour moves; switching it is the person's choice.
- A shape can morph to another outline. `morph.to` sets the outline a shape layer goes to (a rectangle, an ellipse, a polygon or a star with its numbers, or another shape layer's own geometry) and `shape.morph` (percent, 0 its own outline, 100 the target's) says how far it has gone: a number like any other, so key it, give it a curve and a speed graph. `morph.analyze` reads what `morph.to` would make of a pair, without setting it: the segments each outline is given, the turn taken out, the ratio of the areas and the corners of each. Both refuse by name (`not_a_shape`, `morph_to_itself`, `morph_open_contour_unsupported`, `morph_multi_contour_unsupported`, `morph_target_required`). A line or an open path cannot morph, and only one outline per side. The layer's motion blur blurs its transform and opacity as ever but not the change of the outline itself, which is drawn at the frame's instant. The shape's own outline stays when its kind changes to a path (`shape.kind`), whatever stage the morph is at.

## 0.2.8 (2026-11-04)

- Spin, Zoom In, Zoom Out and Whip are rebuilt: Spin turns the picture once (`strength` is the turn in degrees, a multiple of 360), Zoom In and Zoom Out meet at one scale at the change, Whip is one strip of the two pictures touching, panned across with a `strength` punch. The two pictures dissolve across a share of the transition's *time* in the middle of the motion, and the motion blur is a designed shutter (`blur` degrees at the peak, 1440 at most) that is strongest where they dissolve. Spin, Zoom and Whip need a few frames of each layer beyond the cut; `transition.add` overlaps the layers by what is missing unless the policy says otherwise. Zoom In and Zoom Out have a `split` setting (the colour fringe at the change).

## 0.2.7 (2026-11-04)

- Transitions are read from the engine's definitions: the transition reference lists each kind's settings in their real units (a turn in degrees, a zoom in times, a blur in degrees of shutter), its speed-ramp curves, and, for Spin, Zoom In and Zoom Out, a `flash` setting (the light at the change, in stops). Spin, Zoom and Whip change from one picture to the next across a short dissolve, so each layer needs a few frames beyond the cut; `transition.add` overlaps the layers by what is missing unless the policy says otherwise.

## 0.2.6 (2026-11-04)

- A craft page, `storyboard-master-prompt.md`: how to write the master prompt of a storyboard, the one text the Storyboard sheet of Refusion splits into images (the general description, then `Image 1:`, `Image 2:` … each with its complete prompt and, optionally, a `Title:` and a `Narration:` line), what the general description holds, how to write an image that stands alone, how many images a script needs, and a checklist. Setting and generating a storyboard stay the person's.

## 0.2.5 (2026-11-03)

- Nine tools of the creator program (`earn.state`, `earn.sync`, `earn.apply`, `earn.withdraw`, `earn.coupon`, `earn.payout_method`, `earn.payout`, `earn.payout_cancel`, `earn.convert`) are listed under "Not offered to an agent": applying to the program and what it pays are the person's own business with their account. An assistant that asks for one is refused.

## 0.2.4 (2026-11-03)

- `inspector.read` (version 3) declares what can be done with the layer or the layers chosen, after the properties, in a new section Actions (`section_codes` 9): the item `scene.create` has editor 16 and makes a scene of the layers chosen, or of the selected layer, as `layer.precompose` does; its reason says what the scene would draw differently, or why it cannot be made. While several layers are chosen the table holds only these actions, where it held every property turned off.
- `library.preview_open` and `library.look` also draw the kinds of background (`kind` 3; the ids are the `fill_kind` codes `layer.insert_background` takes) and of shape (`kind` 4; the `shape_kind` codes `layer.insert_shape` takes), each as a project of one layer of that kind drawn as a frame of a file is, so an assistant can see what a gradient, a mesh or a star looks like before it places one.

## 0.2.3 (2026-11-01)

- A tool that acts at an instant needs the time in the call: an exact time `{"num": n, "den": d}`, or `"edit_head"` for the owner's edit head (`time_ref` where a tool takes `time_given`). A layer's `start`, a keyframe, a marker, an asset, a cut, a trim, a re-parent that holds the layer, a camera framing and a caption sentence added, copied, cut or trimmed all take it. A call without one is refused with `time_required`; both together with `time_ambiguous`.
- A keyframe tool names its keyframe: `key` is an id, `"selection"` for the keyframes the owner selected, or `key_from` in a batch. A call that names none is refused with `key_required`.
- A tool that acts on a layer needs `target` in the call: the layer's id, or `target_from` in a batch; `"selection"` (the layer the owner selected) is refused for a remote agent. A call that names no layer is refused with `target_required`. `camera.frame_layer` takes `layer`, and `layer.precompose` takes `from` and `to`, the same way.
- `session.handshake` lists, for each capability, the tools that belong to it, with the engine's reason when it is not available on the device.
- A motion applied from the library remembers its item: `text.motion` and `layer.motion` list `phase_origin` for each phase ("Rise", or "Rise — modified" once a number was changed), `scene.survey` and the inspector say the same, and `library.restore` (`item` `text.motion` or `layer.edge`, `phase`) puts it back as it was applied. A motion built by hand has none.
- Every item of the library says when to use it (`usage`) and is found by words in English and in Arabic, written with the item, by its phase and by its kind: the engine pages for the looks and the transitions show them, and `library.catalog` answers the item whose name matches first, then the words, then the usage (Arabic spellings are read as one: "الة كاتبة" finds "آلة كاتبة").
- The index and the seal are written for catalog version 3 (the catalog names each tool's capability).

## 0.2.2 (2026-11-01)

- A library item is applied with `inspector.add` (`item=library`, `kind` its id), also as a batch item; a motion takes the place of what its phase held and the reply's `replaced` names it. Inside a batch a caption's motion is over every sentence of the layer.
- The handshake lists audio mixing and the media pool as available (it said they were not).
- Search words in Arabic for the effects, looks, transitions and ready-made motion, listed in the library reference.
- The index is written for the build that carries these changes (175 tools offered, 57 not offered, each with its reason).

## 0.2.1 (2026-11-01)

- Apache License 2.0, a README with an install table for each assistant, and this changelog.
- `scene.survey`, the tool that counts the habits of a piece from the session, is in the index and the pages on checks and on the defaults to catch.

## 0.2.0 (2026-11-01)

- One skill for every assistant, remote or local (the two earlier skills became one).
- Craft pages: direction (from a request to a plan), timing by role (numbers tagged measured, engine or starting point), choreography, directions to start from, choosing a preset, recipe, effect or transition for a job, the defaults to catch, checks (looking, measuring, judging, mending), Arabic and text; three worked plans.
- An index of the engine in `references/engine/`, written by the Refusion build: the tools an assistant is offered and the ones it is not (with reasons), effects, looks, transitions, ready-made motion and recipes, with what each does and its settings.
- The seal at the end of `SKILL.md` names the catalog version the text was written for.

## 0.1.0 (2026-10-25)

- First release: the way of working with Refusion's tools (read, check, apply, look, mend) and two pages, one on how to make a scene look designed and move well and one on Arabic and text.
