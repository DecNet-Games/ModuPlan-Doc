---
title: Advanced Dynamic Resizing
parent: Features
layout: default
---

# Advanced Dynamic Resizing

Giving players or users the ability to resize in-game UI normally requires thousands of lines of boilerplate edge detection.

ModuPlan Pro offers an **8-Handle Detection Engine** calculated dynamically.

## 4 Corners
Users can left-drag the boundaries defined at the 4 external corners. Diagonal resizing updates both Width and Height parameters synchronously.

## 4 Edges
Top-Center, Bottom-Center logic controls height boundaries only, while Middle-Left and Middle-Right adjust width. All calculations scale relative to a 20px detection zone built to avoid clipping error inside `ModuPlaneDashboard`.

## Modifiers Explained
- **Hold Shift**: Toggles a 10px structural grid snap for perfectly aligned windows.
- **Hold Ctrl/Alt**: Prevents aspect ratio distortion during corner resizing functions (ex: maintaining a 16:9 ratio while expanding diagonally).
  
> **Pro Tip:** Need to customize the grid snap? Navigate to `InteractionManager` and modify the snap resolution properties tied to keyboard modifiers!
