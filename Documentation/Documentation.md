# Notes
A lot of these functions are derived from imGUI Minion. Every GUI Function thats in minion is also in Eden. For example:
```lua
GUI:BeginGroup()
-- is the same as --
Eden:BeginGroup()
```
Basic things that didn't need improvement such as `GUI:BeginGroup()` or `GUI:SetCursorPos()` is not listed in this documentation because I saw no reason for improvement, so I just added function aliasing.

Any function parameter that has brackets is an optional argument, meaning you don't have to pass anything if you don't want to.


# Table of Contents
- ### [`Window Functions`](#window-functions)
- ### [`Main Widgets`](#main-widgets)
- ### [`Widget Drags`](#widget-drags)
- ### [`Widgets Input`](#widgets-input)
- ### [`Widgets Trees`](#widgets-trees)
- ### [`Widgets Lists`](#widgets-lists)
- ### [`Widgets Tooltips`](#widgets-tooltips)
- ### [`Widgets Popups`](#widgets-popups)
- ### [`Widgets Utilities`](#widgets-utilities)





# Window Functions

- ## `Eden:StartWindow(Title, SizeX, SizeY, [Color], [Opacity])`
  The main call to a window. Eden:EndWindow() must be used to close it.
  ### Parameters:
  - `Title` (string): The title of your window.
  - `SizeX, SizeY` (int): The Width & Height of your window.
  - `[Color]`(string): the background color of your window. This is in hex format, i.e. `#000000`
  - `[Opacity]`(int): The Transparency of your window background. Can be anywhere from 0-1.
  ### Usage:
  ```lua
        local MainWindow = Eden:StartWindow("Hello World!", 120, 120, "#000000", 0.3)
        Eden:Text("Hello World!", 0.3, "center")
        Eden:EndWindow()
  ```
  Would pass as: <br>
  ![image](https://user-images.githubusercontent.com/86452536/225070082-36ded147-30e9-4c75-b239-971c0b7ce01e.png)

  
  ### Notes
  - Every StartWindow must have an EndWindow to compliment it. 
  - TitleBar is not customizable <u> *for now* </u>
  - Returns a table of information:
    ```lua
    ["SizeX"] = SizeX,
    ["SizeY"] = SizeY,
    ["Title"] = Title,
    ["States"] = {
         ["Open"] = false,
         ["Visible"] = true
    }
    ```

# Main Widgets

# Widget Drags

# Widgets Input

# Widgets Sliders

# Widgets Trees

# Widgets Lists

# Widgets Tooltips

# Widgets Menus

# Widgets Popups

# Widgets Utilities

- ## `Eden:CalcTextWidth(text, font_size)
  Function to calculate the width of text. Useful for aligning against something.
  
  ### Parameters
  - `text` (string): The text you want to calculate
  - `font_size` (int): The font_size of your text.
  
  ## Usage
  ```lua
  local getTextWidth = Eden:CalcTextWidth("Hello World!", 0.4)
  d(getTextWidth) -- Will return 


# Widgets Keybinds
