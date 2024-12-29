# Sprite Module Documentation

## Overview
This module provides functions to create and manage visual elements like frames, images, and texts within the user interface in Roblox Studio.

## Functions

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
local frame = Sprite:CreateFrame("ExampleFrame", Color3.fromRGB(255, 0, 0), 0, UDim2.new(0, 100, 0, 100), UDim2.new(0, 200, 0, 200), 1, "MainGui")
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
local image = Sprite:CreateImage("ExampleImage", "10006333293", Color3.fromRGB(255, 255, 255), UDim2.new(0, 50, 0, 50), UDim2.new(0, 100, 0, 100), 1, "MainGui", Vector2.new(0.5, 0.5), 0)
```
