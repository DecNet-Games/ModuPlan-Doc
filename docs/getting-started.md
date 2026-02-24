---
title: Getting Started
layout: default
nav_order: 3
---

# Getting Started with ModuPlan Pro

Welcome aboard! ModuPlan Pro is designed to get out of your way and let you build features. 

To prove it, here's the "Hello World" setup exactly as it runs in the included Demo scene.

## 1. The Core Architecture

The entire system rotates around the `AppManager`. But you don't even have to place it! 
Just attach the `ModuPlane` component to **any GameObject in your scene**.

```csharp
using UnityEngine;
using MultiInputDemo.Scripts.Core;

namespace MultiInputDemo.Scripts
{
    /// <summary>
    /// Attach this component to any GameObject to enable ModuPlane systems in this scene.
    /// This acts as the entry point for the AppManager.
    /// </summary>
    public class ModuPlane : MonoBehaviour
    {
        private void Awake()
        {
            // Ensure AppManager exists and is running
            AppManager.EnsureInstance();
        }
    }
}
```

## 2. Bootstrapping the Scene

When `AppManager.EnsureInstance()` is called, it verifies that the `AppManager` exists and sets itself to `DontDestroyOnLoad`. It then subscribes to `SceneManager.sceneLoaded` to ensure that standard ModuPlan configurations are present upon any newly loaded scene:

1. **Environment Initialization:** Automatically generates a `WorldPlane` and global lighting if none exist.
2. **Screen UI Generation:** Whips up standard procedural Canvas environments.
3. **World UI Generation:** Attaches procedurally generated world-space Canvas elements to the `WorldPlane`.
4. **Player Initialization:** Instantiates a camera-rigged player prefab alongside the generated Input Actions mapping.
5. **Interaction Initialization:** Prepares the `InteractionManager` and Input System's `InputSystemUIInputModule` logic out of the box.

## Next Steps
Now that your scene is bootstrapped and your UI generated automatically, dive into the [Features section]({{ site.baseurl }}/docs/features/) to learn more about dynamic resizing handles and procedural generation.
