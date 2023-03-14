# About
EDEN is a user interface framework based on ImGUI, designed to streamline the creation and management of graphical user interfaces. It operates similarly to popular web page frameworks like Bootstrap and Materialize, making it an efficient tool for creating visually appealing and user-friendly interfaces.
<br>

# Table of Contents

- ## [Eden-API](#eden-api-documentation)
  - ### [`Window Functions`](#window-functions)

# Eden API Documentation

## Window Functions

- ### `Eden:StartWindow(Title, SizeX, SizeY, Flags)`
    The main call to a window. Eden:EndWindow() must be used to close it.

    ### Parameters:
    - `Title` (string): The title of your window.
    - `SizeX, SizeY` (number): The width & height of the window.
    - <s><u>`Flags`</u> (table): A table of flags you want to pass to the window. </s> Not Implemented Yet

    ### Notes
    - Every StartWindow must have an EndWindow to compliment it. 
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
    ![](2023-03-14-05-35-27.png)

    ### Usage

    ```lua
        local MainWindow = Eden:StartWindow("Hello World!", 120, 120)
        Eden:Text("Hello World!", 0.3, "center")
        Eden:EndWindow()
- ### `Eden:EndWindow()`
    Closes the last window.



<br>

---

## Widgets Main

- ### `Eden:Text(str, font_size, alignment)`
    This creates a text element with varying font size and alignment options. Colored text & Bold/Italics are coming soon.

    ### Parameters
    - `str` (string): The text you want to be displayed.
    - <u>`font_size`</u> (int): The font size (multiplier).
    - <u>`alignment`</u> (string): The alignment of the text in the current window/child window. Options are:
      1. `"left"`
      2. `"center"`
      3. `"right"` 
   ### Notes
    - Default text size is 1, which is very large by default. If you want a smaller text, you'll have to use a number less than 1.

    ### Usage
    ```lua
    Eden:Text("Hello World!", 0.3, "center")
    ```



---


<br>
<br>
<br>
<br>
<br>

# Error Documentation

## `Error 100: Font data table not found.`
This means that the API cannot find the font_data table. Currently, it's not possible to get this error becaise I currently do not support different fonts.

<br>

## `Error 101: Space character not found in font data.`
This means your Font_Data table doesn't contain a space character. It's another error that currently isn't possible because I don't support different fonts at the moment. 

## `Error 102: Character <char> not found in font data."`
This means you are trying to use an unsupported character in your font string. Custom ascii symbols are not supportd.