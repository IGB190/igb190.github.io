---
title: Events
layout: default
parent: Code Documentation
---

# Game Events
While you are not required to write any code in the development of your experience, if you need to implement complex logic for an item, ability, quest, or other game mechanic, this section will show you how it can be done. This page will focus specifically on how you can build an item with custom logic.

## Triggering an Event


## Listening for an Event

## Registering an Event
All of the events listed below are Unity event variables that can be accessed through the `GameManager.events` object. For example, to register for the OnUnitKilled event, you would do the following:

###
You can register to have a specific method (with a matching signature) run when the event you are listening for is fired. In this case, we are using the `OnUnitKilled` event, so the method must have a signature of `OnUnitKilledInfo`. This `OnUnitKilledInfo` object contains details related to the event which you may need to consider in your actions (e.g., the unit that was killed, the killing unit, the source of the kill, whether it was a critical hit etc).

```csharp
public class RestoreHealthOnKillExample : MonoBehaviour
{
    void Start()
    {
        GameManager.events.OnUnitKilled.AddListener(OnKillActions);
    }

    private void OnKillActions (OnUnitKilledInfo info) 
    {
        GameManager.player.AddHealth(10);
    }
}
```

### Lamda Functions (In-line Logic)
Rather than creating a specific method with the correct signature to handle the logic, you can instead define the logic for the event listener in-line using a lambda function. In this example,  whenever a unit is killed, the player will restore 10 health. This can save some space and make some logic easier to understand, but it can make the logic much harder to manipulate if you need to later de-register this event. For example, if this method should only be registered when an item is equipped, it will be more awkward to deregister it if the item is ever unequipped.

```csharp
public class RestoreHealthOnKillExample : MonoBehaviour
{
    void Start()
    {
        GameManager.events.OnUnitKilled.AddListener(info => {
            GameManager.player.AddHealth(10);
        });
    }
}
```


## Event List
Below provides a comprehensive list of all events used by the game, and the properties given related to each event.

### OnEventMessageReceived
This event can be used to broadcast generic messages to the entire game. This is intended to help send messages to the visual scripting system from coding (e.g., if your experience requires custom logic that is not handled by default).

|Type | Variable |Description |
|string | messageText | The content of the message sent. |

### OnAbilityCastStarted
This event is fired whenever a unit starts casting an ability. This event is fired with an `OnAbilityCastStartedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | castingUnit | The unit casting the ability. |
|Ability | ability | The ability being cast. |
|Unit | targetUnit | The target of the ability (null if no target). |
|Vector3 | targetPosition | The target position of the ability. |

### OnAbilityCastFinished
This event is fired whenever a unit finishes casting an ability. This event is fired with an `OnAbilityCastFinishedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | castingUnit | The unit casting the ability. |
|Ability | ability | The ability being cast. |
|Unit | targetUnit | The target of the ability (null if no target). |
|Vector3 | targetPosition | The target position of the ability. |

### OnUnitGainsBuff
This event is fired whenever a unit gains a buff/debuff. This event is fired with an `OnUnitGainsBuffInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | unitGainingBuff | The Unit that has gained the buff. |
|string | buffName | The name of the buff. |
|Unit | unitApplyingBuff | The unit that applied the buff. This can be null if it wasn't applied by a unit. |

### OnUnitLosesBuff
This event is fired whenever a unit loses a buff/debuff. This event is fired with an `OnUnitLosesBuffInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | unitGainingBuff | The Unit that has lost the buff. |
|string | buffName | The name of the buff. |
|Unit | unitApplyingBuff | The unit that applied the buff. This can be null if it wasn't applied by a unit. |

### OnUnitRefreshesBuff
This event is fired whenever a unit refreshes a buff/debuff. This event is fired with an `OnUnitRefreshesBuffInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | unitWithBuff | The Unit that has the buff. |
|string | buffName | The name of the buff. |
|Unit | unitApplyingBuff | The unit that applied the buff. This can be null if it wasn't applied by a unit. |

### OnUnitKilled
This event is fired whenever a unit is killed. This event is fired with an `OnUnitKilledInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | killedUnit | The Unit that was killed. |
|Unit | killingUnit | The unit that killed the killed unit. |
|bool | isCrit | Whether the effect that killed the unit was a critical strike. |
|IVisualCodeHandler | killingSource | The source that killed the unit (an ability, an item, etc). |

