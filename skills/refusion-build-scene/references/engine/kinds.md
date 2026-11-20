# Layer kinds

Written by `rpro skill-reference --write` from catalog version 3, fingerprint `9aa4256683fb9560`; do not edit. The gate compares this page with what the engine writes now, so a thing added to the engine and left out of it stops the save. The engine is the truth: when this page and a reply differ, the reply is right.

Each table is the engine's own schema of a fresh layer: the path as the project's document writes it (`"transform.position": [960, 540]`), its kind of value, its range or every name a choice takes, a new layer's default, and whether it moves (a motion `{from, to, at, for, ease}` or `{keys}`). A value left out of a new layer is that default. A value a layer has only once a choice is made (a pattern's settings, a fixed text box's size, a morph's amount) is in the table of that choice below.

## Every layer

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `transform.position` | [x, y] |  | [0, 0] | yes |
| `transform.scale` | [x, y] |  | [100, 100] | yes |
| `transform.rotation` | number |  | 0 | yes |
| `transform.anchor` | [x, y] |  | [0, 0] | yes |
| `transform.opacity` | number | 0 to 100 | 100 | yes |
| `transform.shutter_angle` | number | 0 to 720 | 180 | yes |
| `transform.shutter_phase` | number | -360 to 360 | -90 | yes |
| `transform.scale_linked` | choice | Off, On | "On" |  |
| `transform.follows_camera` | choice | Off, On | "On" |  |

## shape (`"kind": "shape"`; a rectangle's values, and the grade at the end of the page; the other outlines, the fills and a morph add theirs below)

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `shape.kind` | choice | Rectangle, Ellipse, Polygon, Star, Line, Path | "Rectangle" |  |
| `shape.size` | [x, y] | [0, 0] to [100000, 100000] | [400, 300] | yes |
| `shape.corner_tl` | number | 0 to 100000 | 0 | yes |
| `shape.corner_tr` | number | 0 to 100000 | 0 | yes |
| `shape.corner_br` | number | 0 to 100000 | 0 | yes |
| `shape.corner_bl` | number | 0 to 100000 | 0 | yes |
| `shape.morph_target` | choice | None, Rectangle, Ellipse, Polygon, Star, Another shape | "None" |  |
| `fill.kind` | choice | Solid, Linear gradient, Radial gradient, Conic gradient, Image, Pattern, Mesh gradient, Colour points, Evolving field, Video | "Solid" |  |
| `color.color` | colour |  | #3366CCFF | yes |
| `stroke.color` | colour |  | #FFFFFFFF | yes |
| `stroke.width` | number | 0 to 100000 | 0 | yes |
| `stroke.cap` | choice | Butt, Round, Square | "Butt" |  |
| `stroke.join` | choice | Miter, Round, Bevel | "Miter" |  |
| `stroke.dash` | number | 0 to 100000 | 0 | yes |
| `stroke.gap` | number | 0 to 100000 | 0 | yes |
| `stroke.dash_offset` | number | -100000 to 100000 | 0 | yes |
| `stroke.trim_start` | number | 0 to 100 | 0 | yes |
| `stroke.trim_end` | number | 0 to 100 | 100 | yes |
| `stroke.trim_offset` | number | -1000 to 1000 | 0 | yes |
| `stroke.taper_start_length` | number | 0 to 100 | 0 | yes |
| `stroke.taper_start_width` | number | 0 to 100 | 100 | yes |
| `stroke.taper_end_length` | number | 0 to 100 | 0 | yes |
| `stroke.taper_end_width` | number | 0 to 100 | 100 | yes |
| `stroke.wobble_amount` | number | 0 to 200 | 0 | yes |
| `stroke.wobble_size` | number | 1 to 2000 | 180 | yes |
| `stroke.wobble_seed` | number | 0 to 100000 | 0 | yes |
| `stroke.wobble_evolution` | number | -100000 to 100000 | 0 | yes |
| `stroke.start_marker` | choice | None, Open arrow, Filled arrow, Dot | "None" |  |
| `stroke.end_marker` | choice | None, Open arrow, Filled arrow, Dot | "None" |  |
| `stroke.marker_size` | number | 0 to 1000 | 40 | yes |
| `stroke_paint.kind` | choice | Solid, Linear gradient, Radial gradient, Conic gradient, Image, Pattern, Mesh gradient, Colour points, Evolving field, Video | "Solid" |  |
| `color.blend_mode` | choice | Normal, Multiply, Screen, Overlay, Darken, Lighten, Color Dodge, Color Burn, Hard Light, Soft Light, Difference, Exclusion, Hue, Saturation, Color, Luminosity | "Normal" |  |
| `time.step` | number | 0 to 240 | 0 |  |

