---
title: Events
layout: default
parent: Code Documentation
---

# Game Events
{: .no_toc }
While you are not required to write any code in the development of your experience, if you need to implement complex logic for an item, ability, quest, or other game mechanic, this section will show you how it can be done. This page will focus specifically on how you can build an item with custom logic.

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

## Registering an Event Listener
All of the events listed below are Unity event variables that can be accessed through the `GameManager.events` object. There are two ways that this can be done: (1) using a callback method, or (2) using an in-line lambda function. An example using both methods is shown below, in which the player restores 10 health every time a unit is killed.

### Callback Methods
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

### Lamda Methods (In-line Logic)
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

## Invoking an Event
It is unlikely you will need to do this, but if you need to trigger an event (rather than listen for an event occuring), you can manually invoke the event. To this with Unity Events, you use the `Invoke` method with an object of the correct type.

For example, if you wanted to invoke the OnPlayerLevelUp event, you could invoke it by doing the following:

```csharp
// Create the container storing all of the information.
OnPlayerLevelUpInfo info = new OnPlayerLevelUpInfo();

// Populate all of the information needed for the container.
info.player = GameManager.player;
info.playerLevel = GameManager.player.level;

// Invoke the event with the specified information.
GameManager.events.OnPlayerLevelUp.Invoke(info);
```

## Event List
Below provides a comprehensive list of all events used by the game, and the properties given related to each event.

### OnEventMessageReceived
{: .no_toc }
This event can be used to broadcast generic messages to the entire game. This is intended to help send messages to the visual scripting system from coding (e.g., if your experience requires custom logic that is not handled by default).

|Type | Variable |Description |
|string | messageText | The content of the message sent. |

### OnAbilityCastStarted
{: .no_toc }
This event is fired whenever a unit starts casting an ability. This event is fired with an `OnAbilityCastStartedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | castingUnit | The unit casting the ability. |
|Ability | ability | The ability being cast. |
|Unit | targetUnit | The target of the ability (null if no target). |
|Vector3 | targetPosition | The target position of the ability. |

### OnAbilityCastFinished
{: .no_toc }
This event is fired whenever a unit finishes casting an ability. This event is fired with an `OnAbilityCastFinishedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | castingUnit | The unit casting the ability. |
|Ability | ability | The ability being cast. |
|Unit | targetUnit | The target of the ability (null if no target). |
|Vector3 | targetPosition | The target position of the ability. |

### OnUnitGainsBuff
{: .no_toc }
This event is fired whenever a unit gains a buff/debuff. This event is fired with an `OnUnitGainsBuffInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | unitGainingBuff | The Unit that has gained the buff. |
|string | buffName | The name of the buff. |
|Unit | unitApplyingBuff | The unit that applied the buff. This can be null if it wasn't applied by a unit. |

### OnUnitLosesBuff
{: .no_toc }
This event is fired whenever a unit loses a buff/debuff. This event is fired with an `OnUnitLosesBuffInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | unitGainingBuff | The Unit that has lost the buff. |
|string | buffName | The name of the buff. |
|Unit | unitApplyingBuff | The unit that applied the buff. This can be null if it wasn't applied by a unit. |

### OnUnitRefreshesBuff
{: .no_toc }
This event is fired whenever a unit refreshes a buff/debuff. This event is fired with an `OnUnitRefreshesBuffInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | unitWithBuff | The Unit that has the buff. |
|string | buffName | The name of the buff. |
|Unit | unitApplyingBuff | The unit that applied the buff. This can be null if it wasn't applied by a unit. |

### OnUnitKilled
{: .no_toc }
This event is fired whenever a unit is killed. This event is fired with an `OnUnitKilledInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | killedUnit | The Unit that was killed. |
|Unit | killingUnit | The unit that killed the killed unit. |
|bool | isCrit | Whether the effect that killed the unit was a critical strike. |
|IVisualCodeHandler | killingSource | The source that killed the unit (an ability, an item, etc). |

