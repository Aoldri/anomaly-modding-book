# Getting Started

## Writing the UI Class
```lua
-- ui_example.script
GUI = nil -- instance, don't touch

class "UIExample" (CUIScriptWnd)

function UIExample:__init() super()
    self:InitControls()
    self:InitCallBacks()
end

function UIExample:Reset()
end

function UIExample:__finalize()
end

function UIExample:InitControls()
    self:SetWndRect(Frect():set(0,0,1024,768))
    self:SetAutoDelete(true)
    
    local xml = CScriptXmlInit()
    xml:ParseFile("ui_hf_wiring.xml")
end

function UIExample:InitCallBacks()
end

function UIExample:Update()
    CUIScriptWnd.Update(self)
end

function UIExample:OnKeyboard(dik, keyboard_action)
    local res = CUIScriptWnd.OnKeyboard(self,dik,keyboard_action)
    if (res == false) then
        if keyboard_action == ui_events.WINDOW_KEY_PRESSED then
            if dik == DIK_keys.DIK_ESCAPE then
                self:Close()
            end
        end
    end
    return res
end

function UIExample:Close()
    self:HideDialog()

    Unregister_UI("UIExample")
end
```

## Displaying the UI


## Drawing elements


## Callbacks


## Best Practices

- Unregister on close

- Throttling the `Update()` function



