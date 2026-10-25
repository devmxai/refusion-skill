# Arabic and text

Refusion shapes text itself, Arabic and other right-to-left scripts included. Your part is to give it the text as the user wrote it and to choose a font that has the letters.

- **Give the text as written.** Type Arabic in its normal logical order. Never reverse the letters, never insert presentation forms or invisible marks to fix the look. The engine joins the letters and orders mixed Arabic and English.
- **Choose the font from the catalog.** Read the families with `read` (`font.catalog`) and a script filter for Arabic (script 2; Latin is 1). Do not name a family you have not found there. If a font has no glyph for the script, the engine substitutes one; `font.resolve` says which, and `render_look` shows it.
- **Mixed text.** For Arabic with English words or numbers, look at the picture: the order of the pieces in the line is what the viewer reads. Fix the text, not the letters.
- **Size and room.** Arabic often needs a slightly larger size than Latin text to read as equally strong, and more room for its line. `scene_layout` reports text that is too small (`text_below_legible`), that leaves the canvas or the safe area, and two texts that overlap; fix those before anything else.
- **Captions.** Captions are a layer of their own with cues of words and times (`guide_read` topic `text`). Their timing belongs to the speech; do not stretch a caption to fill space.
- **Write for the viewer.** Keep on-screen Arabic short and in the register the user used. Do not translate the user's wording unless they ask.

The guide page `text` has the tools for text, fonts and captions, and each tool's own page (`tool:<name>`) shows its parameters and an example.
