---
tags:
  - Class
---
# Class "ImGui"

An example mod using the ImGui class can be found [here.](./examples/ImGuiMenu.md)

???+ info
    You can get this class by using the global table "ImGui"


    ???+ example "Example Code"
        ```lua
        local isblind = ImGui.GetVisible("braillemenu")
        ```
    ### Reference
    For element types we use the same names as in ImGui itself. Check out the **[interactive ImGui example](https://pthom.github.io/imgui_manual_online/manual/imgui_manual.html)**.
    
    ### Icons
    All imgui text supports the usage of icons. Right now, we use "FontAwesome 6", which provides ~1400 icons. You can search for fitting icons here: [https://fontawesome.com/search?o=r&m=free&s=solid](https://fontawesome.com/search?o=r&m=free&s=solid)

    **Icon usage in Lua:**

    If you want to add an Icon into your widget, just use the "Unicode" representation of the icon and put it in between a `\u{ }` string. You can find this, by selecting the icon on the fontawesome page, and looking in the top right corner of the popup-window. You can add it to your element like this:

    `"\u{f0f9} My Text"`

    This will add the "truck-medical" icon in front of the text "My text".

    Result: ":fontawesome-solid-truck-medical: My Text"


## Functions

### AddButton () {: aria-label='Functions' }
#### void AddButton ( string ParentId, string ElementId, string Label = "", function ClickCallback = nil, boolean IsSmall = false ) {: .copyable aria-label='Functions' }
## Functions
Result: ":fontawesome-solid-truck-medical: My Text"
**Icon usage in Lua:**
For element types we use the same names as in ImGui itself. Check out the **[interactive ImGui example](https://pthom.github.io/imgui_manual_online/manual/imgui_manual.html)**.
This will add the "truck-medical" icon in front of the text "My text".
All imgui text supports the usage of icons. Right now, we use "FontAwesome 6", which provides ~1400 icons. You can search for fitting icons here: [https://fontawesome.com/search?o=r&m=free&s=solid](https://fontawesome.com/search?o=r&m=free&s=solid)
`"\u{f0f9} My Text"`
If you want to add an Icon into your widget, just use the "Unicode" representation of the icon and put it in between a `\u{ }` string. You can find this, by selecting the icon on the fontawesome page, and looking in the top right corner of the popup-window. You can add it to your element like this:

### AddCallback () {: aria-label='Functions' }
#### void AddCallback ( string ElementId, [ImGuiCallback](enums/ImGuiCallback.md) Type, Function func ) {: .copyable aria-label='Functions' }
Add a callback to an ImGui-element. An element can have one callback per type.

### AddCheckbox () {: aria-label='Functions' }
#### void AddCheckbox ( string ParentId, string ElementId, string Label = "", function ChangeCallback = nil, boolean IsActive = false ) {: .copyable aria-label='Functions' }
___
### AddCombobox () {: aria-label='Functions' }
#### void AddCombobox ( string ParentId, string ElementId, string Label = "", function ChangeCallback = nil, table Options, int SelectedIndex = 0, boolean IsSlider = false ) {: .copyable aria-label='Functions' }
Adds a Combobox element which represents a single line element that allows you to select a value from a dropdown menu. If `isSlider` is set to true, instead of a dropdown menu, the values can be selected by interacting with a slider element.
```lua
???+ example "Example Code"
ImGui.AddCombobox("catInput", "combobox1", "Combobox", function(index, val) print(index, val) end, { "Item 1", "Item 2", "Item 3" }, 1)
```

### AddDragFloat () {: aria-label='Functions' }
#### void AddDragFloat ( string ParentId, string ElementId, string Label = "", function ChangeCallback = nil, float DefaultVal = 0, float Speed = 1, float Min = INTEGER_MIN, float Min = INTEGER_MAX, string Formatting = "%.3f" ) {: .copyable aria-label='Functions' }
___
### AddDragInteger () {: aria-label='Functions' }
#### void AddDragInteger ( string ParentId, string ElementId, string Label = "", function ChangeCallback = nil, int DefaultVal = 0, float Speed = 1, int Min = INTEGER_MIN, int Min = INTEGER_MAX, string Formatting = "%d%" ) {: .copyable aria-label='Functions' }
___
### AddElement () {: aria-label='Functions' }
#### void AddElement ( string ParentId, string ElementId = "", [ImGuiElement](enums/ImGuiElement.md) type, string Label = "" ) {: .copyable aria-label='Functions' }
Adds a generic element to a given parent. Useful to add control elements like "SameLine", "Bullet" or "Text".

### AddInputColor () {: aria-label='Functions' }
#### void AddInputColor ( string ParentId, string ElementId, string Label = "", function ChangeCallback = nil, float r = 0, float g = 0, float b = 0) {: .copyable aria-label='Functions' }
```lua
ImGui.AddInputColor("catInput", "inputColorRGB", "RGB input", function(r, g, b) print(r, g, b) end, 1, 0.25, 0.45)
???+ example "Example Code"
The callback gets passed the r,g,b and a values as seperate parameters.
Adds a color input element. If the parameter `a` is set, it acts as an RGBA input. Otherwise its just an RGB input. The float values are between `0` and `1`.
0.5)
ImGui.AddInputColor("catInput", "inputColorRGBA", "RGBA input", function(r, g, b, a) print(r, g, b, a) end, 0.5, 0.5, 0.5,
```

### AddInputController () {: aria-label='Functions' }
#### void AddInputController ( string ParentId, string ElementId, string ButtonLabel = "", function ChangeCallback = nil, float DefaultVal = 0 ) {: .copyable aria-label='Functions' }
The callback gets passed the [ButtonAction ID](https://wofsauge.github.io/IsaacDocs/rep/enums/ButtonAction.html) and the ImGuiKey name of the new button.
Adds an input for Gamepad / controller buttons.

### AddInputFloat () {: aria-label='Functions' }
#### void AddInputFloat ( string ParentId, string ElementId, string Label = "", function ChangeCallback = nil, float DefaultVal = 0, float Step = 1, float StepFast = 100  ) {: .copyable aria-label='Functions' }
___
### AddInputInteger () {: aria-label='Functions' }
#### void AddInputInteger ( string ParentId, string ElementId, string Label = "", function ChangeCallback = nil, int DefaultVal = 0, int Step = 1, int StepFast = 100  ) {: .copyable aria-label='Functions' }
___
### AddInputKeyboard () {: aria-label='Functions' }
#### void AddInputKeyboard ( string ParentId, string ElementId, string ButtonLabel = "", function ChangeCallback = nil, float DefaultVal = 0 ) {: .copyable aria-label='Functions' }
Adds an input for keyboard buttons.
The callback gets passed the [Keyboard key ID](https://wofsauge.github.io/IsaacDocs/rep/enums/Keyboard.html) and the ImGuiKey name of the new button.

### AddInputText () {: aria-label='Functions' }
#### void AddInputText ( string ParentId, string ElementId, string Description = "", function ChangeCallback = nil, string DefaultVal = "", string HintText = "" ) {: .copyable aria-label='Functions' }
Adds a text input element. The text from `HintText` will get displayed as a "placeholder" inside the input element, if the input of the element is empty.

### AddInputTextMultiline () {: aria-label='Functions' }
#### void AddInputTextMultiline ( string ParentId, string ElementId, string Description = "", function ChangeCallback = nil, string DefaultVal = "", float DisplayedLines = 6 ) {: .copyable aria-label='Functions' }
Adds a text input element that allows to input multiple lines of text. The attribute `displayedLines` can be used to change the height of the element.

### AddPlotHistogram () {: aria-label='Functions' }
#### void AddPlotHistogram ( string ParentId, string ElementId, string Label = "", table Values, string OverlayText = "", float Minimum = FLT_MIN, float Maximum = FLT_MAX, float Height = 40 ) {: .copyable aria-label='Functions' }
Adds a bar-diagram displaying the given data as vertical bars. On default, minimum and maximum are set "dynamicaly", making the diagram fit its content perfectly.

### AddPlotLines () {: aria-label='Functions' }
#### void AddPlotLines ( string ParentId, string ElementId, string Label = "", table Values, string OverlayText = "", float Minimum = FLT_MIN, float Maximum = FLT_MAX, float Height = 40 ) {: .copyable aria-label='Functions' }
Adds a line-diagram connecting the given values using lines. On default, minimum and maximum are set "dynamicaly", making the diagram fit its content perfectly.

### AddProgressBar () {: aria-label='Functions' }
#### void AddProgressBar ( string ParentId, string ElementId, string Label = "", float Progress = 0, string OverlayText = "__DEFAULT__" ) {: .copyable aria-label='Functions' }
Adds a progressbar element. The `progress` value defines the fill percentage (`0` to `1`).
If the `overlayText` was not defined, the progressbar will display the current fill state in percent inside the progressbar (for example 50% when progress is set to 0.5).
If the `label` is empty, the progressbar will render over the full width of the parent element.

### AddRadioButtons () {: aria-label='Functions' }
#### void AddRadioButtons ( string ParentId, string ElementId, function ChangeCallback = nil, table options, int SelectedIndex = 0, boolean renderSameLine = true ) {: .copyable aria-label='Functions' }
```lua
ImGui.AddRadioButtons("catInput", "radioButtons", function(index) print(index) end, { "Radio 1", "Radio 2", "Radio 3" }, 1)
???+ example "Example Code"
```

### AddSliderFloat () {: aria-label='Functions' }
#### void AddSliderFloat ( string ParentId, string ElementId, string Label = "", function ChangeCallback = nil, float DefaultVal = 0, float Min = INTEGER_MIN, float Max = INTEGER_MAX, string Formatting = "%.3f" ) {: .copyable aria-label='Functions' }
___
### AddSliderInteger () {: aria-label='Functions' }
#### void AddSliderInteger ( string ParentId, string ElementId, string Label = "", function ChangeCallback = nil, int DefaultVal = 0, int Min = INTEGER_MIN, int Max = INTEGER_MAX, string Formatting = "%d%" ) {: .copyable aria-label='Functions' }
___
### AddTab () {: aria-label='Functions' }
#### void AddTab ( string ParentId, string ElementId, string Label ) {: .copyable aria-label='Functions' }
The parent object needs to be a TabBar.
A tab is a clickable area that shows another page or area.

### AddTabBar () {: aria-label='Functions' }
#### void AddTabBar ( string ParentId, string ElementId ) {: .copyable aria-label='Functions' }
A TabBar is a container which is used to store Tab elements.

### AddText () {: aria-label='Functions' }
#### void AddText ( string ParentId, string Text, boolean WrapText = false, string ElementId = "" ) {: .copyable aria-label='Functions' }
The ElementId can be set as well, if the text should be able to be edited by later code.
Creates a text element. If `wrapText` is set to `true`, the text will wrap on the window borders. If set to `false` it will expand the window content till it fits.

### CreateMenu () {: aria-label='Functions' }
#### void CreateMenu ( string ElementId, string Label = "" ) {: .copyable aria-label='Functions' }
Creates an entry to the main menu bar of Repentogon.

### CreateWindow () {: aria-label='Functions' }
#### void CreateWindow ( string ElementId, string Title = "" ) {: .copyable aria-label='Functions' }
Creates a window object. You need to use `LinkWindowToElement()` or `SetVisible()` to toggle the visibility of the window.

### ElementExists () {: aria-label='Functions' }
#### boolean ElementExists ( string ElementId ) {: .copyable aria-label='Functions' }
Returns true if an element with the given ID exists already.

### GetMousePosition () {: aria-label='Functions' }
#### void GetMousePosition ( ) {: .copyable aria-label='Functions' }
Returns the mouse position in Screen coordinates.
Use this instead of `Input.GetMousePosition()` when working with imgui!

### GetVisible () {: aria-label='Functions' }
#### boolean GetVisible ( string ElementId ) {: .copyable aria-label='Functions' }
Get if a window element is visible or not.

### GetWindowPinned () {: aria-label='Functions' }
#### boolean GetWindowPinned ( string WindowId ) {: .copyable aria-label='Functions' }
Get the pinned state of a window.

### Hide () {: aria-label='Functions' }
#### void Hide ( ) {: .copyable aria-label='Functions' }
Closes ImGui.

### ImGuiToWorld () {: aria-label='Functions' }
#### void ImGuiToWorld ( [Vector](Vector.md) Position ) {: .copyable aria-label='Functions' }
Converts ImGui coordinates into World coordinates.
???+ bug "Bug"
This function does not work correctly when the game's scale factor exceeds MaxRenderScale.

### IsVisible () {: aria-label='Functions' }
#### boolean IsVisible ( ) {: .copyable aria-label='Functions' }
Called when the player is actively in ImGui. This isn't triggered by "pinned" windows.

### LinkWindowToElement () {: aria-label='Functions' }
#### void LinkWindowToElement ( string WindowId, string ElementId ) {: .copyable aria-label='Functions' }
ImGui.CreateMenu("myMenu", "Test Menu")
this code creates a new menu entry with one menuitem, which on click toggles a window
ImGui.CreateWindow("myWindow", "Some Window title")
ImGui.AddElement("myMenu", "myButton", ImGuiElement.MenuItem, "Some Text")
```lua
Connects a Window or Popup element to another element, making said element act as a "toggle" for that window.
ImGui.LinkWindowToElement("myWindow", "myButton")
???- example "Example Code"
```

### PushNotification () {: aria-label='Functions' }
#### void PushNotification ( string Text, [ImGuiNotificationType](enums/ImGuiNotificationType.md) notificationType = 0, int lifetime = 5000 ) {: .copyable aria-label='Functions' }        
Displays a pop-up message window in the style of a notification.

### RemoveCallback () {: aria-label='Functions' }
#### void RemoveCallback ( string ElementId, [ImGuiCallback](enums/ImGuiCallback.md) type ) {: .copyable aria-label='Functions' }
Remove the callback of the given type from the element.

### RemoveColor () {: aria-label='Functions' }
#### void RemoveColor ( string ElementId, [ImGuiColor](enums/ImGuiColor.md) colorType ) {: .copyable aria-label='Functions' }
Remove a color modifier of the given type from the element.

### RemoveElement () {: aria-label='Functions' }
#### void RemoveElement ( string ElementId ) {: .copyable aria-label='Functions' }
General function to remove any kind of element.

### RemoveMenu () {: aria-label='Functions' }
#### void RemoveMenu ( string ElementId ) {: .copyable aria-label='Functions' }

___
### RemoveWindow () {: aria-label='Functions' }
#### void RemoveWindow ( string ElementId ) {: .copyable aria-label='Functions' }

___
### Reset () {: aria-label='Functions' }
#### void Reset ( ) {: .copyable aria-label='Functions' }
Removes all custom defined Imgui elements and resets imgui back to its original state.

### SetColor () {: aria-label='Functions' }
#### void SetColor ( string ElementId, [ImGuiColor](enums/ImGuiColor.md) ColorType, float r, float g, float b, float a = 1.0 ) {: .copyable aria-label='Functions' }
Adds a color modifier to a given element.

### SetHelpmarker () {: aria-label='Functions' }
#### void SetHelpmarker ( string ElementId, string Text ) {: .copyable aria-label='Functions' }
Adds a helpmarker to a given element. A Helpmarker is a `(?)` element rendered on the right of an element, which when hovered displays a tooltip.

### SetTextColor () {: aria-label='Functions' }
#### void SetTextColor ( string ElementId, float r, float g, float b, float a = 1.0 ) {: .copyable aria-label='Functions' }
Shortcut function to add a color modifier to text of a given element.

### SetTooltip () {: aria-label='Functions' }
#### void SetTooltip ( string ElementId, string Text ) {: .copyable aria-label='Functions' }
Adds a tooltip to a given element. The tooltip is visible when the user hovers over the element.

### SetVisible () {: aria-label='Functions' }
#### void SetVisible ( string ElementId, boolean Visible ) {: .copyable aria-label='Functions' }

___
### SetWindowPinned () {: aria-label='Functions' }
#### void SetWindowPinned ( string WindowId, boolean Pinned ) {: .copyable aria-label='Functions' }
Set the pinned state of a window, making it visible when the ImGui interface is not active.

### SetWindowPosition () {: aria-label='Functions' }
#### void SetWindowPosition ( string WindowId, float x, float y ) {: .copyable aria-label='Functions' }
Set the position of a window in screen coordinates.

### SetWindowSize () {: aria-label='Functions' }
#### void SetWindowSize ( string WindowId, float width, float Height ) {: .copyable aria-label='Functions' }
Set the width and height of a window, in pixels.

### Show () {: aria-label='Functions' }
#### void Show ( ) {: .copyable aria-label='Functions' }
Opens ImGui.

### UpdateData () {: aria-label='Functions' }
#### void UpdateData ( string ElementId, [ImGuiData](enums/ImGuiData.md) DataType, int NewDataValue ) {: .copyable aria-label='Functions' }
Update arbitrary data of a given element. See [ImGuiData](enums/ImGuiData.md) for possible data to update.
The dataTypes and the expected NewDataValue are evaluated per element. Therefore, if you try to update data of an element where this data is not used, this function will throw an error for you.

### UpdateText () {: aria-label='Functions' }
#### void UpdateText ( string ElementId, string Text ) {: .copyable aria-label='Functions' }
Shortcut function to update an element text or label.

### WorldToImGui () {: aria-label='Functions' }
#### void WorldToImGui ( [Vector](Vector.md) Position ) {: .copyable aria-label='Functions' }
???+ bug "Bug"
This function does not work correctly when the game's scale factor exceeds MaxRenderScale.
Converts world coordinates into ImGui coordinates.
