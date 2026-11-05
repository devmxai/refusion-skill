# Designing a transition

When none of the engine's transitions says what a cut should say, a transition of the owner's own is written as a definition: a small JSON text the engine reads, draws and keeps. This page is the craft of it and the path through the tools; the format itself is `schema/transition.def.schema.json`, and the engine's refusals say exactly what a text lacks.

## What a cut asks for

- **Continue the motion that leaves.** A shot that pans left hands over to a transition that moves left; a push the other way reads as a mistake. Read the outgoing layer's motion (`scene.motion`) before choosing a direction or an angle.
- **The length is the beat's.** At 120 bpm a beat is 0.5 s: a transition of half a beat (0.25 s) is a hit, a whole beat a breath, two beats a scene change. Off the grid it feels late. Most cuts want 0.3 to 0.8 s; a dissolve may take longer, a whip less.
- **One peak, on the cut.** The strongest instant (the blur at its widest, the light at its brightest, the edge mid-frame) belongs where the two shots meet. A speed ramp (`ramp`) puts it there and keeps both ends still.
- **The ends are the shots themselves.** Nothing of the transition shows on its first and last frames; a look that does is a filter, not a transition.
- **Restraint.** A strong transition on every cut is noise. Save it for the cuts that change the subject or the time; the rest are cuts or dissolves.

## Starting from one that is close

Write from the nearest built-in, never from nothing:

1. `transition.def.export` with its id (from `transition.catalog`): its text, exactly as the engine reads it.
2. Give the copy an id in a domain of its own (`com.example.name`; `mine.` is where the owner's own saved ones go), version `1.0.0`, a name in English and Arabic (`name.en`, `name.ar`) and search words in both (`words`). Drop `code`, `legacy` and `replaces`: the engine gives a code and replaces nothing for a definition from outside.
3. Change what should differ: a default (the angle, the softness, a glow), the length (`timing.default_ms`), the curve (`timing.curve`: a name, `{"bezier": [...]}` or `{"ramp": [out, in, peak]}`), or a node's numbers. Spatial values are shares of the canvas, never pixels: the same text looks the same at 720p and 4K, wide or tall.
4. `transition.def.preview` with the text and a transition of the open project: a strip of its frames on that real cut, nothing changed, nothing installed. Look at it as at any strip (`checks.md`): are the ends the shots, is the peak on the cut, does it read at phone size.
5. Make it an add-on: a manifest (the file addon.json, in the format `schema/addon.schema.json` describes) of the same id and version, with its kind (`"transition"`), its name in both languages, its maker (`author`) and its licence (`license`, required: what the person who installs it may do with it). `addon.inspect` with the manifest's text (`manifest`) and the definition's (`entry`) reads them as a package file is read and says whether it can be installed and how it stands to what is held (`new`, `newer`, `same`); it keeps the package under a number (`staged`).
6. `addon.install` with that number: the owner is asked on the device, with its name, version, maker and licence, and it is installed only on their yes. Then it is added like any other, by its id.

A changed definition takes a new version (1.0.0 to 1.1.0), in the manifest and the definition alike: the same version with other content is refused, so a project made with the first one never changes under the owner without saying so.

An author with files writes the same two texts into a folder and makes the add-on's file with `rpro addon pack <folder>` (it is checked as an install checks it); the file (`.rtx`) is what travels between devices.

## From a transition the owner has set

When the owner has tuned a transition on a cut and wants to keep it, `transition.def.save_from` with the transition and a name makes the definition with those settings, that length and that curve as its own. It installs nothing: the add-on made of it (licence `personal`, the owner's own) is kept under a number (`staged`) that `addon.install` takes. Saving again under the same name makes its next version. On the phone, "Save as my transition" at the bottom of a transition's settings does both.

## What travels

A project that uses an installed transition carries its text: it opens with the same transition on a device that never installed it. A project naming one nobody here has shows that transition as a cut and keeps it as it was saved, with a notice; nothing is lost.
