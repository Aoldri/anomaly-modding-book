# Components

- [Static](#static)
- [Text](#text)
- [Progress Bar](#progress-bar)

## Static
> class CUIStatic : [CUIWindow](layouts.md#window)

XML:
```xml
<icon x="135" y="25" width="100" height="100" stretch="1">
    <texture>ui_inGame2_placeable_workshop</texture>
</icon>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `x` | 0 | `number` | The horizontal position of the top-left corner of the Static element in pixels. |
| `y` | 0 | `number` | The vertical position of the top-left corner of the Static element in pixels. |
| `width` | 0 | `number` | The width of the Static element in pixels. |
| `height` | 0 | `number` | The height of the Static element in pixels. |
| `heading_angle` | 0.0 | `number` | The angle (in degrees) by which to rotate the Static element clockwise. |
| `light_anim` | "" | `string` | The name of the light animation to use for the Static element. |
| `la_cyclic` | 1 | `0`\|`1` | Whether the light animation should repeat in a cycle or stop after one iteration. |
| `la_text` | 1 | `0`\|`1` | Whether the light animation should affect the text of the Static element if one is present. |
| `la_texture` | 1 | `0`\|`1` | Whether the light animation should affect the texture of the Static element if one is present. |
| `la_alpha` | 0 | `0`\|`1` | Whether the light animation should affect the alpha channel of the Static element if one is present. |
| `xform_anim` | "" | `string` | The name of the transform animation to use for the Static element. |
| `xform_anim_cyclic` | 1 | `0`\|`1` | Whether the transform animation should repeat in a cycle or stop after one iteration. |
| `complex_mode` | false | `boolean` | Whether to enable complex mode for the Static element. |
| `hint` | "" | `string` | The tooltip text to display when the mouse cursor hovers over the Static element. |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitStatic("icon", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
|  | `SetTextureColor(color: number)` | Sets the color of the Static's texture to the specified `color`. |
| `number` | `GetTextureColor()` | Returns the current color of the Static's texture. |
|  | `AdjustHeightToText()` | Adjusts the height of the Static to fit the size of its text content. |
|  | `AdjustWidthToText()` | Adjusts the width of the Static to fit the size of its text content. |
| `boolean` | `GetStretchTexture()` | Returns whether the Static's texture is set to stretch to fit its dimensions. |
| [`CUILines`](undocumented.md#text) | `TextControl()` | Returns the CUILines object used for rendering text in the Static. |
|  | `InitTexture(path: string)` | Initializes the Static's texture to the image located at `path`. |
|  | `InitTextureEx(path: string, shader: string)` | Initializes the Static's texture to the image located at `path`, using the specified `shader`. |
|  | `SetTextureRect(pr: Frect)` | Sets the texture rectangle for the Static, which specifies which portion of the texture to display. |
|  | `SetStretchTexture(stretch_texture: boolean)` | Sets whether the Static's texture should stretch to fit its dimensions, based on the value of `stretch_texture`. |
| `Frect` | `GetTextureRect()` | Returns the current texture rectangle for the Static. |
|  | `EnableHeading(bool: boolean)` | Enables or disables the use of a heading for the Static, depending on the value of `bool`. |
|  | `SetHeading(angle: number)` | Sets the heading angle for the Static to the specified `angle`. |
| `number` | `GetHeading()` | Returns the current heading angle for the Static. |
|  | `SetConstHeading(angle: number)` | Sets the constant heading angle for the Static to the specified `angle`. |
| `number` | `GetConstHeading()` | Returns the current constant heading angle for the Static. |

## Text

> class CUITextWnd : [CUIWindow](layouts.md#window)

XML:
```xml
<light_duration x="10" y="150" width="350" height="20" stretch="1" complex_desc="0">
    <text font="letterica18" complex_mode="1" align="c" vert_align="c"/>
</light_duration>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitTextWnd("light_duration", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
|  | `AdjustHeightToText()` | |
|  | `AdjustWidthToText()` | |
|  | `SetText(txt: string)` | |
|  | `SetTextST(txt: string)` | |
| `string` | `GetText()` | |
|  | `SetFont(font: CGameFont)` | |
| `CGameFont` | `GetFont()` | |
|  | `SetTextColor(color: ARGB)` | |
| `ARGB` | `GetTextColor()` | |
|  | `SetTextComplexMode(mode: boolean)` | |
|  | `SetTextAlignment(al: enum)` | Enums:<br/>`0` - Left<br/>`1` - Right<br/>`2` - Center|
|  | `SetVTextAlignment(al: enum)` | Enums:<br/>`0` - Top<br/>`1` - Center<br/>`2` - Bottom |
|  | `SetEllipsis(mode: boolean)` | |
|  | `SetTextOffset(x: number, y: number)` | |

## Progress Bar

> CUIProgressBar : [CUIWindow](layouts.md#window)

XML:
```xml
<enemy_health x="37" y="6" width="256" height="10" horz="1" min="0" max="100">
    <progress>
        <texture>ui_sega_healph_progress</texture>
    </progress>
</enemy_health>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitProgressBar("enemy_health", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
|  | `SetProgressPos(pos: number)` | Sets the current position of the Trackbar to the specified value pos. |
| `number` | `GetProgressPos()` | Returns the current position of the Trackbar. |
|  | `SetRange(min: number, max: number)` | Sets the minimum and maximum values of the Trackbar range to `min` and `max`, respectively. |
| `number` | `GetRange_min()` | Returns the current minimum value of the Trackbar range. |
| `number` | `GetRange_max()` | Returns the current maximum value of the Trackbar range. |
|  | `ShowBackground(status: boolean)` | Sets the visibility of the Trackbar background to `status`. |
|  | `SetColor(color: ARGB)` | Sets the color of the Trackbar to the specified `color`. |
|  | `SetMinColor(color: ARGB)` | Sets the color of the Trackbar's minimum value indicator to the specified `color`. |
|  | `SetMiddleColor(color: ARGB)` | Sets the color of the Trackbar's middle value indicator to the specified `color`. |
|  | `SetMaxColor(color: ARGB)` | Sets the color of the Trackbar's maximum value indicator to the specified `color`. |
|  | `UseColor(status: boolean)` | Enables or disables the use of color on the Trackbar, depending on the value of `status`. |