### `"shape.kind": "Ellipse"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|

### `"shape.kind": "Polygon"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `shape.sides` | number | 3 to 64 | 6 | yes |

### `"shape.kind": "Star"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `shape.sides` | number | 3 to 64 | 5 | yes |
| `shape.inner_ratio` | number | 0 to 1 | 0.5 | yes |

### `"shape.kind": "Line"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|

### `"fill.kind": "Linear gradient"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `fill.start` | [x, y] |  | [0, 0] | yes |
| `fill.end` | [x, y] |  | [400, 300] | yes |
| `paint.offset` | [x, y] |  | [0, 0] | yes |
| `paint.scale` | [x, y] |  | [100, 100] | yes |
| `paint.rotation` | number |  | 0 | yes |
| `paint.pivot` | [x, y] |  | [50, 50] | yes |
| `paint.extend` | choice | Pad, Repeat, Mirror | "Pad" |  |

### `"fill.kind": "Radial gradient"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `fill.center` | [x, y] |  | [200, 150] | yes |
| `fill.radius` | number | 1 to 100000 | 250 | yes |
| `paint.offset` | [x, y] |  | [0, 0] | yes |
| `paint.scale` | [x, y] |  | [100, 100] | yes |
| `paint.rotation` | number |  | 0 | yes |
| `paint.pivot` | [x, y] |  | [50, 50] | yes |
| `paint.extend` | choice | Pad, Repeat, Mirror | "Pad" |  |

### `"fill.kind": "Conic gradient"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `fill.center` | [x, y] |  | [200, 150] | yes |
| `fill.angle` | number |  | 0 | yes |
| `paint.offset` | [x, y] |  | [0, 0] | yes |
| `paint.scale` | [x, y] |  | [100, 100] | yes |
| `paint.rotation` | number |  | 0 | yes |
| `paint.pivot` | [x, y] |  | [50, 50] | yes |
| `paint.extend` | choice | Pad, Repeat, Mirror | "Pad" |  |

### `"fill.kind": "Pattern"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `fill.pattern_kind` | choice | Checker, Grid, Dots, Stripes, Noise, Grain | "Checker" |  |
| `fill.pattern_scale` | number | 1 to 100000 | 64 | yes |
| `fill.pattern_angle` | number |  | 0 | yes |
| `fill.pattern_strength` | number | 0 to 1 | 0.5 | yes |
| `fill.pattern_seed` | number | 0 to 4294967295 | 1 |  |
| `fill.pattern_ground` | colour |  | #3366CCFF | yes |
| `fill.pattern_ink` | colour |  | #122447FF | yes |
| `paint.offset` | [x, y] |  | [0, 0] | yes |
| `paint.scale` | [x, y] |  | [100, 100] | yes |
| `paint.rotation` | number |  | 0 | yes |
| `paint.pivot` | [x, y] |  | [50, 50] | yes |
| `paint.extend` | choice | Pad, Repeat, Mirror | "Pad" |  |

### `"fill.kind": "Mesh gradient"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `fill.mesh_top_left` | colour |  | #3366CCFF | yes |
| `fill.mesh_top_right` | colour |  | #122447FF | yes |
| `fill.mesh_bottom_left` | colour |  | #122447FF | yes |
| `fill.mesh_bottom_right` | colour |  | #3366CCFF | yes |
| `fill.mesh_warp` | number | 0 to 1 | 0.35 | yes |
| `fill.mesh_scale` | number | 1 to 100000 | 300 | yes |
| `fill.mesh_seed` | number | 0 to 4294967295 | 1 |  |
| `paint.offset` | [x, y] |  | [0, 0] | yes |
| `paint.scale` | [x, y] |  | [100, 100] | yes |
| `paint.rotation` | number |  | 0 | yes |
| `paint.pivot` | [x, y] |  | [50, 50] | yes |
| `paint.extend` | choice | Pad, Repeat, Mirror | "Pad" |  |

