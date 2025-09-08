---
title: Event Nodes
layout: default
parent: Visual Coding
nav_order: 10
---

# Event Nodes
{: .no_toc }
Below is a summary of all the events in the visual scripting system, with a short summary of each and an outline of any associated preset values which will be populated from the event.

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

### Ability Events

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">When a unit begins casting this ability</summary>
> This event will only trigger if it is attached to an ability, and will only trigger for the unit that cast the ability. It will trigger when the ability **starts** casting. If you want to handle the ability cast logic, it is recommended you use the `When a unit finishes casting this ability` event instead.
>
> The event populates the following preset values:
> - **Casting Unit** (Unit): The unit that cast the ability.
> - **Ability Target Location** (Location): The location that the ability should be cast at.
> - **Target Unit** (Unit): The target unit for the ability (only exists if the ability targets a specific unit).
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">When a unit finishes casting this ability</summary>
> This event will only trigger if it is attached to an ability, and will only trigger for the unit that cast the ability. It will trigger when the ability **finishes** casting, and is the main event you should use to execute logic when coding the logic for an ability cast.
>
> The event populates the following preset values:
> - **Casting Unit** (Unit): The unit that cast the ability.
> - **Ability Target Location** (Location): The location that the ability should be cast at.
> - **Target Unit** (Unit): The target unit for the ability (only exists if the ability targets a specific unit).
> </details>

