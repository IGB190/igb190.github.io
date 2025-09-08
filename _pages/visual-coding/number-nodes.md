---
title: Number Nodes
layout: default
parent: Visual Coding
nav_order: 20
---

# Number Nodes
{: .no_toc }
Below is a summary of all the visual scripting nodes which return a **number** in the visual scripting system. 

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

### Specify a Specific Number
If the visual scripting node allows it, you will be able to specify a *specific* number for the node, rather than using one of the methods below (e.g., dealing an exact amount of damage). 

![Script Editor Example](../assets/number-nodes-1.jpg)

### Number Nodes (Player)

{: .note-title }
> Number > Player
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player level</summary>
> ![Script Editor Example](../assets/unit-node-2.jpg)
>
> Returns the current player level.
> </details>

{: .note-title }
> Number > Player
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player gold</summary>
> ![Script Editor Example](../assets/unit-node-3.jpg)
>
> Returns the amount of gold the player currently has.
> </details>

{: .note-title }
> Number > Player
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Player items equipped</summary>
> ![Script Editor Example](../assets/unit-node-3.jpg)
>
> Returns the number of items the player currently has equipped.
> </details>

### Number (Time)

{: .note-title }
> Number > Time
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Time since level start</summary>
> Returns the amount of time in seconds since the level started.
> </details>

{: .note-title }
> Number > Time
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Delta time</summary>
> Returns the amount of time spent rendering the frame.
> </details>

{: .note-title }
> Number > Time
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Fixed delta time</summary>
> Returns the amount of time between physicis timesteps.
> </details>

### Number (Math)

{: .note-title }
> Number > Math
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Addition</summary>
> ![Script Editor Example](../assets/number-nodes-2.jpg)
>
> Returns the result of two numbers being added together.
> </details>

{: .note-title }
> Number > Math
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Subtraction</summary>
> ![Script Editor Example](../assets/number-nodes-3.jpg)
>
> Returns the result of one number being subtracted from another.
> </details>

{: .note-title }
> Number > Math
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Multiplication</summary>
> ![Script Editor Example](../assets/number-nodes-4.jpg)
>
> Returns the result of two numbers being multiplied together.
> </details>

{: .note-title }
> Number > Math
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Division</summary>
> ![Script Editor Example](../assets/number-nodes-5.jpg)
>
> Returns the result of one number being divided by another.
> </details>

{: .note-title }
> Number > Math
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Distance between points</summary>
> ![Script Editor Example](../assets/number-nodes-6.jpg)
>
> Returns the distance between two points.
> </details>

{: .note-title }
> Number > Math
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Distance between units</summary>
> ![Script Editor Example](../assets/number-nodes-7.jpg)
>
> Returns the distance between two units.
> </details>

{: .note-title }
> Number > Math
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Vector component</summary>
> ![Script Editor Example](../assets/number-nodes-8.jpg)
>
> Returns a specific component from a vector (e.g., the X, Y, or Z component).
> </details>

### Number Nodes (Random)

{: .note-title }
> Number > Random
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Random number</summary>
> ![Script Editor Example](../assets/number-nodes-9.jpg)
>
> Returns a random number between two values.
> </details>

### Number Nodes (Unit)

{: .note-title }
> Number > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit health</summary>
> ![Script Editor Example](../assets/number-nodes-10.jpg)
>
> Returns the current health of the specified unit.
> </details>

{: .note-title }
> Number > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit max health</summary>
> ![Script Editor Example](../assets/number-nodes-11.jpg)
>
> Returns the maximum health of the specified unit.
> </details>

{: .note-title }
> Number > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit health percent</summary>
> ![Script Editor Example](../assets/number-nodes-12.jpg)
>
> Returns the current health percent of the unit (e.g., 40 = 40% health).
> </details>

{: .note-title }
> Number > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit resource</summary>
> ![Script Editor Example](../assets/number-nodes-13.jpg)
>
> Returns the current resource of the specified unit.
> </details>

{: .note-title }
> Number > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit max resource</summary>
> ![Script Editor Example](../assets/number-nodes-14.jpg)
>
> Returns the maximum resource of the specified unit.
> </details>

{: .note-title }
> Number > Unit
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit resource percent</summary>
> ![Script Editor Example](../assets/number-nodes-15.jpg)
>
> Returns the current resource percent of the unit (e.g., 40 = 40% resource).
> </details>    

### Number (Unit Group)

{: .note-title }
> Number > Unit Group
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Count units in unit group</summary>
> ![Script Editor Example](../assets/number-nodes-16.jpg)
>
> Returns the number of units in the specified unit group.
> </details>  

### Number (Variables)

{: .note-title }
> Unit > Variable
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Number variable</summary>
> ![Script Editor Example](../assets/unit-node-17.jpg)
>
> Returns the number stored in the variable with the given name. This variable is shared between all scripts in the same "block" (e.g., ability/item).
> </details>

{: .note-title }
> Unit > Variable
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Global number variable</summary>
> ![Script Editor Example](../assets/unit-node-18.jpg)
>
> Returns the number stored in the global variable with the given name. This variable is shared across the entire application.
> </details>