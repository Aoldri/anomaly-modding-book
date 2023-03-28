# Inputs

- [Buttons](#buttons)
- [Combobox](#combobox)
- [Listbox](#listbox)
- [Text Field](#text-field)
- [Slider](#slider)

## Buttons


> CUICheckButton : CUI3tButton

XML:
```xml
<autoplay_btn x="256" y="373" width="93" height="22" stretch="1">
    <texture>ui_checkbox_TabLED</texture>
    <txt x="15" y="0" width="93" height="22" stretch="1">
        <text complex_mode="1" r="200" g="200" b="200" align="l"  vert_align="c" font="letterica16"/>
    </txt>
</autoplay_btn>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitCheck("button", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
| boolean | `GetCheck()` |  |  |
|  | `SetCheck(ch: boolean)` |  |  |
|  | `SetDependControl(pWnd: CUIWindow)` |  |  |

---


> CUI3tButton : CUIButton


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

Lua:
```lua
local xml = CScriptXmlInit()
xml:Init3tButton("button", self)
```

Elements:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `texture` | "" | `string` | Texture Description ID, determines what texture is drawn on the button |

## Combobox

> CUIComboBox : CUIWindow

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

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitComboBox("select", self)
```


## Listbox

> CUIListBox : [CUIScrollView](layouts.md#scrollable-window)


XML:
```xml
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

## Text Field


> class CUIEditBox : CUICustomEdit

XML:
```xml
<input x="12" y="20" width="160" height="30" stretch="1">
    <text x="4" font="letterica16" vert_align="c" align="l"/>
    <texture>ui_inGame2_edit_box_2</texture>
</input>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitEditBox("input", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
|  | `SetText(str: string)` |  |
| `string` | `GetText()` |  |
|  | `CaptureFocus(bCapture: boolean)` |  |
|  | `SetNextFocusCapturer(next_capturer: CUICustomEdit)` |  |
|  | `InitTexture(texture: string)` |  |

## Slider

> CUITrackBar : [CUIWindow](layouts.md#window)

XML:
```xml
<trackbar x="64" y="4" width="140" height="16" stretch="1"/>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitTrackBar("trackbar", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
|  | `GetCheck()` |  |
|  | `SetCheck()` |  |
|  | `GetIValue()` |  |
|  | `GetFValue()` |  |
|  | `SetIValue()` |  |
|  | `SetFValue()` |  |
|  | `SetStep()` |  |
|  | `GetInvert()` |  |
|  | `SetInvert()` |  |
|  | `SetOptIBounds()` |  |
|  | `SetOptFBounds()` |  |
|  | `SetCurrentValue()` |  |