### `"fill.kind": "Colour points"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `fill.points_model` | choice | Inverse distance, Gaussian | "Inverse distance" |  |
| `fill.points_swirl` | number | -720 to 720 | 0 | yes |
| `fill.points_bend` | number | 0 to 1 | 0 | yes |
| `fill.points_bend_scale` | number | 1 to 100000 | 300 | yes |
| `fill.points_seed` | number | 0 to 4294967295 | 1 |  |
| `fill.points_dither` | number | 0 to 8 | 1 | yes |
| `fill.points_contrast` | number | 0 to 3 | 1 | yes |
| `paint.offset` | [x, y] |  | [0, 0] | yes |
| `paint.scale` | [x, y] |  | [100, 100] | yes |
| `paint.rotation` | number |  | 0 | yes |
| `paint.pivot` | [x, y] |  | [50, 50] | yes |
| `paint.extend` | choice | Pad, Repeat, Mirror | "Pad" |  |

### `"fill.kind": "Evolving field"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `fill.field_kind` | choice | Noise, Cells, Waves, Rays | "Noise" |  |
| `fill.field_scale` | number | 2 to 100000 | 420 | yes |
| `fill.field_octaves` | number | 1 to 6 | 4 |  |
| `fill.field_lacunarity` | number | 1.2 to 4 | 2 | yes |
| `fill.field_gain` | number | 0 to 1 | 0.5 | yes |
| `fill.field_seed` | number | 0 to 4294967295 | 1 |  |
| `fill.field_phase` | number |  | 0 | yes |
| `fill.field_warp` | number | 0 to 1 | 0.3 | yes |
| `fill.field_angle` | number |  | 0 | yes |
| `fill.field_contrast` | number | 0 to 4 | 1.4 | yes |
| `fill.field_centre` | [x, y] |  | [50, 50] | yes |
| `fill.field_rays` | number | 1 to 64 | 12 |  |
| `paint.offset` | [x, y] |  | [0, 0] | yes |
| `paint.scale` | [x, y] |  | [100, 100] | yes |
| `paint.rotation` | number |  | 0 | yes |
| `paint.pivot` | [x, y] |  | [50, 50] | yes |
| `paint.extend` | choice | Pad, Repeat, Mirror | "Pad" |  |

### `"shape.morph_target"` set adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `shape.morph` | number | -100 to 200 | 0 | yes |

## text

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `content.text` | text |  | "" |  |
| `font.family` | text |  | "sans-serif" |  |
| `font.arabic_family` | text |  | "" |  |
| `font.size` | number | 1 to 500 | 48 | yes |
| `font.weight` | choice | Thin, ExtraLight, Light, Regular, Medium, SemiBold, Bold, ExtraBold, Black | "Regular" |  |
| `font.style` | choice | Normal, Italic | "Normal" |  |
| `font.line_height` | number | 0.5 to 3 | 1.2 | yes |
| `font.tracking` | number | -1000 to 5000 | 0 |  |
| `font.word_spacing` | number | -1000 to 5000 | 0 |  |
| `paragraph.align` | choice | Start, Center, End, Justify | "Start" |  |
| `paragraph.direction` | choice | Auto, LTR, RTL | "Auto" |  |
| `paragraph.indent` | number | 0 to 20 | 0 |  |
| `box.mode` | choice | Auto width, Auto height, Fixed | "Auto width" |  |
| `box.padding` | number | 0 to 1000 | 0 |  |
| `box.max_lines` | number | 0 to 100 | 0 |  |
| `backdrop.mode` | choice | None, Box, Lines | "None" |  |
| `fill.kind` | choice | Solid, Linear gradient, Radial gradient, Conic gradient | "Solid" |  |
| `fill.color` | colour |  | #FFFFFFFF | yes |
| `stroke.color` | colour |  | #000000FF | yes |
| `stroke.width` | number | 0 to 50 | 0 | yes |
| `color.blend_mode` | choice | Normal, Multiply, Screen, Overlay, Darken, Lighten, Color Dodge, Color Burn, Hard Light, Soft Light, Difference, Exclusion, Hue, Saturation, Color, Luminosity | "Normal" |  |
| `time.step` | number | 0 to 240 | 0 |  |