### OnPlayerKilled
This event is fired whenever the player is killed. This event is fired with an `OnPlayerKilledInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | killedUnit | The Unit that was killed. |
|Unit | killingUnit | The unit that killed the killed unit. |
|bool | isCrit | Whether the effect that killed the unit was a critical strike. |
|IVisualCodeHandler | killingSource | The source that killed the unit (an ability, an item, etc). |

### OnPlayerExperienceGained
This event is fired whenever the player gains experience. This event is fired with an `OnPlayerExperienceGainedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Player | player | The player that gained experience. |
|float | experienceGained | The amount of experience gained. |

### OnPlayerLevelUp
This event is fired whenever the player gains a level. This event is fired with an `OnPlayerLevelUpInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Player | player | The player that gained a level. |
|int | playerLevel | The new level of the player. |

### OnPlayerEnteredRegion
This event is fired whenever a unit enters a region. This event is fired with an `OnPlayerEnteredRegionInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | enteringUnit | The unit that entered the region. |
|Region | region | The region that was entered. |
|string | regionName | The name of the region that was entered. |

### OnPlayerExistsRegion
This event is fired whenever a unit exits a region. This event is fired with an `OnPlayerExistsRegionInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | exitingUnit | The unit that exited the region. |
|Region | region | The region that was exited. |
|string | regionName | The name of the region that was exited. |

### OnUnitDamaged
This event is fired whenever a unit is damaged. This event is fired with an `OnUnitDamagedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | damagedUnit | The unit that was damaged. |
|Unit | damagingUnit | The unit that did the damage. |
|bool | isCritical | Whether the damage dealt was a critical hit. |
|float | damage | The amount of damage that was dealt. |
|IVisualCodeHandler | damageSource | The source that did the damage (an ability, an item etc). |

### OnUnitSpawned
This event is fired whenever a unit is spawned. This event is fired with an `OnUnitSpawnedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | spawnedUnit | The unit that was spawned. |
|Unit | spawningUnit | The unit that spawned the unit. Can be null if it was not spawned by a unit. |

### OnGoldAdded
This event is fired whenever the player gains gold. This event is fired with an `OnGoldAddedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|float | goldAdded | The amount of gold that was added. |

### OnGoldRemoved
This event is fired whenever the player loses gold. This event is fired with an `OnGoldRemovedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|float | goldRemoved | The amount of gold that was removed. |

### OnGoldPickedUp
This event is fired whenever the player picks up gold. This event is fired with an `OnGoldPickedUpInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|float | goldPickedUp | The amount of gold that was picked up. |

### OnHealthPickedUp
This event is fired whenever the player picks up a health globe. This event is fired with an `OnHealthPickedUpInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|float | healthPickedUp | The amount of health that was picked up. |

### OnItemEquipped
This event is fired whenever the player equips an item. This event is fired with an `OnItemEquippedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Item | itemEquipped | The item that was equipped. |

### OnItemUnequipped
This event is fired whenever the player unequips an item. This event is fired with an `OnItemUnequippedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Item | itemUnequipped | The item that was unequipped. |

### OnItemSold
This event is fired whenever the player sells an item. This event is fired with an `OnItemSoldInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Item | itemSold | The item that was sold. |

### OnQuestUpdated
This event is fired whenever a quest is updated. This event is fired with an `OnQuestUpdatedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Quest | questUpdated | The quest that was updated. |

### OnQuestCompleted
This event is fired whenever a quest is completed. This event is fired with an `OnQuestCompletedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Quest | questCompleted | The quest that was completed. |

### OnQuestAdded
This event is fired whenever a quest is added to the quest system. This event is fired with an `OnQuestAddedInfo` object with the following variables:
 
|**Type** | **Variable** |**Description** |
|Quest | questAdded | The quest that was added. |

### OnGameWon
This event is fired whenever the player wins the game. This event is fired with an `OnGameWonInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Player | player | The player that won the game. |


```csharp
// Add 100 to the unit's current health.
unit.AddHealth(100);

// Remove 100 from the unit's current health.
unit.RemoveHealth(100);
```





The experience can be developed without any code, but if you do want to use code to develop your items, abilities, quests or other content to control complex logic which cannot easi

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

## Unit Logic


### Ability Selection
Non-player units will constantly try to 

### Target Selection


### Unit Range
Unit


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