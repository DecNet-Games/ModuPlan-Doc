---
title: Unified Multi-Input System
parent: Features
layout: default
---

# Unified Multi-Input System

ModuPlan Pro leverages the new Unity Input System by distributing an optimized InputActionAsset globally.
Through this architecture, it handles device polling implicitly across three main hardware boundaries seamlessly.

## 1. Interaction Mapping
Binding logic spans standard input listeners without custom Editor Windows for maximum compatibility. Out of the box, `InteractionManager.cs` detects context mapping:

[Keyboard / Mouse]
- Left Click vs Right Click
- Screen vs World UI Priority

[Gamepad / Joystick]
- Configured generic USB controllers
- Analog interpolation

## 2. Event Interception
Because we inject the `InputSystemUIInputModule` procedurally, `AppManager` resolves event listeners for UI interactions before normal Raycast blockers typically trigger faults.

## Deep Technical Detail: Action Map Isolation
We strictly enforce a separation between **Player Movement** vs **Interaction** Action Maps inside the DemoInput asset:

```csharp
// AppManager.cs automatically routes this to prevent logic conflicts:
var playerInput = playerObj.GetComponent<PlayerInput>();
playerInput.SwitchCurrentActionMap("Player");

var intInput = interactionObj.AddComponent<PlayerInput>();
intInput.defaultActionMap = "Interaction";
```

This ensures moving the camera doesn't accidentally submit an unwanted "Interact" command in a clustered Canvas environment.
