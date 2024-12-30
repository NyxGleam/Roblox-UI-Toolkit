# Sprite Module Documentation

## Overview
This module provides functions to create and manage visual elements like frames, images, and texts within the user interface in Roblox Studio.

## Functions

# Setup

To use the **Sprite** module in your Roblox project, follow these steps:

### 1. File Structure

Make sure your file structure in Roblox Studio is as follows:

- **`StarterGui`**: The folder that should contain the module.
- **`Roblox-UI-Toolkit`**: The folder where your `SpriteManager.lua` (the `ModuleScript`) is located.
- **`SpriteManager.lua`**: The file containing the logic for the `Sprite` module.

### 2. Import the Module in Your Script

To use the `Sprite` module in your scripts, simply import the `ModuleScript` like this:

```lua
local Sprite = require(game.StarterGui["Roblox-UI-Toolkit"].SpriteManager)
```

This code will allow you to access the functions of the `Sprite module` from any other script in your game.

### 3. Basic Usage
Once you've imported the module, you can use the functions it provides. For example, to create a frame:

```lua
local Sprite = require(game.StarterGui["Roblox-UI-Toolkit"].SpriteManager)

Sprite:CreateFrame(
    "ExampleFrame",           -- NameId
    Color3.fromRGB(255, 0, 0), -- Color
    0,                         -- BackgroundTransparency
    UDim2.new(0, 100, 0, 100), -- Position
    UDim2.new(0, 200, 0, 200), -- Size
    1,                         -- ZIndex
    "Sprites"                  -- Parent
)
```

You can also make animations too:

```lua
local Sprite = require(game.StarterGui["Roblox-UI-Toolkit"].SpriteManager)

Sprite:CreateFrame(
	"ExampleFrame",            -- NameId
	Color3.fromRGB(255, 0, 0), -- Color
	0,                         -- BackgroundTransparency
	UDim2.fromScale(0.5, 0.25),-- Position
	Vector2.new(0.5, 0.5),	   -- AnchorPoint
	UDim2.fromOffset(150, 150),-- Size
	1,                         -- ZIndex
	"MainGui"                  -- Parent
)

Sprite:Move(
	"ExampleFrame",            -- NameId
	UDim2.fromScale(0.5, 0.25),-- OldPosition
	UDim2.fromScale(0.5, 0.75),-- NewPosition
	true,                      -- IsSmooth
	1,                         -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,     -- EasingStyle
	"MainGui"                  -- Location
)

Sprite:Scale(
	"ExampleFrame",            -- NameId
	UDim2.fromOffset(150, 150),-- OldSize
	UDim2.fromOffset(250, 250),-- NewSize
	true,			   -- IsSmooth
	1,			   -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,	   -- EasingStyle
	"MainGui"		   -- Location
)

Sprite:Rotate(
	"ExampleFrame",            -- NameId
	0, 			   -- OldRotation
	180, 			   -- NewRotation
	true,			   -- IsSmooth
	1,			   -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,	   -- EasingStyle
	"MainGui"		   -- Location
)

task.wait(2)

Sprite:Move(
	"ExampleFrame",            -- NameId
	UDim2.fromScale(0.5, 0.75),-- OldPosition
	UDim2.fromScale(0.5, 0.25),-- NewPosition
	true,			   -- IsSmooth
	1,		           -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,	   -- EasingStyle
	"MainGui"		   -- Location
)

Sprite:Scale(
	"ExampleFrame",            -- NameId
	UDim2.fromOffset(250, 250),-- OldSize
	UDim2.fromOffset(150, 150),-- NewSize
	true,			   -- IsSmooth
	1,			   -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,	   -- EasingStyle
	"MainGui"		   -- Location
)

Sprite:Rotate(
	"ExampleFrame",            -- NameId
	180, 			   -- OldRotation
	0, 			   -- NewRotation
	true,			   -- IsSmooth
	1,			   -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,	   -- EasingStyle
	"MainGui"		   -- Location
)
```

### `Sprite:CreateFrame`
The `CreateFrame` function allows you to create a `Frame` element within the UI, customizable with various properties like color, position, size, and Z-index.

#### Parameters:
- `NameId` (string): The name of the frame.
- `Color` (Color3): The color of the frame.
- `BackgroundTransparency` (number): The transparency of the frame’s background (0 is fully opaque, 1 is fully transparent).
- `Position` (UDim2): The position of the frame in the UI.
- `Size` (UDim2): The size of the frame.
- `ZIndex` (number): The Z-index determines the layering of the frame (higher value is on top).
- `Parent` (string): The name of the parent object (UI element) where the frame will be placed.

**Returns**: A `Frame` object with the specified properties.

#### Example:
```lua
Sprite:CreateFrame("ExampleFrame", Color3.fromRGB(255, 255, 255), 0, UDim2.new(0.5, 0, 0.5, 0), UDim2.new(0, 200, 0, 200), 1, "MainGui")
```

