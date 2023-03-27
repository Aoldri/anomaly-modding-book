# Layout

## Scrollable Window
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

## Frame Window
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
