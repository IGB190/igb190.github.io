---
title: Unit Nodes
layout: default
parent: Visual Coding
nav_order: 20
---

# Unit Nodes
{: .no_toc }
Below is a summary of all the visual scripting nodes which return a unit in the visual scripting system. 

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

### Specify a Specific Unit
If the visual scripting node allows it, you will be able to specify a *specific* unit for the node, rather than using one of the methods below (e.g., when spawning a unit). 

![Script Editor Example](../assets/unit-node-1.jpg)

### Unit Nodes (Distance)

{: .new-title }
> Unit > Distance
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Closest unit near point</summary>
> ![Script Editor Example](../assets/unit-node-2.jpg)
>
> Returns the closest unit to the specified point (within the maximum distance).
> </details>

{: .new-title }
> Unit > Distance
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Furthest unit near point</summary>
> ![Script Editor Example](../assets/unit-node-3.jpg)
>
> Returns the furthest unit to the specified point (within the maximum distance).
> </details>

{: .new-title }
> Unit > Distance
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Closest unit near unit</summary>
> ![Script Editor Example](../assets/unit-node-4.jpg)
>
> Returns the closest unit to the specified unit (within the maximum distance).
> </details>

{: .new-title }
> Unit > Distance
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Furthest unit near unit</summary>
> ![Script Editor Example](../assets/unit-node-5.jpg)
>
> Returns the furthest unit to the specified unit (within the maximum distance).
> </details>

### Unit Nodes (Random)

{: .new-title }
> Unit > Random
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Random unit near point</summary>
> ![Script Editor Example](../assets/unit-node-6.jpg)
>
> Returns a random unit within a given distance of a given unit.
> </details>

{: .new-title }
> Unit > Random
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Random unit near point</summary>
> ![Script Editor Example](../assets/unit-node-7.jpg)
>
> Returns a random unit within a given distance of a given point.
> </details>

### Unit Nodes (Variables)

{: .new-title }
> Unit > Variable
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit variable</summary>
> ![Script Editor Example](../assets/unit-node-9.jpg)
>
> Returns the unit stored in the variable with the given name. This variable is shared between all scripts in the same "block" (e.g., ability/item).
> </details>

{: .new-title }
> Unit > Variable
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Global Unit variable</summary>
> ![Script Editor Example](../assets/unit-node-10.jpg)
>
> Returns the unit stored in the global variable with the given name. This variable is shared across the entire application.
> </details>

### Unit Nodes (Other)

{: .new-title }
> Unit > Other
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Unit with label</summary>
> ![Script Editor Example](../assets/unit-node-8.jpg)
>
> Returns the unit in the scene which has the given label. If multiple units have the same label, it will return a random unit.
> </details>