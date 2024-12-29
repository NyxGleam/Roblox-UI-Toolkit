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

Or to make animations:

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
	true,					             -- IsSmooth
	1,						             -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,	   -- EasingStyle
	"MainGui"				           -- Location
)

Sprite:Rotate(
	"ExampleFrame",            -- NameId
	0, 						             -- OldRotation
	180, 					             -- NewRotation
	true,					             -- IsSmooth
	1,						             -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,	   -- EasingStyle
	"MainGui"			        	   -- Location
)

task.wait(2)

Sprite:Move(
	"ExampleFrame",            -- NameId
	UDim2.fromScale(0.5, 0.75),-- OldPosition
	UDim2.fromScale(0.5, 0.25),-- NewPosition
	true,					             -- IsSmooth
	1,						             -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,	   -- EasingStyle
	"MainGui"				           -- Location
)

Sprite:Scale(
	"ExampleFrame",            -- NameId
	UDim2.fromOffset(250, 250),-- OldSize
	UDim2.fromOffset(150, 150),-- NewSize
	true,					             -- IsSmooth
	1,						             -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,	   -- EasingStyle
	"MainGui"			        	   -- Location
)

Sprite:Rotate(
	"ExampleFrame",            -- NameId
	180, 					             -- OldRotation
	0, 						             -- NewRotation
	true,					             -- IsSmooth
	1,						             -- Time
	Enum.EasingDirection.InOut,-- EasingDirection
	Enum.EasingStyle.Quad,	   -- EasingStyle
	"MainGui"				           -- Location
)
```

### `Sprite:CreateFrame`
Creates a new frame within the UI.

**Parameters**:
- `NameId` (string)
- `Color` (Color3)
- `BackgroundTransparency` (number)
- `Position` (UDim2)
- `Size` (UDim2)
- `ZIndex` (number)
- `Parent` (string)

**Returns**: A `Frame` object.

**Example**:
```lua
Sprite:CreateFrame("ExampleFrame", Color3.fromRGB(255, 0, 0), 0, UDim2.new(0, 100, 0, 100), UDim2.new(0, 200, 0, 200), 1, "MainGui")
```

### `Sprite:CreateImage`
Creates an image label in the UI.

**Parameters**:

- `NameId` (string): The name of the image.
- `ImageId` (string): The asset ID of the image.
- `Color` (Color3): The image's color.
- `Position` (UDim2): The position of the image in the UI.
- `Size` (UDim2): The size of the image.
- `ZIndex` (number): The layer index of the image.
- `Parent` (string): The parent UI object.
- `Anchorpoint` (Vector2): The anchor point of the image.
- `Transparency` (number): The transparency of the image.
**Returns**: An `ImageLabel` object.

**Example**:
```lua
Sprite:CreateImage("ExampleImage", "10006333293", Color3.fromRGB(255, 255, 255), UDim2.new(0, 50, 0, 50), UDim2.new(0, 100, 0, 100), 1, "MainGui", Vector2.new(0.5, 0.5), 0)
```

### FAQ

Q: Why isn’t the frame showing up in my GUI?
A: Make sure you have at least one `ScreenGui` | Make sure the `Location` value is not empty.

Q: How do I change the color of a frame?
A: You can use the Color3.fromRGB(r, g, b) method to change the color of your frame, where r, g, and b are values between 0 and 255.