### OnPlayerKilled
{: .no_toc }
This event is fired whenever the player is killed. This event is fired with an `OnPlayerKilledInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | killedUnit | The Unit that was killed. |
|Unit | killingUnit | The unit that killed the killed unit. |
|bool | isCrit | Whether the effect that killed the unit was a critical strike. |
|IVisualCodeHandler | killingSource | The source that killed the unit (an ability, an item, etc). |

### OnPlayerExperienceGained
{: .no_toc }
This event is fired whenever the player gains experience. This event is fired with an `OnPlayerExperienceGainedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Player | player | The player that gained experience. |
|float | experienceGained | The amount of experience gained. |

### OnPlayerLevelUp
{: .no_toc }
This event is fired whenever the player gains a level. This event is fired with an `OnPlayerLevelUpInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Player | player | The player that gained a level. |
|int | playerLevel | The new level of the player. |

### OnPlayerEnteredRegion
{: .no_toc }
This event is fired whenever a unit enters a region. This event is fired with an `OnPlayerEnteredRegionInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | enteringUnit | The unit that entered the region. |
|Region | region | The region that was entered. |
|string | regionName | The name of the region that was entered. |

### OnPlayerExistsRegion
{: .no_toc }
This event is fired whenever a unit exits a region. This event is fired with an `OnPlayerExistsRegionInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | exitingUnit | The unit that exited the region. |
|Region | region | The region that was exited. |
|string | regionName | The name of the region that was exited. |

### OnUnitDamaged
{: .no_toc }
This event is fired whenever a unit is damaged. This event is fired with an `OnUnitDamagedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | damagedUnit | The unit that was damaged. |
|Unit | damagingUnit | The unit that did the damage. |
|bool | isCritical | Whether the damage dealt was a critical hit. |
|float | damage | The amount of damage that was dealt. |
|IVisualCodeHandler | damageSource | The source that did the damage (an ability, an item etc). |

### OnUnitSpawned
{: .no_toc }
This event is fired whenever a unit is spawned. This event is fired with an `OnUnitSpawnedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Unit | spawnedUnit | The unit that was spawned. |
|Unit | spawningUnit | The unit that spawned the unit. Can be null if it was not spawned by a unit. |

### OnGoldAdded
{: .no_toc }
This event is fired whenever the player gains gold. This event is fired with an `OnGoldAddedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|float | goldAdded | The amount of gold that was added. |

### OnGoldRemoved
{: .no_toc }
This event is fired whenever the player loses gold. This event is fired with an `OnGoldRemovedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|float | goldRemoved | The amount of gold that was removed. |

### OnGoldPickedUp
{: .no_toc }
This event is fired whenever the player picks up gold. This event is fired with an `OnGoldPickedUpInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|float | goldPickedUp | The amount of gold that was picked up. |

### OnHealthPickedUp
{: .no_toc }
This event is fired whenever the player picks up a health globe. This event is fired with an `OnHealthPickedUpInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|float | healthPickedUp | The amount of health that was picked up. |

### OnItemEquipped
{: .no_toc }
This event is fired whenever the player equips an item. This event is fired with an `OnItemEquippedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Item | itemEquipped | The item that was equipped. |

### OnItemUnequipped
{: .no_toc }
This event is fired whenever the player unequips an item. This event is fired with an `OnItemUnequippedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Item | itemUnequipped | The item that was unequipped. |

### OnItemSold
{: .no_toc }
This event is fired whenever the player sells an item. This event is fired with an `OnItemSoldInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Item | itemSold | The item that was sold. |

### OnQuestUpdated
{: .no_toc }
This event is fired whenever a quest is updated. This event is fired with an `OnQuestUpdatedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Quest | questUpdated | The quest that was updated. |

### OnQuestCompleted
{: .no_toc }
This event is fired whenever a quest is completed. This event is fired with an `OnQuestCompletedInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Quest | questCompleted | The quest that was completed. |

### OnQuestAdded
{: .no_toc }
This event is fired whenever a quest is added to the quest system. This event is fired with an `OnQuestAddedInfo` object with the following variables:
 
|**Type** | **Variable** |**Description** |
|Quest | questAdded | The quest that was added. |

### OnGameWon
{: .no_toc }
This event is fired whenever the player wins the game. This event is fired with an `OnGameWonInfo` object with the following variables:

|**Type** | **Variable** |**Description** |
|Player | player | The player that won the game. |