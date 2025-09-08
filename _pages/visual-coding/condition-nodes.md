---
title: Condition Nodes
layout: default
parent: Visual Coding
nav_order: 10
---

# Condition Nodes
{: .no_toc }
Below is a summary of all the condition/boolean nodes in the visual scripting system. You can use any of these (or a combination of these) when looking to perform condition checks in the visual scripting system.

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

### Region Conditions

{: .new-title }
> Condition > Region
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Region exists</summary>
> ![Script Editor Example](../assets/condition-1.jpg)
>
> True if a region with the **exact** name currently exists. 
> </details>

{: .new-title }
> Condition > Region
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is in region</summary>
> ![Script Editor Example](../assets/condition-2.jpg)
>
> True if the specified unit is currently in a region with the specified name. The name must match the region **exactly**.
> </details>

### Input Conditions

{: .new-title }
> Condition > Input
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Key is held</summary>
> ![Script Editor Example](../assets/condition-3.jpg)
>
> True if the specified key is currently being held. For simple keys, just enter the key (e.g., enter 'f' if you want to check for the f key being pressed). If you want to check more "complex" keybinds, refer to the lists in the discussion thread [**here**](https://discussions.unity.com/t/c-list-of-string-name-for-input-getkey-string-name/112629/3).
> </details>

### Unit Group Conditions

{: .new-title }
> Condition > Unit Group
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit group is empty</summary>
> ![Script Editor Example](../assets/condition-4.jpg)
>
> True if the specified `Unit Group` contains no units.
> </details>

{: .new-title }
> Condition > Unit Group
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit group is not empty</summary>
> ![Script Editor Example](../assets/condition-5.jpg)
>
> True if the specified `Unit Group` contains at least one units.
> </details>

{: .new-title }
> Condition > Unit Group
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is in unit group</summary>
> ![Script Editor Example](../assets/condition-6.jpg)
>
> True if the specified `Unit` is contained in the specified `Unit Group`.
> </details>

{: .new-title }
> Condition > Unit Group
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is not in unit group</summary>
> ![Script Editor Example](../assets/condition-7.jpg)
>
> True if the specified `Unit` is **not** contained in the specified `Unit Group`.
> </details>

### Comparisons

{: .new-title }
> Condition > Comparisons
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Or Comparison</summary>
> ![Script Editor Example](../assets/condition-8.jpg)
>
> True if **either** (or both) of the specified conditions is true.
> </details>

{: .new-title }
> Condition > Comparisons
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">And Comparison</summary>
> ![Script Editor Example](../assets/condition-9.jpg)
>
> True if **both** of the specified conditions are true.
> </details>

{: .new-title }
> Condition > Comparisons
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Bool Comparison</summary>
> ![Script Editor Example](../assets/condition-10.jpg)
>
> Compares two Boolean conditions and checks them against the assigned operator (`Equal to`, or `Not Equal To`).
> </details>

{: .new-title }
> Condition > Comparisons
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Bool Comparison</summary>
> ![Script Editor Example](../assets/condition-10.jpg)
>
> Compares two Boolean conditions and checks them against the assigned operator (`Equal to`, or `Not Equal To`).
> </details>

{: .new-title }
> Condition > Comparisons
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Number Comparison</summary>
> ![Script Editor Example](../assets/condition-11.jpg)
>
> Compares two numbers and checks them against the assigned operator (`Equal to`, or `Not Equal To`, `Greater Than`, `Less Than`, `Greater Than or Equal To`, `Less Than or Equal To`).
> </details>

{: .new-title }
> Condition > Comparisons
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Vector Comparison</summary>
> ![Script Editor Example](../assets/condition-12.jpg)
>
> Compares two vectors/positions and checks them against the assigned operator (`Equal to`, or `Not Equal To`).
> </details>

{: .new-title }
> Condition > Comparisons
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Ability Comparison</summary>
> ![Script Editor Example](../assets/condition-13.jpg)
>
> Compares two abilities and checks them against the assigned operator (`Equal to`, or `Not Equal To`).
> </details>

{: .new-title }
> Condition > Comparisons
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Text Comparison</summary>
> ![Script Editor Example](../assets/condition-14.jpg)
>
> Compares two pieces of text and checks them against the assigned operator (`Equal to`, or `Not Equal To`).
> </details>

{: .new-title }
> Condition > Comparisons
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit Comparison</summary>
> ![Script Editor Example](../assets/condition-15.jpg)
>
> Compares two units and checks them against the assigned operator (`Equal to`, or `Not Equal To`).
> </details>

### Unit

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit matches template</summary>
> ![Script Editor Example](../assets/condition-16.jpg)
>
> Returns true if the specified unit matches the specified template. This is useful for checking the "type" of unit - e.g., a Skeleton Archer.
> </details>

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is moving</summary>
> ![Script Editor Example](../assets/condition-17.jpg)
>
> Returns true if the specified unit is currently moving (this does **not** include unit movement through the `Unit > Move Over Time` action, only standard movement).
> </details>

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is stationary</summary>
> ![Script Editor Example](../assets/condition-18.jpg)
>
> Returns true if the specified unit is **not** currently moving (this does **not** check for movement through the `Unit > Move Over Time` action, only 'standard' movement).
> </details>

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is casting</summary>
> ![Script Editor Example](../assets/condition-19.jpg)
>
> Returns true if the specified unit is currently casting an ability.
> </details>

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit can move</summary>
> ![Script Editor Example](../assets/condition-20.jpg)
>
> Returns true if the specified unit **could** currently move.
> </details>

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit has buff</summary>
> ![Script Editor Example](../assets/condition-21.jpg)
>
> Returns true if the specified unit has a buff with the specified name. This buff name must match a buff exactly (this is case sensitive).
> </details>

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is stunned</summary>
> ![Script Editor Example](../assets/condition-22.jpg)
>
> Returns true if the specified unit is currently stunned.
> </details>

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit ability is on cooldown</summary>
> ![Script Editor Example](../assets/condition-23.jpg)
>
> Returns true if the specified ability for the specified unit is currently on cooldown.
> </details>

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit can cast ability</summary>
> ![Script Editor Example](../assets/condition-24.jpg)
>
> Returns true if the specified ability for the specified unit could currently be cast. This may be because the unit lacks resources, is already casting, etc.
> </details>

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit is empowered</summary>
> ![Script Editor Example](../assets/condition-25.jpg)
>
> Returns true if the specified unit is currently empowered. Only monsters can be empowered.
> </details>

{: .new-title }
> Condition > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit has tag</summary>
> ![Script Editor Example](../assets/condition-26.jpg)
>
> Returns true if the specified unit has the specified tag. This must match the unit tag exactly.
> </details>

### Quests

{: .new-title }
> Condition > Quest
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Quest is active</summary>
> ![Script Editor Example](../assets/condition-27.jpg)
>
> Returns true if a quest with the specified name is currently active for the player.
> </details>

{: .new-title }
> Condition > Quest
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Quest has been completed</summary>
> ![Script Editor Example](../assets/condition-28.jpg)
>
> Returns true if a quest with the specified name has been completed by the player.
> </details>

### Player

{: .new-title }
> Condition > Player
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player has item equipped</summary>
> ![Script Editor Example](../assets/condition-29.jpg)
>
> Returns true if the player currently has the specified item equipped.
> </details>

{: .new-title }
> Condition > Player
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player has item in inventory</summary>
> ![Script Editor Example](../assets/condition-30.jpg)
>
> Returns true if the player currently has the specified item in their inventory. This can be useful for checking if the player is holding a key or other object.
> </details>

### Variables

{: .new-title }
> Condition > Variables
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Boolean Variable</summary>
> ![Script Editor Example](../assets/condition-30.jpg)
>
> Returns the value of a Boolean variable with the given name. This variable is local to the "group" of scripts - i.e., the variable will be shared by all of the scripts used by the ability or item.
> </details>

{: .new-title }
> Condition > Variables
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Global Boolean Variable</summary>
> ![Script Editor Example](../assets/condition-30.jpg)
>
> Returns the value of a Boolean variable with the given name. This variable is global to the entire application.
> </details>