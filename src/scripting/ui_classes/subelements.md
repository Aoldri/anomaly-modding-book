# Subelements

- [Text](#text)
- [Font](#font)
- [Colour](#colour)
- [Stateful Text](#stateful-text)
- [Texture](#texture)

These are not proper UI elements, but rather common elements that show up in multiple components. As such, there are no 'functions' to use as they are instantiated from the classes themselves when parsing the XML.

## Text
Example:
```xml
<text font="letterica16" r="170" g="170" b="170" align="l">ui_ammo_count</text>
```

Tag: `text`

Node value: `String ID` - A string, defined inside `configs/ui/text/<language>/*.xml`, that determines the resulting localised text.

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `align` | `l` | `c`\|`r`\|`l` | Horizontal alignment:<br>`c` - Center<br>`r` - Right<br>`l` - Left|
| `vert_align` | `t` | `c`\|`b`\|`t` | Vertical alignment:<br>`c` - Center<br>`b` - Bottom<br>`t` - Top |
| `complex_mode` | `0` | `0`\|`1` | Whether to enable complex mode for the text. |

Also uses: [`font`](#font).

## Font

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `font` |  | `string` | Determines font to be used in text. |

<br>

<details>
<summary>Complete list of fonts</summary>

- `arial`
- `arial_14`
- `small`
- `medium`
- `graffiti19`
- `graffiti22`
- `graffiti32`
- `graffiti50`
- `letterica16`
- `letterica18`
- `letterica25`
- `di`

</details>

Also uses: [`colour`](#colour).

## Colour

Example:
```xml
<texture r="242" g="231" b="11">ui_mmap_secondary_alert</texture>
```
```xml
<text font="letterica16" color="ui_1"/>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `r` | Depends on component: `0`\|`255` | `number` | Red component of the colour. Range from `0`-`255` |
| `g` | Depends on component: `0`\|`255` | `number` | Green component of the colour. Range from `0`-`255` |
| `b` | Depends on component: `0`\|`255` | `number` | Blue component of the colour. Range from `0`-`255` |
| `a` | `255` | `number` | Alpha component of the colour. Range from `0` (transparent) - `255` (opaque) |
| `color` | white (`255`) | `string` | Alternative to specifying RGBA values directly: uses a String ID to map to  an RGB value. |

A comprehensive list of possible values for `color` can be found in `configs/ui/color_defs.xml`. With [Demonized's modified exes](https://github.com/themrdemonized/STALKER-Anomaly-modded-exes), it is possible to add custom colours into this file via DXML.

<details>
<summary>Complete list of vanilla colours</summary>

- <span style="color: rgb(255, 0, 0)">red</span>
- <span style="color: rgb(255, 150, 0)">orange</span>
- <span style="color: rgb(0, 255, 0)">green</span>
- <span style="color: rgb(0, 0, 255)">blue</span>
- <span style="color: rgb(255, 255, 255)">white</span>
- <span style="color: rgb(0, 0, 0)">black</span>
- <span style="color: rgb(128, 128, 128)">gray</span>
- <span style="color: rgb(115, 114, 112)">light_gray</span>
- <span style="color: rgb(100, 100, 100)">tut_gray</span>
- <span style="color: rgb(80, 80, 80)">dark_gray</span>
- <span style="color: rgb(255, 255, 0)">yellow</span>
- <span style="color: rgb(204, 0, 51)">d_red</span>
- <span style="color: rgb(230, 150, 30)">d_red_1</span>
- <span style="color: rgb(93, 0, 116)">d_purple</span>
- <span style="color: rgb(238, 153, 26)">d_orange</span>
- <span style="color: rgb(153, 255, 255)">d_cyan</span>
- <span style="color: rgb(100, 100, 255)">d_blue</span>
- <span style="color: rgb(51, 255, 102)">d_green</span>
- <span style="color: rgb(255, 0, 0)">ui_red</span>
- <span style="color: rgb(0, 255, 0)">ui_green</span>
- <span style="color: rgb(0, 0, 255)">ui_blue</span>
- <span style="color: rgb(255, 255, 255)">ui_white</span>
- <span style="color: rgb(0, 0, 0)">ui_black</span>
- <span style="color: rgb(128, 128, 128)">ui_gray</span>
- <span style="color: rgb(255, 255, 0)">ui_yellow</span>
- <span style="color: rgb(170, 170, 170)">ui_gray_1</span>
- <span style="color: rgb(140, 140, 140)">ui_gray_2</span>
- <span style="color: rgb(200, 200, 200)">ui_gray_3</span>
- <span style="color: rgb(135, 183, 116)">ui_lime</span>
- <span style="color: rgb(255, 255, 255)">ui_1</span>
- <span style="color: rgb(255, 232, 208)">ui_2</span>
- <span style="color: rgb(128, 128, 128)">ui_3</span>
- <span style="color: rgb(189, 189, 224)">ui_4</span>
- <span style="color: rgb(135, 123, 116)">ui_5</span>
- <span style="color: rgb(240, 217, 182)">ui_6</span>
- <span style="color: rgb(238, 155, 23)">ui_7</span>
- <span style="color: rgb(216, 186, 140)">ui_8</span>
- <span style="color: rgb(150, 150, 180)">ui_9</span>
- <span style="color: rgb(225, 225, 250)">ui_10</span>
- <span style="color: rgb(41, 27, 16)">ui_mm_font</span>
- <span style="color: rgb(250, 250, 250)">pda_white</span>
- <span style="color: rgb(56, 209, 115)">pda_green</span>
- <span style="color: rgb(209, 209, 56)">pda_yellow</span>
- <span style="color: rgb(238, 28, 36)">pda_red</span>
- <span style="color: rgb(56, 166, 209)">pda_blue</span>
- <span style="color: rgb(207, 155, 80)">edit</span>

</details>

## Texture

Example:
```xml
<texture>ui_inGame2_workshop_item_window</texture>
```

Tag: `texture`

Node value: `Texture ID` - A string, defined in a "Texture Description" inside `configs/ui/texture_descr/*.xml`, that determines the texture rectangle of the texture and the image it is taken from.

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `shader` |  | `string` | Determines the shader to be applied to the texture. |

Any components that use this `texture` can also have a `stretch` flag (`0`\|`1`) as an attribute, which determines if the texture stretches to fit the dimensions of the parent element.

Also uses: [`colour`](#colour).