#### Explanation:
The `CreateFrame` function creates a customizable `Frame` element in the UI. It allows you to adjust the frame’s color, size, position, transparency, and layering. This function is useful for creating static or dynamic UI elements that serve as containers or backgrounds for other elements.

---

### `Sprite:CreateImage`
The `CreateImage` function allows you to create an image label (`ImageLabel`) within the UI, with customizable properties such as image asset, position, size, and more.

#### Parameters:
- `NameId` (string): The name of the image.
- `ImageId` (string): The asset ID of the image.
- `Color` (Color3): The color of the image.
- `Position` (UDim2): The position of the image in the UI.
- `Size` (UDim2): The size of the image.
- `ZIndex` (number): The Z-index determines the layering of the image (higher value is on top).
- `Parent` (string): The name of the parent object (UI element) where the image will be placed.
- `AnchorPoint` (Vector2): The anchor point of the image. This determines the point of the image used for positioning.
- `Transparency` (number): The transparency of the image (from 0 to 1, where 0 is fully opaque and 1 is fully transparent).

**Returns**: An `ImageLabel` object with the specified properties.

#### Example:
```lua
Sprite:CreateImage("ExampleImage", "10006333293", Color3.fromRGB(255, 255, 255), UDim2.new(0, 50, 0, 50), UDim2.new(0, 100, 0, 100), 1, "MainGui")
```

#### Explanation:
The `CreateImage` function creates an `ImageLabel` element within the UI, with properties to control its image, position, size, transparency, and layering. You can use this function to display images or icons in your UI, as well as customize their appearance to fit your game's design.

### `Sprite:CreateText`
The `CreateText` function allows you to create a `TextLabel` element with customizable text properties such as color, font style, size, position, shadow, and more.

#### Parameters:
- `NameId` (string): The name of the text label.
- `Text` (string): The text to display in the `TextLabel`.
- `TextColor3` (Color3): The color of the text.
- `FontStyle` (Enum.Font): The font style to use for the text.
- `TextXAlignment` (Enum.TextXAlignment): The horizontal alignment of the text.
- `Alpha` (number): The opacity of the text (from 0 to 1, where 0 is fully transparent and 1 is fully opaque).
- `Size` (UDim2): The size of the `TextLabel`.
- `Position` (UDim2): The position of the `TextLabel` in the UI.
- `AnchorPoint` (Vector2): The anchor point of the `TextLabel`. This determines the point of the `TextLabel` used for positioning.
- `HasShadow` (boolean): Whether to add a shadow effect to the text.
- `ShadowColor3` (Color3): The color of the shadow.
- `ShadowAlpha` (number): The opacity of the shadow (from 0 to 1).
- `ShadowPosition` (UDim2): The position of the shadow relative to the text.
- `ZIndex` (number): The Z-index determines the layering of the text (higher value is on top).
- `WriteSpeed` (number): The speed at which the text is typed out, in seconds per character. Set to 0 to display all text instantly.
- `Parent` (string): The name of the parent object (UI element) where the `TextLabel` will be placed.

**Returns**: A `TextLabel` object with the specified text and properties.

---

#### **Example**:
```lua
Sprite:CreateText("ExampleText", "This is an example text with cool-looking design", Color3.fromRGB(255, 255, 255), Enum.Font.FredokaOne, Enum.TextXAlignment.Center, 1, UDim2.new(1, 0, 0.2, 0), UDim2.new(0.5, 0, 0.8, 0), Vector2.new(0.5, 0.5), true, Color3.fromRGB(25, 25, 25), 0.3, UDim2.new(0.51, 0, 0.82, 0), 1, 0.05, "MainGui")
```

---

#### **Explanation**:
The `CreateText` function creates a dynamic `TextLabel` element that can be customized for various UI effects in Roblox. It allows you to manipulate text properties, including positioning, size, font, shadow, and more. 

- **Text Color**: The `TextColor3` parameter defines the color of the text, while the shadow color can be customized via the `ShadowColor3` parameter.
- **Shadow Effect**:
    - If `HasShadow` is set to `true`, a shadow will be added to the text label. The shadow's appearance is influenced by the `ShadowColor3`, `ShadowAlpha`, and `ShadowPosition` parameters.
    - If `HasShadow` is set to `false`, the shadow-related parameters (`ShadowColor3`, `ShadowAlpha`, and `ShadowPosition`) are ignored. These parameters should still be defined for consistency, even when shadows are not applied.
- **Typing Effect**: The `WriteSpeed` parameter controls how quickly the text is revealed. A `WriteSpeed` of 0 will display all text instantly, while a higher value (in seconds) will simulate a typing effect.

This function is ideal for adding rich, animated text effects to Roblox games, with complete control over text appearance and timing.

### FAQ

Q: Why isn’t the frame showing up in my GUI?
A: Make sure you have at least one `ScreenGui` | Make sure the `Location` value is not empty.

Q: How do I change the color of a frame?
A: You can use the Color3.fromRGB(r, g, b) method to change the color of your frame, where r, g, and b are values between 0 and 255.
