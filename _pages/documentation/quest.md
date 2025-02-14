---
title: Quest Documentation
layout: default
parent: Code Documentation
---

# The Quest Class
{: .no_toc }
The quest class is used to create and control quests. The Quest class does **not** inherit from MonoBehaviour, so quests are not components which can be added to your scenes. Instead, you should use the methods described below to control quests (or use the visual scripting system).

{: .note }
You are not required to write any code in this unit. It is recommended that you instead use the provided visual scripting system in this unit. If you want to implement logic that cannot easily be handled by that system though, this documentation should help you better understand the code and classes in the project.


---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

## Creating a Quest
```csharp
// Create the quest with a basic label.
Quest quest = new Quest("Skill Training");

// Add a requirement to the quest.
quest.AddCompletionRequirement("Use the Cleave Ability");

// Alternatively, if you want it to have multiple progress increments, specify that number here.
quest.AddCompletionRequirement("Use the Cleave Ability", 5);

// Specify the reward for the quest. This is just a label, you must code the specific reward logic
// when the quest is completed.
quest.SetReward("Legendary Item");
```

## Activating a Quest
Even if you create a quest object, it is not 'active' until it is has been added to the quest system. This means that you can create all of the quests at the start of the level, and then only give them to the player when appropriate conditions are met.

To add a quest to the quest system, use the following code:

```csharp
GameManager.quests.AddQuest(quest);
```

## Deactivating a Quest
If you want to remove a quest that has already been assigned to the player, you can use a similar command:

```csharp
GameManager.quests.RemoveQuest(quest);
```

## Updating Quest Progress
```csharp
// Increments the quest requirement by a single increment. This can only be used
// if the quest contains a single increment (otherwise it doesn't know which to
// increment).
quest.IncrementProgress();

// Increments the quest requirement by the given number of progress increments.
quest.IncrementProgress(5);

// Sets the quest progress to a specific value. This is helpful when the requirement
// isn't going up and down in a steady way. E.g., if the quest completes when the player
// gets 500 gold, this should dynamically update to a specific value whenever the player
// gains or loses gold.
quest.SetProgress((int)GameManager.player.currentGold);

// Decrements the quest requirement by a single value.
quest.DecrementProgress();

// If the quest has multiple completion requirements, you need to specify the label for
// the requirement when incrementing it.
quest.IncrementProgress("SpecificRequirement", 2);
```

## Checking Quest States
You can request information about the current quests with the following methods:

```csharp
// Check to see if a quest is currently active.
bool questIsActive = GameManager.quests.QuestIsActive(quest);

// Alternatively, you can use the quest name instead.
bool questIsActive = GameManager.quests.QuestIsActive("QuestName");

// Check to see if a quest has been completed.
bool questIsCompleted = GameManager.quests.QuestIsCompleted(quest);

// Alternatively, use the quest name instead.
bool questIsCompleted = GameManager.quests.QuestIsCompleted("QuestName");
```

## Completing a Quest
A quest will **automatically** be completed when all of the requirements have been met. If you are wanting to perform actions when the quest completes (e.g., providing the quest reward), you should use the provided events to execute the quest completion logic.


