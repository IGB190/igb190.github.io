---
title: Item Pickup
layout: default
parent: Code Documentation
---

# The ItemPickup Class
The ItemPickup class is used to control the generation of item pickups.

## Placing an Item Pickup in the World
In the base project, you can find the Item Pickup prefab under `Assets > Assets to Use > ItemPickup`. 

Drag this prefab into the environment and place it where you want it. In the inspector, you can then choose to either specify a specific item for the pickup, or the intended rarity for the randomised item.

## Spawning an Item Pickup
```csharp
// Items are scriptable objects. If you expose the item variable in the inspector,
// you can select the item template you want to use.
public Item itemToSpawn;

// Spawn an item pickup containing the specified item.
ItemPickup.Spawn(spawnLocation, itemToSpawn);

// Spawn an item pickup containing a random item of the specified rarity.
ItemPickup.Spawn(spawnLocation, Item.ItemRarity.Common);
ItemPickup.Spawn(spawnLocation, Item.ItemRarity.Rare);
ItemPickup.Spawn(spawnLocation, Item.ItemRarity.Legendary);
```





The experience can be developed without any code, but if you do want to use code to develop your items, abilities, quests or other content to control complex logic which cannot easi

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

## Public Methods
You can interact with units via the public methods. These allow you to modify unit stats, visuals, and other key properties.


### Modifying Unit Health
```csharp
// Add 100 to the unit's current health.
unit.AddHealth(100);

// Remove 100 from the unit's current health.
unit.RemoveHealth(100);
```

### Modifying Unit Resources
```csharp
// Add 100 to the unit's current resource count.
unit.AddResource(100);

// Remove 100 from the unit's current resource count.
unit.RemoveResource(100);
```

### Modifying Unit Abilities
```csharp
// Add the specified ability to the unit.
unit.AddAbility(abilityTemplate);

// Remove the specified ability from the unit.
unit.RemoveAbility(abilityTemplate);

// Replace the current specified ability with the specified ability. If the unit does
// not have the 'current' ability, they will not get the new ability.
unit.ReplaceAbility(currentAbilityTemplate, newAbilityTemplate);

// Lock the given ability, preventing the unit from casting it. If the unit does not
// have an ability with a matching template, this will do nothing.
unit.LockAbility(abilityTemplate);

// Unlock the given ability, allowing the unit to cast it. If the unit does not
// have an ability with a matching template, this will do nothing.
unit.UnlockAbility(abilityTemplate);
```

### Checking Unit Statuses 
```csharp
// Check to see if the unit is currently stunned.
bool isStunned = unit.IsStunned();

// Check to see if the unit is currently moving.
bool isMoving = unit.IsMoving();

// Check to see if the unit is currently casting an ability.
bool isCasting = unit.IsCasting();

// Check to see if the specified unit is an enemy of the unit.
bool isEnemy = unit.IsEnemy(unitToCompare);

// Check to see if the specified unit is an ally of the unit.
bool isAlly = unit.IsAlly(unitToCompare);

// Check to see if the unit has a specific buff/debuff.
bool hasBuff = unit.HasBuff("NameOfBuff");

// Check to see if the unit is currently able to move.
bool canMove = unit.CanMove();
```

### Moving a Unit
```csharp
// Instantly move the unit to the specified location.
unit.Teleport(newPosition);

// Smoothly move the unit to the specified location in the specified amount of time.
unit.MoveOverTime(newPosition, timeToReachDestination);
```

### Visual Effects
```csharp
// Set the outline colour for the unit.
unit.SetOutline(Color.red);

// Set the outline colour and size for the unit.
unit.SetOutline(Color.red, outlineSize, outlineAlpha);

// Have the unit play the specified animation (the name must match a node in the Animator).
unit.PlayAnimation("AnimationName");

// Rotate the unit by the given amount (in degrees) over the given duration.
unit.StartSpin(degreesToRotate, duration);
```

### Applying a Buff
```csharp
// Set the outline colour for the unit.
unit.SetOutline(Color.red);

// Set the outline colour and size for the unit.
unit.SetOutline(Color.red, outlineSize, outlineAlpha);

// Have the unit play the specified animation (the name must match a node in the Animator).
unit.PlayAnimation("AnimationName");

// Rotate the unit by the given amount (in degrees) over the given duration.
unit.StartSpin(degreesToRotate, duration);
```

