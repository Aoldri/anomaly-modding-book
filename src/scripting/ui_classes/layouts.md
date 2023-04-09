# Layout

- [Window](#window)
- [Scrollable Window](#scrollable-window)
- [Frame Window](#frame-window)

## Window

> class CUIWindow

XML:
```xml
<window x="4" y="4" width="120" height="193" stretch="1" complex_desc="0"/>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `x` | 0 | `number` | The horizontal position of the top-left corner of the Window element in pixels. |
| `y` | 0 | `number` | The vertical position of the top-left corner of the Window element in pixels. |
| `width` | 0 | `number` | The width of the Window element in pixels. |
| `height` | 0 | `number` | The height of the Window element in pixels. |

Child Elements:
- `<window_name>`

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitWindow("window", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
|  | `AttachChild(pChild: CUIWindow)` | Attaches a child window to this window. |
|  | `DetachChild(pChild: CUIWindow)` | Detaches a child window from this window. |
|  | `SetAutoDelete(auto_delete: boolean)` | Sets whether this window should automatically delete itself when it's no longer needed. |
| `boolean` | `IsAutoDelete()` | Returns whether this window will automatically delete itself when it's no longer needed. |
| `boolean` | `IsCursorOverWindow()` | Returns whether the mouse cursor is currently over this window. |
| `number` | `FocusReceiveTime()` | Returns the time (in milliseconds) when this window last received focus. |
| `Frect` | `GetAbsoluteRect()` | Returns the absolute position and size of this window, relative to the top-left corner of the screen. |
|  | `SetWndRect(rect: Frect)` | Sets the position and size of this window. |
|  | `SetWndPos(pos: vector2)` | Sets the position of this window. |
|  | `SetWndSize(size: vector2)` | Sets the size of this window. |
| `vector2` | `GetWndPos()` | Returns the position of this window. |
| `number` | `GetWidth()` | Returns the width of this window. |
| `number` | `GetHeight()` | Returns the height of this window. |
|  | `Enable(status: boolean)` | Enables or disables this window. |
| `boolean` | `IsEnabled()` | Returns whether this window is enabled. |
|  | `Show(status: boolean)` | Shows or hides this window. |
| `boolean` | `IsShown()` | Returns whether this window is shown. |
| `string` | `WindowName()` | Returns the name of this window. |
|  | `SetWindowName(name: string)` | Sets the name of this window. |
|  | `SetPPMode()` | Enables post-processing mode for this window. This can be used to apply special effects to the window's rendering. |
|  | `ResetPPMode()` | Disables post-processing mode for this window. |

## Scrollable Window

> CUIScrollView : [CUIWindow](#window)

XML:
```xml
<tag_select_scroll x="4" y="4" width="120" height="193" stretch="1" complex_desc="0"/>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
| `right_ident` | 0.0 | `number` | The right margin of the scrolling window content area, measured in pixels. |
| `left_ident` | 0.0 | `number` | The left margin of the scrolling window content area, measured in pixels. |
| `top_indent` | 0.0 | `number` | The top margin of the scrolling window content area, measured in pixels. |
| `bottom_indent` | 0.0 | `number` | The bottom margin of the scrolling window content area, measured in pixels. |
| `vert_interval` | 0.0 | `number` | The vertical interval between child windows of the scrolling window, measured in pixels. |
| `inverse_dir` | 0 | `0`\|`1` | If set to `1`, the scrolling direction of the window is reversed. |
| `scroll_profile` | default | `string` | The scrolling behavior of the window, specified by a string value. |
| `flip_vert` | 0 | `0`\|`1` | If set to `1`, the vertical axis of the scrolling window is flipped. |
| `always_show_scroll` | 1 | `0`\|`1` | If set to `1`, the scroll bar is always visible even if scrolling is not needed. |
| `can_select` | 0 | `0`\|`1` | If set to `1`, the child windows of the scrolling window can be selected. |

Child Elements:
- [`<text>`](components.md#text): Can have multiple `<text>` elements as children to insert into the window.

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitScrollView("tag_select_scroll", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
|  | `AddWindow(pWnd: CUIWindow, auto_delete: boolean)` | Adds a child window to the Scrolling Window. If auto_delete is set to true, the window will be automatically deleted when it's detached from the Scrolling Window. |
|  | `RemoveWindow(pWnd: CUIWindow)` | Removes a child window from the Scrolling Window. |
|  | `Clear()` | Removes all child windows from the Scrolling Window. |
|  | `ScrollToBegin()` | Scrolls the window to the beginning. |
|  | `ScrollToEnd()` | Scrolls the window to the end. |
| `number` | `GetMinScrollPos()` | Returns the minimum scroll position. |
| `number` | `GetMaxScrollPos()` | Returns the maximum scroll position. |
| `number` | `GetCurrentScrollPos()` | Returns the current scroll position. |
|  | `SetFixedScrollBar(b: boolean)` | Sets whether the scrollbar is fixed in position or not. |
|  | `SetScrollPos(value: number)` | Sets the scroll position to the specified value. |

## Frame Window

> CUIFrameWindow : [CUIWindow](#window)

XML:
```xml
<background x="326" y="256" width="370" height="265" stretch="1">
    <texture>ui_inGame2_hint_wnd_main_window</texture>
</background>
```

Attributes:
Nothing unique to Frame Window.

Child Elements:
- [`<texture>`](subelements.md#texture): Texture of Frame Window, dynamically scaling to fit its dimensions

Note that this layout expects 9 variants of the provided Texture ID, each with a unique suffix to denote their respective positions in a 3x3 grid:

|  |  |  |
| --- | --- | --- |
| `_lt` | `_t` | `_rt` |
| `_l` | `_back` | `_r` |
| `_lb` | `_b` | `_rb` |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitFrame("background", self)
```

Methods:

| Returns | Method | Description |
| --- | --- | --- |
|  | `SetWidth(width: number)` | Sets the width of the window in pixels. |
|  | `SetHeight(height: number)` | Sets the height of the window in pixels. |
|  | `SetColor(color: ARGB)` | Sets the color of the window to the specified `color`. |