# Components

## Static
```
class CUIStatic : CUIWindow
```

XML:
```xml
<icon x="135" y="25" width="100" height="100" stretch="1">
    <texture>ui_inGame2_placeable_workshop</texture>
</icon>
```

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitStatic("button", self)
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `x` | 0 | `number` | x coordinate |
| `y` | 0 | `number` | y coordinate |
| `width` | 0 | `number` | x coordinate |
| `height` | 0 | `number` | x coordinate |
| `heading_angle` | 0.0 | `number` | Heading |
| `light_anim` | "" | `string` | Light Anim |
| `la_cyclic` | 1 | `0`\|`1` | Flag |
| `la_text` | 1 | `0`\|`1` | Flag |
| `la_texture` | 1 | `0`\|`1` | Flag |
| `la_alpha` | 0 | `0`\|`1` | Flag |
| `xform_anim` | "" | `string` | Flag |
| `xform_anim_cyclic` | 1 | `0`\|`1` | Flag |
| `complex_mode` | false | `boolean` | Flag |
| `hint` | "" | `string` | Flag |

## Text
```
class CUITextWnd : CUIWindow
```
XML:
```xml
<light_duration x="10" y="150" width="350" height="20" stretch="1" complex_desc="0">
    <text font="letterica18" complex_mode="1" align="c" vert_align="c"/>
</light_duration>
```

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitTextWnd("light_duration", self)
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

## Progress Bar
```
class CUIProgressBar : CUIWindow
```
XML:
```xml
<enemy_health x="37" y="6" width="256" height="10" horz="1" min="0" max="100">
    <progress>
        <texture>ui_sega_healph_progress</texture>
    </progress>
</enemy_health>
```

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitProgressBar("enemy_health", self)
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |
