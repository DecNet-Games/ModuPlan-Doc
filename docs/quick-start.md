---
title: Quick Start
layout: default
nav_order: 4
---

# Quick Start Guide

Ready to get your hands dirty quickly without waiting?

Let's dive into ModuPlan Pro's built-in demo environment. This scene is fully configured to let you pilot the **Interaction Manager** through Keyboard, Gamepad, and Mouse combinations sequentially.

## 1. Entering Play Mode

Drop the `MultiInputDemo` scene into your hierarchy or attach a `ModuPlane` component to an empty GameObject in any of your existing scenes. Hit the **Play** button.

## 2. Navigating the UI

You can move your newly spawned player and interact using standard inputs:

### General Movement
- `[W][A][S][D]` or `[Left Joystick]` - Move Player
- `[Q][E]` or `[Twist Joystick]` - Rotate Player

### Interaction Mapping
Once a button is hovered or selected, try specific inputs from the robust mappings:
- `[Arrow Keys]` - Move Selected Button around the Space UI
- `[Left Click]` - Interact/Drag Button
- `[Left Drag Corner]` - Resize the Button dynamically from its relative space (All 4 corners supported).
- `[Left Drag Edge]` - Resize the Button dynamically from exact sides (Top/Bottom/Left/Right midpoints).

### Modifiers
We believe great tools offer infinite customization at the user level:
- `[Shift]` **(Hold)**: Enables Grid Snapping when Moving, Rotating, or Resizing!
- `[Ctrl]` **(Hold)**: Initiates Aspect Ratio Lock during Resize on corners.
- `[Alt]` **(Hold)**: Aspect Ratio Lock (Resize) and Rotate Selected Button depending on hover status.

## Enjoying the Show

Notice that ModuPlan Pro doesn't just manage the Input binding behind the scenes - It directly powers the Procedural UI Builder elements without you writing a single `Canvas.ForceUpdateCanvases()`.

When finished, explore the rich source code in `InteractionManager.cs` to see exactly which commands trigger the 8-handle dynamic UI elements.
