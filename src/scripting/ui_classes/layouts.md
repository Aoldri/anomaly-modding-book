# Layout

- [Window](#window)
- [Scrollable Window](#scrollable-window)
- [Frame Window](#frame-window)

## Window

> class CUIWindow


## Scrollable Window

> CUIScrollView : [CUIWindow](#window)

XML:
```xml
<tag_select_scroll x="4" y="4" width="120" height="193" stretch="1" complex_desc="0"/>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitScrollView("tag_select_scroll", self)
```


## Frame Window

> CUIFrameWindow : [CUIWindow](#window)

XML:
```xml
<background x="326" y="256" width="370" height="265" stretch="1">
    <texture>ui_inGame2_hint_wnd_main_window</texture>
</background>
```

Attributes:

| Name | Default | Type | Description |
| --- | --- | --- | --- |
|  |  |  |  |

Lua:
```lua
local xml = CScriptXmlInit()
xml:InitFrame("background", self)
```

