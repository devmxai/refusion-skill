# Templates and recipes

A **template** is a scene the person fills with their own pictures and videos. A **recipe** is a scene you write as text when you have no connection to the engine (a chat): the person pastes it into Refusion and it is built there.

## Assets: the shapes the person fills

- Every picture or video you do not have (their product, their logo, their face) is a **shape** in the scene: a rounded card, a circle, the outline of a cup. Design the shape as the frame the media will be seen through, and give it all the motion, effects and timing the media should have. When the person puts something in it (Replace, `slot.fill`), only what it shows changes; the motion stays.
- Name each one with `slot.set`: a name the person recognises (`Coffee cup`), a description of what is wanted (`your cup or drink, seen from the front`), and `must_fill` 1 when the piece is not done without it. Use a group and an order for a set (a carousel). Naming locks nothing: any shape can be replaced, named or not. It is how the person and the next agent find the assets (`slot.list`, and the Assets sheet in the app).
- Give the empty shape a colour that reads as a placeholder in the piece's palette. The person sees it until they fill it, and an export with an empty must-fill asset is allowed, with a note.
- Texts stay texts: the person edits them as they are.

## Recipes: building with no connection

A recipe is one JSON object:

```json
{"refusion_recipe": 1, "name": "Coffee ad", "width": 1080, "height": 1920,
 "fps": {"num": 30, "den": 1}, "duration": {"num": 8, "den": 1},
 "items": [
  {"tool": "layer.insert_shape", "args": {"start": {"num": 0, "den": 1}, "duration": {"num": 8, "den": 1}, "shape_kind": 0}},
  {"tool": "property.set", "target_from": 0, "args": {"path": "shape.size", "value": {"vec2": [600, 740]}}},
  {"tool": "slot.set", "target_from": 0, "args": {"name": "Coffee cup", "must_fill": 1}}
 ]}
```

- The items are `session.batch` items, run in order as one transaction. An item names a layer an earlier item made by that item's position (`target_from`, counted from 0); it never gives a layer id or an `expected_revision`. Times are exact fractions; values are typed as the tools reference says (`{"vec2": [x, y]}`, `{"color": [r, g, b, a]}`, `{"scalar": n}`).
- A recipe edits the project's content only: no tool that reaches a file, a source or the network (no media is placed, no font imported, nothing fetched), and nothing that deletes. The project it builds has an empty media library: assets are shapes the person fills afterwards.
- A key lands inside its layer's span: the last key of a layer that ends at 8 s is at 7.9 s, not 8.
- Give the person the recipe as one block they can copy. In Refusion they press **Paste recipe** on the home screen; the project is built and opens. If the engine refuses it, they copy its words back to you: the words name the item's number, its tool and the engine's own reason. Fix that item and give the whole recipe again.
- With a connection, `recipe.run` builds the same text, and `rpro recipe check FILE` proves one without leaving anything.

A whole example, a vertical coffee ad with three assets and two texts: [examples/coffee-ad.rfr](../../examples/coffee-ad.rfr).
