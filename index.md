# Obese.vip Addons Documentation

## Overview
This document provides detailed information about the custom functions, variables, and interface provided by the Obese.vip Addons library.

## Setup
Create a LUA file inside of your executors workspace > obese.vip > addons and edit it in notepad++ or visual studio code.

## Custom Functions

### `getCustomImage(URL, FileName)`
Gets an icon from a specified URL.

```lua
-- Example usage
local image = getCustomImage("http://example.com/icon.png", "icon.png")
```

**Parameters:**
- `URL`: The URL from which to download the image.
- `FileName`: The name under which the image will be saved.

### `getGameIcon(gameId)`
Gets the icon for the specified game ID.

```lua
-- Example usage
local icon = getGameIcon(123456789)
```

**Parameters:**
- `gameId`: The ID of the game whose icon is to be retrieved.

## Custom Variables

### `ObeseAddons`
The page where all addons get stored.

### `ObeseTarget`
Gets the current aim target.

## Interface

### `ObeseAddons`
The addons page where you can add sections.

#### Example

```lua
local Example = ObeseAddons:Section({Name = "This is an example addon title", Side = "left"})

Example:Toggle({Name = "Test print", Flag = "ToggleFlag1", Def = true, Callback = function(v) 
    print(v)
end})

Example:Keybind({Name = "Test Keybind", Flag = "KeybindFlag1", Default = Enum.KeyCode.J, Callback = function(v) 
    print(v)
end})

Example:Slider({Name = "Test Slider", Flag = "SliderFlag1", Suffix = " stud(s)", Min = 0, Max = 100, Default = 50, Decimals = 0.1, Callback = function(v)
    print(v)
end})

Example:Button({Name = "Text Button", Callback = function()
    print("Button clicked")
end})

Example:List({Name = "Test Dropdown", Flag = "DropdownFlag1", Options = {"1","2","3","a","b","c"}, Default = "1", CallBack = function(v)
	print(v)		
end})

Example:Textbox({Name = "Test Textbox", Flag = "TextBoxFlag1", Def = "", Callback = function(v)
    print(v)
end})
```