### `"box.mode": "Fixed"` adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `box.width` | number | 1 to 10000 | 800 |  |
| `box.height` | number | 1 to 10000 | 400 |  |
| `paragraph.vertical_align` | choice | Top, Middle, Bottom | "Top" |  |
| `box.overflow` | choice | Visible, Clip, Ellipsis | "Visible" |  |
| `box.fit` | choice | Off, Shrink | "Off" |  |

### `"backdrop.mode": "Box"` (or `"Lines"`) adds

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `backdrop.color` | colour |  | #00000099 |  |
| `backdrop.padding_x` | number | -1 to 10 | 0.35 |  |
| `backdrop.padding_y` | number | -1 to 10 | 0.1 |  |
| `backdrop.radius` | number | 0 to 5 | 0.25 |  |

## background

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `fill.kind` | choice | Solid, Linear gradient, Radial gradient, Conic gradient, Image, Pattern, Mesh gradient, Colour points, Evolving field, Video | "Solid" |  |
| `color.color` | colour |  | #3366CCFF | yes |
| `color.blend_mode` | choice | Normal, Multiply, Screen, Overlay, Darken, Lighten, Color Dodge, Color Burn, Hard Light, Soft Light, Difference, Exclusion, Hue, Saturation, Color, Luminosity | "Normal" |  |
| `time.step` | number | 0 to 240 | 0 |  |

## null

| path | value | range or names | default | moves |
|---|---|---|---|---|

## adjustment

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `color.blend_mode` | choice | Normal, Multiply, Screen, Overlay, Darken, Lighten, Color Dodge, Color Burn, Hard Light, Soft Light, Difference, Exclusion, Hue, Saturation, Color, Luminosity | "Normal" |  |

And the grade below.

## camera

The view its composition is seen through: the top camera shown is the active one, and every layer that follows it (`transform.follows_camera`) is seen through it. Its frame is kept on the canvas (the canvas is the stage): a camera the size of the canvas stands still, so zoom it in, its frame made smaller than the canvas (`transform.scale` below 100; `transform.zoom` reads how far in), for it to move, pan or push in.

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `transform.scale` | [x, y] | [1, 1] to [100, 100] | [100, 100] | yes |

## The grade (a shape's, a picture's, a video's and an adjustment layer's)