### Time Events

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">On script loaded</summary>
> This event will trigger when the script is loaded. The script is *loaded* when the logic should start being 'checked'. If the script is attached to an ability, this will either be triggered when the unit spawns, or the ability is added to the unit. If the script is attached to an item, it is triggered when the item is equipped. If the script is attached to a general script, it will be triggered when the game begins. This event is often used to handle setup logic.
>
> The event populates no preset values.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">On script unloaded</summary>
> This event will trigger when the script is unloaded. The script is *unloaded* when the logic should stop being 'checked'. If the script is attached to an ability, this will either be triggered when the unit dies, or the ability is removed from the unit. If the script is attached to an item, it is triggered when the item is unequipped.
>
> The event populates no preset values.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Do every frame</summary>
> This event will trigger **every game frame**. This can be very powerful if you need to constantly check if something has happened, but should be avoided if you are executing complex game logic (e.g., don't spawn visual effects every frame).
>
> The event populates no preset values.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Do after X seconds</summary>
> This event will trigger a specific amount of time after the script is first loaded, and then won't trigger again. You can specify the exact amount of time in the number node on the event.
>
> The event populates no preset values.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Do every X seconds</summary>
> This event will repeatedly trigger, with a delay between each execution. Specify the exact amount of time to delay between executions in the number node on the event.
>
> The event populates no preset values.
> </details>

### Unit Events

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is killed</summary>
> This event is triggered every time a unit is killed, regardless of faction or how it was killed (e.g., it could be an ally, a monster, or the player itself).
>
> The event populates the following preset values:
> - **Killed Unit** (Unit): The unit that was killed.
> - **Killing Unit** (Unit): The unit that killed the dying unit.
> - **Killing Ability** (Ability): The ability that killed the dying unit.
> - **Is Critical** (Boolean): True if the ability was a critical, otherwise False.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is damaged</summary>
> This event is triggered every time a unit is damaged, regardless of faction or how it was damaged (e.g., it could be an ally, a monster, or the player itself).
>
> The event populates the following preset values:
> - **Damaged Unit** (Unit): The unit that was damaged.
> - **Damaging Unit** (Unit): The unit that damaged the dying unit.
> - **Damaging Ability** (Ability): The ability that damaged the damaged unit.
> - **Damage Dealt** (Number): The amount of damage done by the ability.
> - **Is Critical** (Boolean): True if the ability was a critical, otherwise False.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is healed</summary>
> This event is triggered every time a unit is healed, regardless of faction or how it was healed (e.g., it could be an ally, a monster, or the player itself).
>
> The event populates the following preset values:
> - **Healed Unit** (Unit): The unit that was healed.
> - **Healing Unit** (Unit): The unit that healed the unit.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit gains resource</summary>
> This event is triggered every time a unit gains resource (except from base regeneration).
>
> The event populates the following preset values:
> - **Triggering Unit** (Unit): The unit that gained sources.
> - **Resources Gained** (Number): The amount of resources gained.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit loses resource</summary>
> This event is triggered every time a unit loses resource.
>
> The event populates the following preset values:
> - **Triggering Unit** (Unit): The unit that lost sources.
> - **Resources Gained** (Number): The amount of resources lost.
> </details>

### Player Events

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player gains experience</summary>
> This event is triggered every time the player gains experience.
>
> The event does not populate any preset values.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player gains a level</summary>
> This event is triggered every time the player gains a level.
>
> The event does not populate any preset values.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player sells an item</summary>
> This event is triggered every time the player sells an item through the shop.
>
> The event populates the following preset values:
> - **Triggering Item** (Unit): The item that was sold.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player buys an item</summary>
> This event is triggered every time the player buys an item through the shop.
>
> The event populates the following preset values:
> - **Triggering Item** (Unit): The item that was purchased.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player equips an item</summary>
> This event is triggered every time the player equips an item.
>
> The event populates the following preset values:
> - **Triggering Item** (Unit): The item that was equipped.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player unequips an item</summary>
> This event is triggered every time the player unequips an item.
>
> The event populates the following preset values:
> - **Triggering Item** (Unit): The item that was unequipped.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player picks up gold</summary>
> This event is triggered every time the player picks up gold.
>
> The event populates the following preset values:
> - **Gold Added** (Number): The amount of gold collected.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player picks up a health globe</summary>
> This event is triggered every time the player picks up a health globe.
>
> The event populates the following preset values:
> - **Health Restored** (Number): The amount of health restored.
> </details>

### Region Events

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit enters region</summary>
> This event is triggered when the player enters a region with a specific name. Use the text slot in the event to specify the exact region name. This must match the name on the region **exactly**.
>
> The event does not populate any preset values.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit leaves region</summary>
> This event is triggered when the player leave a region with a specific name. Use the text slot in the event to specify the exact region name. This must match the name on the region **exactly**.
>
> The event does not populate any preset values.
> </details>

### Projectile Events

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Projectile collides with an enemy</summary>
> This event is triggered when a projectile spawned by this ability or item collides with an enemy of its owner. Note that for optimisation purposes, you cannot use this event to check if a projectile created from *another source* collided with an enemy. **exactly**.
>
> The event populates the following preset values:
> - **Event Projectile** (Projectile): The projectile that collided.
> - **Casting Unit** (Unit): The unit that created the projectile.
> - **Colliding Unit** (Unit): The unit that was hit by the projectile.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Projectile times out</summary>
> This event is triggered when a projectile spawned by this ability or item exceeds its assigned lifetime. Note that you must have first assigned a lifetime to the projectile via the `Projectile > Set Lifetime` action. **exactly**.
>
> The event populates the following preset values:
> - **Event Projectile** (Projectile): The projectile that is timing out.
> - **Casting Unit** (Unit): The unit that created the projectile.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Projectile reaches its goal</summary>
> This event is triggered when a projectile spawned by this ability reaches its goal. This only triggers if the projectile was assigned a goal location, via the `Projectile > Move Projectile Towards Point` action.
>
> The event populates the following preset values:
> - **Event Projectile** (Projectile): The projectile that is timing out.
> - **Casting Unit** (Unit): The unit that created the projectile.
> - **Goal Position** (Location): The final gloal location.
> - **Goal Unit** (Unit): The goal unit. This is only assigned if the projectile was assigned to move towards a specific unit.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Projectile collides with terrain</summary>
> This event is triggered when a projectile spawned by this ability/item collides with terrain (e.g., a wall).
>
> The event populates the following preset values:
> - **Event Projectile** (Projectile): The projectile that collided with terrain.
> - **Casting Unit** (Unit): The unit that created the projectile.
> </details>

### Quest Events

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">On quest received</summary>
> This event is triggered when the player receives a specific quest. Use the text slot in the event to specify the exact quest name. This must match the name of the quest **exactly**.
>
> The event does not populate any preset values.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">On quest completed</summary>
> This event is triggered when the player completes a specific quest. Use the text slot in the event to specify the exact quest name. This must match the name of the quest **exactly**.**exactly**.
>
> The event does not populate any preset values.
> </details>

### Input Events

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">On key down</summary>
> This event is triggered when the player presses a specific key. Use the text slot in the event to specify the exact key. For simple keys, just enter the key (e.g., enter 'f' if you want to check for the f key being pressed). If you want to check more "complex" keybinds, refer to the lists in the discussion thread [**here**](https://discussions.unity.com/t/c-list-of-string-name-for-input-getkey-string-name/112629/3).
>
> The event does not populate any preset values.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">On key up</summary>
> This event is triggered when the player releases a specific key. Use the text slot in the event to specify the exact key. For simple keys, just enter the key (e.g., enter 'f' if you want to check for the f key being pressed). If you want to check more "complex" keybinds, refer to the lists in the discussion thread [**here**](https://discussions.unity.com/t/c-list-of-string-name-for-input-getkey-string-name/112629/3).
>
> The event does not populate any preset values.
> </details>

{: .highlight }
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">On key held</summary>
> This event is triggered when the player every frame while they are holding a specific key. Use the text slot in the event to specify the exact key. For simple keys, just enter the key (e.g., enter 'f' if you want to check for the f key being pressed). If you want to check more "complex" keybinds, refer to the lists in the discussion thread [**here**](https://discussions.unity.com/t/c-list-of-string-name-for-input-getkey-string-name/112629/3).
>
> The event does not populate any preset values.
> </details>