---
title: Player
layout: default
parent: Code Documentation
---

# The Player Class
{: .no_toc }
The player class handles all logic unique to the player character. The player class inherits from the Unit class, so all Unit methods can also be called on the player.

{: .note }
You are not required to write any code in this unit. It is recommended that you instead use the provided visual scripting system in this unit. If you want to implement logic that cannot easily be handled by that system though, this documentation should help you better understand the code and classes in the project.

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

## Referencing the Player
The script architecture is setup for a **single** player character being in the game at once. You can get a reference to this player using `GameManager.player`. 

For example, if you attached the below script as a component to an object in the scene, the player would gain 500 gold whenever the spacebar key was pressed.
```csharp
public class PlayerGoldChangeExample : MonoBehaviour 
{
    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space))
        {
            GameManager.player.AddGold(500);
        }
    }
}
```

## Public Methods
You can interact with the player via the below public methods. These allow you to modify unit stats, visuals, and other key properties.

### Modifying Player Experience
```csharp
// Adds 100 experience to the player. This may cause the player to gain a level.
player.AddExperience(100);

// Removes 100 experience from the player. This **cannot** cause the player to lose a level.
// At most, it can reset them to the start of their current level.

player.RemoveExperience(100);

// Sets the current experience of the player to an exact value. A value of 0 sets them to the
// start of the level. This **can** cause the player to gain multiple levels.
player.SetExperience(0);
```

### Modifying Player Level
```csharp
// Adds 5 levels to the player. This will *keep* their current experience at that new level.
// If the player was 200 experience into level 3, they would be 200 experience into level 8 after this runs.
player.AddLevels(5);

// Removes levels from the player. This will *keep** the player's current experience at that new level.
// If the player was 200 experience into level 8, they would be 200 experience into level 3 after this runs.
player.RemoveLevels(5);

// Sets the player to a specific level.
player.SetLevel(5);
```

{: .warning }
Be very careful when removing levels from the player. You may have logic that runs when the player reaches a specific level, and this could cause that logic to run multiple times if you are not careful.


### Modifying Player Gold
```csharp
// Adds 100 to the player's current gold amount.
player.AddGold(100);

// Removes 100 gold from the player's current gold amount. Gold cannot go below 0.
player.RemoveGold(100);

// Sets the player's current gold to exactly 500. Gold cannot go below 0.
player.SetGold(500);
```

### State Changes
```csharp
// Revives a dead player.
player.Revive();
```

### Status Checks
```csharp
// Checks to see whether the player has a specific item equipped.
bool itemEquipped = player.HasItemEquipped(item);

// Check to see whether the player has a specific item in their inventory.
bool itemInInventory = player.HasItemInInventory(item);
```