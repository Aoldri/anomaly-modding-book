# Components

These classes are exported from the engine and allow us to compose different elements on-screen. Note that these are super low-level.



## Buttons

```lua
class CUICheckButton : CUI3tButton
```
XML:
```xml
<autoplay_btn x="256" y="373" width="93" height="22" stretch="1">
    <texture>ui_checkbox_TabLED</texture>
    <txt x="15" y="0" width="93" height="22" stretch="1">
        <text complex_mode="1" r="200" g="200" b="200" align="l"  vert_align="c" font="letterica16"/>
    </txt>
</autoplay_btn>
```

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitCheck("button", self)
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

```lua
class CUI3tButton : CUIButton
```
Lua:
```lua
-- class CUIButton : CUIStatic
local xml = CScriptXmlInit()
xml:Init3tButton("button", self)
```

XML:
```xml
<btn x="" y="" width="" height="" stretch="1">
    <texture></texture>
</btn>
```
Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `x` | 0 | `number` | x coordinate |
| `y` | 0 | `number` | y coordinate |
| `width` | 0 | `number` | width |
| `height` | 0 | `number` | x coordinate |
| `stretch` | 1 | `boolean` | The texture can stretch to fit the size of the button |

Elements:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `texture` | "" | `string` | Texture Description ID, determines what texture is drawn on the button |

## NPC Dialog Window
```
class CUIDialogWnd : CUIWindow
```

## Scripted Window
```
class CUIScriptWnd : CUIDialogWnd
```


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

## Property Box
```
class CUIPropertiesBox : CUIFrameWindow
```

## Scrollable Element
```
class CUIScrollView : CUIWindow
```
XML:
```xml
<tag_select_scroll x="4" y="4" width="120" height="193" stretch="1" complex_desc="0"/>
```

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitScrollView("tag_select_scroll", self)
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

## Textures
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

## Tabs
```
class CUITabButton : CUIButton
```

```
class CUITabControl : CUIWindow
```

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

## Slider
```
class CUITrackBar : CUIWindow
```
XML:
```xml
<trackbar x="64" y="4" width="140" height="16" stretch="1"/>
```

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitTrackBar("trackbar", self)
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

## ???
```
class CUIWindow
```

## ???
```
class CUISleepStatic : CUIStatic
```

## ???
```
class CUISpinFlt : CUICustomSpin
```

```
class CUISpinNum : CUICustomSpin
```

```
class CUISpinText : CUICustomSpin
```

## ???
```
class CUIFrameLineWnd : CUIWindow
```

## ???
```
class CUIFrameWindow : CUIWindow
```
XML:
```xml
<background x="326" y="256" width="370" height="265" stretch="1">
    <texture>ui_inGame2_hint_wnd_main_window</texture>
</background>
```

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitFrame("background", self)
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

## ???
```
class CUIGameCustom
```

## ???
```
class CUILines
```

## ???
```
class CUIListBox : CUIScrollView
```
<listbox x="28" y="150" width="764" height="558" can_select="0" always_show_scroll="1" stretch="1"/>
```

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitListBox("listbox", self)
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

```
class CUIListBoxItem : CUIFrameLineWnd
```

```
class CUIListBoxItemMsgChain : CUIListBoxItem
```

## ???
```
class CUIMMShniaga : CUIWindow
```

## ???
```
class CUIMapInfo : CUIWindow
```

```
class CUIMapList : CUIWindow
```

## ???
```
class CUIMessageBox : CUIStatic
```

```
class CUIMessageBoxEx : CUIDialogWnd
```

## ???
```
class CUIComboBox : CUIWindow
```
XML:
```xml
<select x="64" y="0" width="160" height="24" can_select="1">
    <select_font r="170" g="170" b="170" font="letterica16"/>
    <text_color>
        <e r="170" g="170" b="170"/>
        <d r="70" g="70" b="70"/>
    </text_color>
</select>
```

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitComboBox("select", self)
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

## ???
```
class CUICustomEdit : CUIWindow
```

```
class CUIEditBox : CUICustomEdit
```
XML:
```xml
<input x="12" y="20" width="160" height="30" stretch="1">
    <text x="4" font="letterica16" vert_align="c" align="l"/>
    <texture>ui_inGame2_edit_box_2</texture>
</input>
```

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitEditBox("input", self)
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

```
class CUIEditBoxEx : CUICustomEdit
```

## ???
```
class CUICustomSpin : CUIWindow
```