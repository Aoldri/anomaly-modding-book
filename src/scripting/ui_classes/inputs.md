# Inputs

- [Button](#button)
- [Checkbox](#checkbox)
- [Combobox](#combobox)
- [Listbox](#listbox)
- [Text Field](#text-field)
- [Slider](#slider)

## Button

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
| `frame_mode` | `0` | `0`\|`1` | Initialises and attaches a [Frame Line Window](undocumented.md#frame-line-window) to the button. |
| `vertical` | `0` | `0`\|`1` | ??? |
| `hint` |  | `string` | Displays translated text when the mouse cursor hovers over the button. |

Child Elements:
- [`<texture>`](subelements.md#texture): Texture of button, requires variants with the suffixes `_e`, `_d`, `_t`, `_h` for enabled, disabled, touched, and highlighted states respectively.
- [`<text>`](subelements.md#text): String ID to display localised text
- `<text_color>`
  - [`<e>`](subelements.md#colour): Colour of text when the button is enabled
  - [`<d>`](subelements.md#colour): Colour of text when the button is disabled
  - [`<t>`](subelements.md#colour): Colour of text when the button is touched
  - [`<h>`](subelements.md#colour): Colour of text when the button is highlighted

Lua:
```lua
local xml = CScriptXmlInit()
xml:Init3tButton("button", self)
```

## Checkbox

> CUICheckButton : [CUI3tButton](#button)

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
|  |  |  |  |

Child Elements:
- [`<texture>`](subelements.md#texture): Texture of checkbox, defaults to `ui_checker`
- `<text_color>`
  - [`<e>`](subelements.md#colour): Colour of text when the button is enabled
  - [`<d>`](subelements.md#colour): Colour of text when the button is disabled
  - [`<t>`](subelements.md#colour): Colour of text when the button is touched
  - [`<h>`](subelements.md#colour): Colour of text when the button is highlighted

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitCheck("button", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
| `boolean` | `GetCheck()` | Returns `true` if the checkbox is checked.   | 
|  | `SetCheck(ch: boolean)` | Checks the checkbox if `ch` is `true`, and unchecks if it is `false`.  | 
|  | `SetDependControl(pWnd: CUIWindow)` | Enables or disables `pWnd` depending on if the checkbox is checked or unchecked respectively. | 

## Combobox

> CUIComboBox : [CUIWindow](layouts.md#window)

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
| `list_length` | `4` | `number` | Determines length of the list displayed after clicking. |
| `always_show_scroll` | `1` | `0`\|`1` | If set to `1`, the scroll bar is always visible even if scrolling is not needed. |

Child Elements:
- [`<list_font>`](subelements.md#font): Determines the [font](subelements.md#font) and [colour](subelements.md#colour) of the list
- `<text_color>`
  - [`<e>`](subelements.md#colour): Colour of text when the item is enabled
  - [`<d>`](subelements.md#colour): Colour of text when the item is disabled

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

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `item_height` | 20.0 | `number` | Determines the height of each item in the list box. |

Child Elements:
- [`<font>`](subelements.md#font): Determines the [font](subelements.md#font) and [colour](subelements.md#colour) of the text

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitListBox("listbox", self)
```

| Returns | Method | Description |
| --- | --- | --- |
|  | `ShowSelectedItem()` | Displays the currently selected item in the list box. |
|  | `RemoveAll()` | Removes all items from the list box. |
| `number` | `GetSize()` | Returns the number of items in the list box. |
| `CUIListBoxItem` | `GetSelectedItem()` | Returns the currently selected item in the list box. |
| `number` | `GetSelectedIndex()` | Returns the index of the currently selected item in the list box. |
|  | `SetSelectedIndex(index: number)` | Sets the currently selected item in the list box to the item at the specified index. |
|  | `SetItemHeight(height: number)` | Sets the height of each item in the list box. |
| `number` | `GetItemHeight()` | Returns the height of each item in the list box. |
| `CUIListBoxItem` | `GetItemByIndex()` | Returns the item at the specified index in the list box. |
| `CUIListBoxItem` | `GetItem()` | Returns the item with the specified text in the list box. |
|  | `RemoveItem()` | Removes the specified item from the list box. |
| `CUIListBoxItem` | `AddTextItem(text: string)` | Adds a new item with the specified text to the list box. |
|  | `AddExistingItem(item: CUIListBoxItem)` | Adds an existing item to the list box. |

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

Child Elements:
- [`<texture>`](subelements.md#texture)
- `<text_color>`
  - [`<e>`](subelements.md#colour): Text colour

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitEditBox("input", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
|  | `SetText(str: string)` | Sets the text of the text field to the specified string. |
| `string` | `GetText()` | Returns the current text in the text field as a string. |
|  | `CaptureFocus(bCapture: boolean)` | Captures or releases focus for the text field. When focus is captured, the text field receives all keyboard input until focus is released. |
|  | `SetNextFocusCapturer(next_capturer: CUICustomEdit)` | Sets the next UI element that will capture focus after this text field. |
|  | `InitTexture(texture: string)` | Initializes the texture used for rendering the text field. |

## Slider

> CUITrackBar : [CUIWindow](layouts.md#window)

XML:
```xml
<trackbar x="64" y="4" width="140" height="16" stretch="1"/>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `is_integer` | `0` | `0`\|`1` |  |
| `invert` | `0` | `0`\|`1` |  |
| `step` | 0.1 | `number` |  |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitTrackBar("trackbar", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
| `boolean` | `GetCheck()` | Returns `true` if the slider is checked; otherwise, returns `false`. |
|  | `SetCheck(b: boolean)` | Sets the slider check state to `true` if b is `true`; otherwise, sets it to `false`. |
| `number` | `GetIValue()` | Returns the integer value of the slider. |
| `number` | `GetFValue()` | Returns the floating-point value of the slider. |
|  | `SetIValue(i: number)` | Sets the integer value of the slider to `i`. |
|  | `SetFValue(f: number)` | Sets the floating-point value of the slider to `f`. |
|  | `SetStep(step: number)` | Sets the step increment of the slider to `step`. |
| `boolean` | `GetInvert()` | Returns `true` if the slider is inverted; otherwise, returns `false`. |
|  | `SetInvert(v: boolean)` | Sets the slider to be inverted if `v` is `true`; otherwise, sets it to be normal. |
|  | `SetOptIBounds(imin: number, imax: number)` | Sets the integer bounds of the slider to `imin` and `imax`. |
|  | `SetOptFBounds(fmin: number, fmax: number)` | Sets the floating-point bounds of the slider to `fmin` and `fmax`. |
|  | `SetCurrentValue()` | Sets the current value of the slider based on its position. |