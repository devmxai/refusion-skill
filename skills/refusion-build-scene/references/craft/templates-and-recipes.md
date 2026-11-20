# Templates and project files

A **template** is a scene the person fills with their own pictures and videos. A **project file** (`.rfp`) is a whole scene you write as text when you have no connection to the engine (a chat): the person opens it in Refusion and the project is made there.

## Assets: the shapes the person fills

- Every picture or video you do not have (their product, their logo, their face) is a **shape** in the scene: a rounded card, a circle, the outline of a cup. Design the shape as the frame the media will be seen through, and give it all the motion, effects and timing the media should have. When the person puts something in it (Replace), only what it shows changes; the motion stays.
- Name each one by its `slot` in the project's file: a `name` the person recognises (`Coffee cup`), a `description` of what is wanted (`your cup or drink, seen from the front`), and `required` when the piece is not done without it. Use a group and an order for a set (a carousel). Naming locks nothing: any shape can be replaced, named or not. It is how the person and the next agent find the assets (`slot.list`, and the Assets sheet in the app).
- Give the empty shape a colour that reads as a placeholder in the piece's palette. The person sees it until they fill it, and an export with an empty must-fill asset is allowed, with a note.
- Texts stay texts: the person edits them as they are.

## A whole scene with no connection: the project's file

The project's file is the project's document, the same one an agent in the project's folder writes as `project.rfp` (and a connected agent with no folder reads with `project.file_read` and writes with `project.file_write`); its form, its names and what it carries are in [document](../engine/document.md).

```json
{"refusion": "project", "version": 2, "canvas": [1080, 1920], "fps": 30, "for": "8s",
 "layers": [
  {"key": "bg", "kind": "background", "at": "0s", "for": "8s", "color.color": "#14100C"},
  {"key": "cup", "kind": "shape", "at": "0.4s", "for": "7.6s", "shape.size": [600, 740],
   "transform.scale": {"from": [80, 80], "to": [100, 100], "at": "0s", "for": "0.6s", "ease": "out_back"}}
 ]}
```

- One object, headed `"refusion": "project"` with its canvas, its rate and its length. Every layer by its `key`, its `kind`, its `at` and its `for`, then its values and its motion; every unit as a scene by its `name` in `scenes`. Leave out `written`: it names a copy only the engine that wrote a file keeps.
- Write the project's content only: no media is placed and nothing is fetched. The person's pictures and videos go into shapes they fill afterwards (Replace). What the document does not carry yet (what `omitted` counts, effects, masks and named assets among them) cannot be in a file written offline: say so to the person, and say what a connected agent would add.
- Times are `"1.5s"` or `"45f"` and land on the frames of the rate. A layer's `at` and `for` are in the project's time; every time inside a layer (its keys, its accents) is counted from its `at`, so the cup above grows from its first frame, and moving its `at` moves its motion. A key lands inside its layer's span: the last key of a layer that lasts 7.6 s is before 7.6 s.
- Give the person the file as one block they can copy, and as `name.rfp` too where your chat can give a file. In Refusion they press **Paste recipe** on the home screen, or open the file with Refusion from WhatsApp, Files or their downloads; the project is made and opens (a code fence around the object is read as well). If the engine refuses it, nothing is made, and its words name the first addresses it refused: the person copies them back to you. Mend those addresses and give the whole file again.
- In the project's folder on the owner's computer, the same document is the file `project.rfp`, applied as it is saved (the folder's `AGENTS.md` says how); through the connector, `project.file_write` writes it. `rpro document check FILE` proves one without leaving anything.

Whole examples, each made by the engine with no refusal: [a title card](../../examples/title-card.rfp) · [a lower third in a scene of its own](../../examples/lower-third.rfp).

## Scene templates: one design, a value per use

A scene can be a template: a person or an agent uses it many times, each instance with its own text, font, pictures and what shows, while the design and its motion stay the designer's.

- **Make the scene a template.** Give the scene's entry in the project's file its `template` (`{"controls": [...]}`, with `intro`, `outro` and `hold` when it must stretch).
  - Give it sections when its length will change: `intro` and `outro` are the lengths that play at their own speed, and the outro ends with the instance.
  - `hold` says how the middle takes the rest: `stretch` (the default), `loop` or `freeze`.
  - An instance as long as the scene shows it as it is.
  - Sections do not apply to a scene that holds a video, a sound or a scene of its own (`template.state` says so).
- **Declare its controls.** Each entry of `controls` names a layer of the scene by its key (`layer`), with its `id` and its `kind`. The kinds:
  - `text`: a text's words;
  - `font`: its family;
  - `switch`: whether a layer shows;
  - `media`: the picture a shape is filled with.
  - `colour` and `number`: a property of the layer that has no keys, named by `property` by its path (the fill colour **fill.color**, the size **font.size**). A number stays inside its property's range.

  A control binds what is fixed: the value is one for the whole instance, and the keys the designer set stay as made.
- **Give an instance its values.** Write its `values` on the layer that shows the scene, by the controls' ids.
  - Its parameters: `control`, then `text`, `font`, `on` (1 or 0), `source` (a picture of the library), `colour` (`#RRGGBBAA`) or `number`; `clear` 1 gives back the designer's value.
  - Only that instance changes. The scene and its other instances do not.
  - The person sets the same values in the instance's inspector, in its own tab, Template, where each control is a row at the path `pkg.template.<control>`. An instance that gives a control its own value keeps it when the designer changes the scene; a control its `values` leaves out shows the designer's.
- **Read it back.** `template.state` gives the controls, the value each instance shows, why a control cannot take one, and the sections.
- **Take an instance apart.** Write it as layers of its own, with its values laid on.
