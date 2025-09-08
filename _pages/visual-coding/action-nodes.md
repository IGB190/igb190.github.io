---
title: Action Nodes
layout: default
parent: Visual Coding
nav_order: 10
---

# Action Nodes
{: .no_toc }
Below is a summary of all the action nodes in the visual scripting system. These action nodes perform all of the action logic for the visual scripting system.

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

### Action Nodes (Flow)

{: .important-title }
> Action > Flow
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Wait</summary>
> ![Script Editor Example](../assets/action-nodes-1.jpg)
>
> Waits for the specified amount of time before continuing the remaining actions. 
> </details>

{: .important-title }
> Action > Flow
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">If statement</summary>
> ![Script Editor Example](../assets/action-nodes-2.jpg)
>
> Only executes the nested actions if the given condition is true. 
> </details>

{: .important-title }
> Action > Flow
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">While statement</summary>
> ![Script Editor Example](../assets/action-nodes-3.jpg)
>
> Executes the nested actions while the specified condition is true.
> </details>

{: .important-title }
> Action > Flow
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">For statement</summary>
> ![Script Editor Example](../assets/action-nodes-4.jpg)
>
> Executes the nested actions a set number of times.
> </details>

{: .important-title }
> Action > Flow
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">For each unit in unit group</summary>
> ![Script Editor Example](../assets/action-nodes-5.jpg)
>
> Executes the nested actions for each unit in the specified unit group.
> </details>

{: .important-title }
> Action > Flow
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Disable this script</summary>
> ![Script Editor Example](../assets/action-nodes-6.jpg)
>
> Disables this script, preventing the events from triggering.
> </details>

{: .important-title }
> Action > Flow
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Send event message</summary>
> ![Script Editor Example](../assets/action-nodes-7.jpg)
>
> Sends an event message which can be received by the corresponding event message event. This allows you to have one script trigger logic in a secondary script.
> </details>

### Action Nodes (Unit)
...

### Action Nodes (Player)
...

### Action Nodes (Audio)

{: .important-title }
> Action > Audio
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Play audio clip</summary>
> ![Script Editor Example](../assets/action-nodes-14.jpg)
>
> Plays the specified sound effect. **Do not** use this to play game music - use the `Play music` action instead!
> </details>

{: .important-title }
> Action > Audio
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Play music</summary>
> ![Script Editor Example](../assets/action-nodes-15.jpg)
>
> Plays the specified music. **Do not** use this to play sound effects - use the `Play audio clip` action instead!
> </details>

### Action Nodes (Feedback)
...

### Action Nodes (Projectile)
...

### Action Nodes (Region)

{: .important-title }
> Action > Region
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Destroy region</summary>
> ![Script Editor Example](../assets/action-nodes-7.jpg)
>
> Destroys all regions with the given name (if any exist).
> </details>

### Action Nodes (Quests)
...

### Action Nodes (Pickups)

{: .important-title }
> Action > Pickups
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Spawn item pickup</summary>
> ![Script Editor Example](../assets/action-nodes-11.jpg)
>
> Spawn an item pickup at the specified location which contains the specified item.
> </details>

{: .important-title }
> Action > Pickups
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Spawn gold pickup</summary>
> ![Script Editor Example](../assets/action-nodes-12.jpg)
>
> Spawn a gold pickup at the specified location which contains the specified amount of gold.
> </details>

{: .important-title }
> Action > Pickups
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Spawn health pickup</summary>
> ![Script Editor Example](../assets/action-nodes-13.jpg)
>
> Spawn a health pickup at the specified location.
> </details>

### Action Nodes (Game State)

{: .important-title }
> Action > Game State
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Win game</summary>
> ![Script Editor Example](../assets/action-nodes-10.jpg)
>
> Have the player win the game, taking them to the victory screen.
> </details>

### Action Nodes (UI Actions)

{: .important-title }
> Action > UI Actions
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Show debug message</summary>
> ![Script Editor Example](../assets/action-nodes-16.jpg)
>
> Logs the given message to the game console.
> </details>

{: .important-title }
> Action > UI Actions
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Show in-world status message</summary>
> ![Script Editor Example](../assets/action-nodes-17.jpg)
>
> Shows the specified message in world space with the specified text and color (this is how the gold and health messages are implemented!).
> </details>

{: .important-title }
> Action > UI Actions
> 
> <details markdown="1" class="note">
> <summary style="font-weight: 500;">Show tutorial message</summary>
> ![Script Editor Example](../assets/action-nodes-18.jpg)
>
> Shows the given message in a tutorial window. This is useful for giving information or instructions to the player.
> </details>

### Action Nodes (Variables)
...

### Action Nodes (Global Variables)
...