### Modifying a Stat
```csharp
// Permanently modifies the movement speed of the unit. In this case,
// it will increase the movement speed of the unit by 20%.
//
// Valid Stats include: 
//  - Damage
//  - MaxHealth
//  - MaxResource
//  - CriticalStrikeChance
//  - CriticalStrikeDamage
//  - Armor
//  - AttacksPerSecond
//  - CooldownReduction
//  - MovementSpeed
//  - ResourceCostReduction
//  - ResourceGeneration
unit.stats[Stat.MovementSpeed].AddPercentageModifier(1.2f);

// Temporarily modifies the movement speed of the unit. In this case,
// it will increase the movement speed of the unit by 20% for 10 seconds.
unit.stats[Stat.MovementSpeed].AddTimedPercentageModifier(1.2f, 10.0f);

// A buff name can also be given when applying a buff or debuff. This lets you
// reference it later if you want to remove or modify it (e.g., an ability may
// give the player a movement speed boost until they next take damage).
unit.stats[Stat.MovementSpeed].AddPercentageModifier(1.2f, "Sprint");

// If a buff name is given, a maximum number of buff 'stacks' can also be specified.
// This limits how many times this effect can be applied to the unit. In this case,
// the unit can have three sprint modifiers applied (resulting in a 60% speed increase).
unit.stats[Stat.MovementSpeed].AddPercentageModifier(1.2f, "Sprint", 3);

// This method can be used to remove all existing modifiers with a matching label.
unit.stats[Stat.Damage].RemoveModifiersWithLabel("Sprint");

// A stat modifier can also be a specific value, rather than a percentage. In this case,
// the base damage of all attacks is increased by 5 instead of a percentage modifier.
unit.stats[Stat.Damage].AddValueModifier(5);
```

### Modifying a Specific Unit Ability
```csharp
// Modifies the damage of the specified ability on the specified unit.
// In this example, the ability would do 50% more damage.
unit.AddAbilityDamageModifier(ability, 1.5f);

// Modifies the cooldown of the specified ability on the specified unit.
// In this example, the ability cooldown will be reduced by 50%.
unit.AddAbilityCooldownModifier(ability, 0.5f);

// Modifies the cost of the specified ability on the specified unit.
// In this example, the ability would be reduced to 10% of its current cost.
unit.AddAbilityCostModifier(ability, 0.1f);

// Just like with stat modifiers, the ability modifiers can also be timed.
// In this example, the ability would deal double damage for five seconds.
unit.AddTimedAbilityDamageModifier(ability, 2.0f, 5.0f);

// Just like with stat modifiers, the ability modifiers can also be given a
// reference name, and a maximum stack count.
unit.AddTimedAbilityDamageModifier(ability, 2.0f, 5.0f, "Frenzy", 1);

// Use this method to remove all ability modifiers from an ability which have
// the given reference name (e.g., this would remove the frenzy buff in the previous example).
unit.RemoveAbilityBuffModifiers(ability, "Frenzy");
```



### Damaging a Unit
```csharp
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

---


## Download the Model

{: .highlight }
> 1. Go to [Mixamo](https://www.mixamo.com/).
1. Log in, or create a new account if you do not already have one.
1. Select or upload your character model.
1. Customize the animation if needed by selecting from the animations available.
1. Click the Download button.
1. Choose the following options for Unity:
- **Format**: FBX for Unity.
- **Pose**: T-Pose.
- **Animation**: If you want to include the animation, make sure it's selected.
- **Skin**: With Skin.
1. Click the Download button in the popup.

## Import the Mixamo Model

{: .highlight }
> 1. Open your Unity project.
1. In the Project window, navigate to the folder you want to import the model into.
1. Drag the downloaded FBX file into the Unity folder, or right-click and select Import New Asset to locate and import the file manually.
1. Once imported, select the model in the Project window.
1. In the Inspector, go to the Model tab and ensure the Animation Type is set to Humanoid (for human-like characters) or Generic (for other types of models).
1. Under the Material section, if you're using the legacy shader, check Import Materials and Use Legacy Materials to ensure proper texture mapping. This will help the model use the correct materials that were imported with the FBX.
1. Click Apply.

## Importing Mixamo Animations
> 1. Go to Mixamo.com.
1. Log in, or create a new account if you do not already have one.

{: .warning }
Mixamo models use different avatars for defining animations. This means that an animation shown on one character may not look correct if it is applied to a different character. If you encounter this problem, you should use a T-Pose for the avatar instead.

<iframe width="480" height="360" src="http://www.youtube.com/embed/WO82PoAczTc" frameborder="0"> </iframe>


dfgdfgdfg

## Features
- Clean layout
- Responsive design
- Easy to use

Default label
{: .label }

Blue label
{: .label .label-blue }

Stable
{: .label .label-green }

New release
{: .label .label-purple }

Coming soon
{: .label .label-yellow }

Deprecated
{: .label .label-red }