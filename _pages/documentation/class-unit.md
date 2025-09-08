---
title: Unit
layout: default
parent: Code Documentation
---

# The Unit Class
This page details the key public methods available to interact with the Unit class. Both the Player and the Monster classes inherit from this class, so any methods shown here will work on any unit in the game. 

{: .note }
You are not required to write any code in this unit. It is recommended that you instead use the provided visual scripting system in this unit. If you want to implement logic that cannot easily be handled by that system though, this documentation should help you better understand the code and classes in the project.

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