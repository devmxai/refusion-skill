# Changelog

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
