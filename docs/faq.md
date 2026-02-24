---
title: FAQ
layout: default
nav_order: 6
---

# Frequently Asked Questions

**Is ModuPlan Pro compatible with the old Unity Input Manager?**

No, ModuPlan Pro requires the New Input System to fully harness proper event handling, dynamic rebinding, and the `InputSystemUIInputModule` simultaneously.

**Does this work in 2D Projects?**

Yes! While the primary demo focuses on a First-Person 3D space with a procedurally generated `WorldPlane`, the Screen UI generation completely bypasses depth constraints. The Interaction architecture functions optimally in both environments.

**How do I adjust the 8-Handle Resizing threshold limits?**

Under the hood, the UI controllers calculate the bounds relative to an edge. You can adjust the exact pixel tolerance mapping directly in `InteractionManager.cs` or visually configure boundary constraints in the generated `PanelSettings`.

**Is there a free version on GitHub?**

No, ModuPlan Pro is a premium asset that empowers your project infrastructure and saves you hours of boilerplate generation. It evaluates strictly to purchasing users generated via the [Unity Asset Store](https://assetstore.unity.com/). Only this documentation is stored here entirely for your viewing convenience.

**Why is my World UI not rendering properly over unlit shaders?**

The World Canvas operates using procedural UIElements embedded onto geometry materials out of the box. Ensure the material accepts UI shader dependencies, typically leveraging default Unlit/Transparent logic implicitly loaded during runtime. The Global Light fallback covers typical Lit interactions.
