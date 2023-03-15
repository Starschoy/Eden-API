# Notes
A lot of these functions are derived from imGUI Minion. Every GUI Function thats in minion is also in Eden. For example:
```lua
GUI:BeginGroup()
-- is the same as --
Eden:BeginGroup()
```
Basic things that didn't need improvement such as `GUI:BeginGroup()` or `GUI:SetCursorPos()` is not listed in this documentation because I saw no reason for improvement, so I just added function aliasing.

# Table of Contents
- [`Window Functions`](#window-functions)
- [`Main Widgets`](#main-widgets)
- [`Widget Drags`](#widget-drags)
- [`Widgets Input`](#widgets-input)
- [`Widgets Trees`](#widgets-trees)
- [`Widgets Lists`](#widgets-lists)
- [`Widgets Tooltips`](#widgets-tooltips)
- [`Widgets Popups`](#widgets-popups)
- [`Widgets Utilities`](#widgets-utilities)

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

- ## `Eden:EndWindow()`
  The main call to end a window. this must be used whenever you start a new window using Eden:StartWindow().
  ### Usage
  ```lua
  local MainWindow = Eden:StartWindow("My Window", 120, 120)
  --Your window widgets in here--
  Eden:EndWindow()
  ```
  
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

- ## Eden:BeginChild(Title, SizeX, SizeY, [Padding], [Color])
  Edens variant of the BeginChild 
  ### Parameters
  - `Title` (string): The title of your child window.
  - `SizeX, SizeY` (int): The size of your child region.
  - `[Padding]` (int): The padding of the child window.
  - `[Color]` (string): #color of your child background
  ### Usage
  ```lua
    Eden:StartWindow(400,200, "My Title")
        GUI:SetCursorPosX(GUI:GetCursorPosX()+10)
        Eden:BeginChild("hello", 120, 120, 25)
        GUI:SetCursorPosY(GUI:GetCursorPosY()+15)
        Eden:Text("This is a child region",0.5,"center")
        Eden:EndChild()
    Eden:EndWindow()
  ```
  This would render:<br>
  ![image](https://user-images.githubusercontent.com/86452536/225285237-07405388-e9e7-4c43-8b1d-85d9e86b5c4c.png)
  ### Notes
  - Child window opacity not able to be edited currently, will figure out a better way to do this later.
- ## `Eden:EndChild()`
  Ends the current child window.
  
# Main Widgets
- ## `Eden:Text(str, font_size, [alignment])`
  This function works differently than minions in that it uses a .png font atlas to render text on the screen. This means you can't use regular text widgets like GUI:CalcTextSize().
  
  ### Parameters
  - `str` (string): The text you want to be printed
  - `font_size` (int): ((MULTIPLIER)) The size of the text you want to be rendered.
  - `[alignment]` (string): The alignment of the text you render. Can be aligned `"left"`, `"center"`, or `"right"`. 
  
  ### Usage
  ```lua
  GUI:Text("Hello World!", 1, "center")
  ```
  This bit would render: <br>
  ![image](https://user-images.githubusercontent.com/86452536/225076493-c73b0eaa-e791-4f4e-a5bc-ab95ab4db706.png)

  ### Notes
  - The font atlas .png has characters at 48px, meaning any size higher than 1 will likely result in blurry/pixelated text.
  - Only default ascii is currently supported, with plans to implement other things like Bold & Italics.
  - Has automatic text wrapping if the next word can't fit in the remaining X space in the window. 
  
---

# Widget Drags

# Widgets Input

# Widgets Sliders

# Widgets Trees

# Widgets Lists

# Widgets Tooltips

# Widgets Menus

# Widgets Popups

# Widgets Utilities

- ## `Eden:CalcTextWidth(text, font_size)`
  Function to calculate the width of text. Useful for aligning against something.
  
  ### Parameters
  - `text` (string): The text you want to calculate
  - `font_size` (int): The font_size of your text.
  
  ## Usage
  ```lua
  local getTextWidth = Eden:CalcTextWidth("Hello World!", 0.4)
  d(getTextWidth) -- Will return 105.2
  ```
  
# Widgets Keybinds
