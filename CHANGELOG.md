# Changelog

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