| path | value | range or names | default | moves |
|---|---|---|---|---|
| `grade.exposure` | number | -5 to 5 | 0 | yes |
| `grade.contrast` | number | -100 to 100 | 0 | yes |
| `grade.pivot` | number | 0 to 1 | 0.413 | yes |
| `grade.highlights` | number | -100 to 100 | 0 | yes |
| `grade.shadows` | number | -100 to 100 | 0 | yes |
| `grade.whites` | number | -100 to 100 | 0 | yes |
| `grade.blacks` | number | -100 to 100 | 0 | yes |
| `grade.temperature` | number | -100 to 100 | 0 | yes |
| `grade.tint` | number | -100 to 100 | 0 | yes |
| `grade.vibrance` | number | -100 to 100 | 0 | yes |
| `grade.saturation` | number | -100 to 100 | 0 | yes |
| `grade.lift` | [x, y] | [-1, -1] to [1, 1] | [0, 0] | yes |
| `grade.gamma` | [x, y] | [-1, -1] to [1, 1] | [0, 0] | yes |
| `grade.gain` | [x, y] | [-1, -1] to [1, 1] | [0, 0] | yes |
| `grade.offset` | [x, y] | [-1, -1] to [1, 1] | [0, 0] | yes |
| `grade.lift_master` | number | -100 to 100 | 0 | yes |
| `grade.gamma_master` | number | -100 to 100 | 0 | yes |
| `grade.gain_master` | number | -100 to 100 | 0 | yes |
| `grade.offset_master` | number | -100 to 100 | 0 | yes |
| `grade.curve_luma_0` | [x, y] | [-1, -1] to [1, 1] | [0, 0] | yes |
| `grade.curve_luma_1` | [x, y] | [-1, -1] to [1, 1] | [1, 1] | yes |
| `grade.curve_luma_2` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_luma_3` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_luma_4` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_luma_5` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_luma_6` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_luma_7` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_luma_8` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_luma_9` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_red_0` | [x, y] | [-1, -1] to [1, 1] | [0, 0] | yes |
| `grade.curve_red_1` | [x, y] | [-1, -1] to [1, 1] | [1, 1] | yes |
| `grade.curve_red_2` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_red_3` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_red_4` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_red_5` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_red_6` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_red_7` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_red_8` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_red_9` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_green_0` | [x, y] | [-1, -1] to [1, 1] | [0, 0] | yes |
| `grade.curve_green_1` | [x, y] | [-1, -1] to [1, 1] | [1, 1] | yes |
| `grade.curve_green_2` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_green_3` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_green_4` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_green_5` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_green_6` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_green_7` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_green_8` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_green_9` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_blue_0` | [x, y] | [-1, -1] to [1, 1] | [0, 0] | yes |
| `grade.curve_blue_1` | [x, y] | [-1, -1] to [1, 1] | [1, 1] | yes |
| `grade.curve_blue_2` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_blue_3` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_blue_4` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_blue_5` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_blue_6` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_blue_7` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_blue_8` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_blue_9` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_hue_0` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_hue_1` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_hue_2` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_hue_3` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_hue_4` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_hue_5` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_hue_6` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_hue_7` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_hue_8` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_hue_9` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_sat_0` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_sat_1` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_sat_2` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_sat_3` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_sat_4` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_sat_5` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_sat_6` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_sat_7` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_sat_8` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_sat_9` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_lum_0` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_lum_1` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_lum_2` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_lum_3` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_lum_4` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_lum_5` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_lum_6` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_lum_7` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_lum_8` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_hue_lum_9` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_lum_sat_0` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_lum_sat_1` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_lum_sat_2` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_lum_sat_3` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_lum_sat_4` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_lum_sat_5` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_lum_sat_6` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_lum_sat_7` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_lum_sat_8` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_lum_sat_9` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_sat_sat_0` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_sat_sat_1` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_sat_sat_2` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_sat_sat_3` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_sat_sat_4` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_sat_sat_5` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_sat_sat_6` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_sat_sat_7` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_sat_sat_8` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.curve_sat_sat_9` | [x, y] | [-1, -1] to [1, 1] | [-1, -1] | yes |
| `grade.red_hue` | number | -100 to 100 | 0 | yes |
| `grade.red_saturation` | number | -100 to 100 | 0 | yes |
| `grade.red_luminance` | number | -100 to 100 | 0 | yes |
| `grade.orange_hue` | number | -100 to 100 | 0 | yes |
| `grade.orange_saturation` | number | -100 to 100 | 0 | yes |
| `grade.orange_luminance` | number | -100 to 100 | 0 | yes |
| `grade.yellow_hue` | number | -100 to 100 | 0 | yes |
| `grade.yellow_saturation` | number | -100 to 100 | 0 | yes |
| `grade.yellow_luminance` | number | -100 to 100 | 0 | yes |
| `grade.green_hue` | number | -100 to 100 | 0 | yes |
| `grade.green_saturation` | number | -100 to 100 | 0 | yes |
| `grade.green_luminance` | number | -100 to 100 | 0 | yes |
| `grade.aqua_hue` | number | -100 to 100 | 0 | yes |
| `grade.aqua_saturation` | number | -100 to 100 | 0 | yes |
| `grade.aqua_luminance` | number | -100 to 100 | 0 | yes |
| `grade.blue_hue` | number | -100 to 100 | 0 | yes |
| `grade.blue_saturation` | number | -100 to 100 | 0 | yes |
| `grade.blue_luminance` | number | -100 to 100 | 0 | yes |
| `grade.purple_hue` | number | -100 to 100 | 0 | yes |
| `grade.purple_saturation` | number | -100 to 100 | 0 | yes |
| `grade.purple_luminance` | number | -100 to 100 | 0 | yes |
| `grade.magenta_hue` | number | -100 to 100 | 0 | yes |
| `grade.magenta_saturation` | number | -100 to 100 | 0 | yes |
| `grade.magenta_luminance` | number | -100 to 100 | 0 | yes |
| `grade.skin_protect` | number | 0 to 100 | 0 | yes |
| `grade.look_amount` | number | 0 to 100 | 100 | yes |
| `grade.vignette_amount` | number | -100 to 100 | 0 | yes |
| `grade.vignette_midpoint` | number | 0 to 100 | 50 | yes |
| `grade.vignette_roundness` | number | -100 to 100 | 0 | yes |
| `grade.vignette_feather` | number | 0 to 100 | 50 | yes |
| `grade.grain_amount` | number | 0 to 100 | 0 | yes |
| `grade.grain_size` | number | 0 to 100 | 25 | yes |
| `grade.grain_roughness` | number | 0 to 100 | 50 | yes |
| `grade.grain_colour` | number | 0 to 100 | 0 | yes |
| `grade.bloom_amount` | number | 0 to 100 | 0 | yes |
| `grade.bloom_threshold` | number | 0 to 100 | 70 | yes |
| `grade.bloom_size` | number | 0 to 100 | 50 | yes |
| `grade.halation_amount` | number | 0 to 100 | 0 | yes |
| `grade.halation_threshold` | number | 0 to 100 | 80 | yes |
| `grade.halation_size` | number | 0 to 100 | 30 | yes |
| `grade.clarity` | number | -100 to 100 | 0 | yes |
| `grade.texture` | number | -100 to 100 | 0 | yes |
| `grade.select1_hue` | number | 0 to 360 | 0 | yes |
| `grade.select1_hue_width` | number | 0 to 360 | 360 | yes |
| `grade.select1_hue_softness` | number | 0 to 90 | 10 | yes |
| `grade.select1_saturation_low` | number | 0 to 100 | 0 | yes |
| `grade.select1_saturation_high` | number | 0 to 100 | 100 | yes |
| `grade.select1_saturation_softness` | number | 0 to 50 | 5 | yes |
| `grade.select1_lightness_low` | number | 0 to 100 | 0 | yes |
| `grade.select1_lightness_high` | number | 0 to 100 | 100 | yes |
| `grade.select1_lightness_softness` | number | 0 to 50 | 5 | yes |
| `grade.select1_exposure` | number | -5 to 5 | 0 | yes |
| `grade.select1_contrast` | number | -100 to 100 | 0 | yes |
| `grade.select1_temperature` | number | -100 to 100 | 0 | yes |
| `grade.select1_tint` | number | -100 to 100 | 0 | yes |
| `grade.select1_saturation` | number | -100 to 100 | 0 | yes |
| `grade.select1_hue_shift` | number | -180 to 180 | 0 | yes |
| `grade.select1_window` | number | 0 to 2 | 0 | yes |
| `grade.select1_window_x` | number | 0 to 100 | 50 | yes |
| `grade.select1_window_y` | number | 0 to 100 | 50 | yes |
| `grade.select1_window_width` | number | 1 to 300 | 40 | yes |
| `grade.select1_window_height` | number | 1 to 300 | 40 | yes |
| `grade.select1_window_rotation` | number | -180 to 180 | 0 | yes |
| `grade.select1_window_softness` | number | 0 to 100 | 30 | yes |
| `grade.select1_window_invert` | number | 0 to 1 | 0 | yes |
| `grade.select2_hue` | number | 0 to 360 | 0 | yes |
| `grade.select2_hue_width` | number | 0 to 360 | 360 | yes |
| `grade.select2_hue_softness` | number | 0 to 90 | 10 | yes |
| `grade.select2_saturation_low` | number | 0 to 100 | 0 | yes |
| `grade.select2_saturation_high` | number | 0 to 100 | 100 | yes |
| `grade.select2_saturation_softness` | number | 0 to 50 | 5 | yes |
| `grade.select2_lightness_low` | number | 0 to 100 | 0 | yes |
| `grade.select2_lightness_high` | number | 0 to 100 | 100 | yes |
| `grade.select2_lightness_softness` | number | 0 to 50 | 5 | yes |
| `grade.select2_exposure` | number | -5 to 5 | 0 | yes |
| `grade.select2_contrast` | number | -100 to 100 | 0 | yes |
| `grade.select2_temperature` | number | -100 to 100 | 0 | yes |
| `grade.select2_tint` | number | -100 to 100 | 0 | yes |
| `grade.select2_saturation` | number | -100 to 100 | 0 | yes |
| `grade.select2_hue_shift` | number | -180 to 180 | 0 | yes |
| `grade.select2_window` | number | 0 to 2 | 0 | yes |
| `grade.select2_window_x` | number | 0 to 100 | 50 | yes |
| `grade.select2_window_y` | number | 0 to 100 | 50 | yes |
| `grade.select2_window_width` | number | 1 to 300 | 40 | yes |
| `grade.select2_window_height` | number | 1 to 300 | 40 | yes |
| `grade.select2_window_rotation` | number | -180 to 180 | 0 | yes |
| `grade.select2_window_softness` | number | 0 to 100 | 30 | yes |
| `grade.select2_window_invert` | number | 0 to 1 | 0 | yes |
| `grade.select3_hue` | number | 0 to 360 | 0 | yes |
| `grade.select3_hue_width` | number | 0 to 360 | 360 | yes |
| `grade.select3_hue_softness` | number | 0 to 90 | 10 | yes |
| `grade.select3_saturation_low` | number | 0 to 100 | 0 | yes |
| `grade.select3_saturation_high` | number | 0 to 100 | 100 | yes |
| `grade.select3_saturation_softness` | number | 0 to 50 | 5 | yes |
| `grade.select3_lightness_low` | number | 0 to 100 | 0 | yes |
| `grade.select3_lightness_high` | number | 0 to 100 | 100 | yes |
| `grade.select3_lightness_softness` | number | 0 to 50 | 5 | yes |
| `grade.select3_exposure` | number | -5 to 5 | 0 | yes |
| `grade.select3_contrast` | number | -100 to 100 | 0 | yes |
| `grade.select3_temperature` | number | -100 to 100 | 0 | yes |
| `grade.select3_tint` | number | -100 to 100 | 0 | yes |
| `grade.select3_saturation` | number | -100 to 100 | 0 | yes |
| `grade.select3_hue_shift` | number | -180 to 180 | 0 | yes |
| `grade.select3_window` | number | 0 to 2 | 0 | yes |
| `grade.select3_window_x` | number | 0 to 100 | 50 | yes |
| `grade.select3_window_y` | number | 0 to 100 | 50 | yes |
| `grade.select3_window_width` | number | 1 to 300 | 40 | yes |
| `grade.select3_window_height` | number | 1 to 300 | 40 | yes |
| `grade.select3_window_rotation` | number | -180 to 180 | 0 | yes |
| `grade.select3_window_softness` | number | 0 to 100 | 30 | yes |
| `grade.select3_window_invert` | number | 0 to 1 | 0 | yes |
| `grade.select4_hue` | number | 0 to 360 | 0 | yes |
| `grade.select4_hue_width` | number | 0 to 360 | 360 | yes |
| `grade.select4_hue_softness` | number | 0 to 90 | 10 | yes |
| `grade.select4_saturation_low` | number | 0 to 100 | 0 | yes |
| `grade.select4_saturation_high` | number | 0 to 100 | 100 | yes |
| `grade.select4_saturation_softness` | number | 0 to 50 | 5 | yes |
| `grade.select4_lightness_low` | number | 0 to 100 | 0 | yes |
| `grade.select4_lightness_high` | number | 0 to 100 | 100 | yes |
| `grade.select4_lightness_softness` | number | 0 to 50 | 5 | yes |
| `grade.select4_exposure` | number | -5 to 5 | 0 | yes |
| `grade.select4_contrast` | number | -100 to 100 | 0 | yes |
| `grade.select4_temperature` | number | -100 to 100 | 0 | yes |
| `grade.select4_tint` | number | -100 to 100 | 0 | yes |
| `grade.select4_saturation` | number | -100 to 100 | 0 | yes |
| `grade.select4_hue_shift` | number | -180 to 180 | 0 | yes |
| `grade.select4_window` | number | 0 to 2 | 0 | yes |
| `grade.select4_window_x` | number | 0 to 100 | 50 | yes |
| `grade.select4_window_y` | number | 0 to 100 | 50 | yes |
| `grade.select4_window_width` | number | 1 to 300 | 40 | yes |
| `grade.select4_window_height` | number | 1 to 300 | 40 | yes |
| `grade.select4_window_rotation` | number | -180 to 180 | 0 | yes |
| `grade.select4_window_softness` | number | 0 to 100 | 30 | yes |
| `grade.select4_window_invert` | number | 0 to 1 | 0 | yes |
