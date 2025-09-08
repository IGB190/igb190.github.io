---
title: Gold Pickup
layout: default
parent: Code Documentation
---



# The GoldPickup Class
{: .no_toc }
The GoldPickup class is used to control the generation of gold pickups.

![Image of the Monster Attributes](../assets/gold-pickup-1.jpg)

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

## Placing a Gold Pickup in the World
In the base project, you can find the Gold Pickup prefab under `Assets > Assets to Use > GoldPickup`. 

Drag this prefab into the environment and place it where you want it. In the inspector, you can then choose the amount of gold that the pickup should have, and the radius at which the gold should be picked up.

## Spawning an Gold Pickup
```csharp
// Spawn a gold pickup at the player's location.
GoldPickup.Spawn(GameManager.player.transform.position, 500);
```

## Destroying an Gold Pickup
Gold Pickups are standard prefabs of standard Unity GameObjects. To Destroy an GoldPickup object, just call `Destroy()` with the GameObject as a parameter.