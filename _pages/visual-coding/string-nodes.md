---
title: String Nodes
layout: default
parent: Visual Coding
nav_order: 20
---

# String Nodes
{: .no_toc }
Below is a summary of all the visual scripting nodes which return a **string** in the visual scripting system. 

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

### Specify a Specific String
If the visual scripting node allows it, you will be able to specify a *specific* string for the node, rather than using one of the methods below. 

![Script Editor Example](../assets/string-node-1.jpg)

### String Nodes

{: .note-title }
> String
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Name of Unit</summary>
> ![Script Editor Example](../assets/unit-node-2.jpg)
>
> Returns the name of the given unit. Note that its name is specified by the `unitName`, and is not the name of the prefab which you see when selecting the unit from the dropdown.
> </details>

{: .note-title }
> String
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Name of Ability</summary>
> ![Script Editor Example](../assets/unit-node-2.jpg)
>
> Returns the name of the given ability.
> </details>

{: .note-title }
> String
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Tag of Ability</summary>
> ![Script Editor Example](../assets/unit-node-2.jpg)
>
> Returns the tag of the given ability.
> </details>

{: .note-title }
> String
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Tag of Item</summary>
> ![Script Editor Example](../assets/unit-node-2.jpg)
>
> Returns the tag of the given item.
> </details>

{: .note-title }
> String
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Combine Strings</summary>
> ![Script Editor Example](../assets/unit-node-2.jpg)
>
> Combines two strings together using string concatenation.
> </details>

### Unit Nodes (Variables)

{: .note-title }
> String > Variable
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">String variable</summary>
> ![Script Editor Example](../assets/unit-node-9.jpg)
>
> Returns the string stored in the variable with the given name. This variable is shared between all scripts in the same "block" (e.g., ability/item).
> </details>

{: .note-title }
> String > Variable
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Global String variable</summary>
> ![Script Editor Example](../assets/unit-node-10.jpg)
>
> Returns the string stored in the global variable with the given name. This variable is shared across the entire application.
> </details>