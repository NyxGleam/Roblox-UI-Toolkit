# Sprite Module Documentation

## Overview
This module provides functions to create and manage visual elements like frames, images, and texts within the user interface in Roblox Studio.

## Functions

### `Sprite:CreateFrame`
Creates a new frame within the user interface.

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
