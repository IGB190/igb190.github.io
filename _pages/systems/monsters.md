---
title: Monsters
layout: default
parent: Systems
---

# Monsters
{: .no_toc }
In this guide, you will learn how to create and implement custom monsters into your experience.

---
<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}
---

## Monster Overview
...

## Finding a Character Model
In this unit, you will not have the time to model and rig your own character. Instead, you should source a custom character from online. You should consider looking at sources such as the Unity Asset Store or Mixamo (which is where the three current characters were found).

![Image of Mixamo Characters](../assets/mixamo-characters.jpg)

Once you have found a character, you will need to then download it and import it into your Unity project.

## Creating the Character
Rather than building a monster "from scratch", it is much faster to instead copy an existing monster. Choose a Monster in the project (Monsters are found under `Assets to Use > Monsters`) and duplicate it by pressing `Control+D`. Rename the new monster to your desired name.

Double click on the Monster prefab to open it in the prefab editor. Expand the monster so that you can see the existing model, then delete it. Drag in your new model and ensure that it is positioned at `X=0, Y=0, Z=0` and has a rotation of `X=0, Y=0, Z=0`.

Select your new monster model. It should have an Animator component on it. Replace the `Controller` of the `Animator` component with the `Skeleton Override Controller` (this can be found at `Core > Animator Controllers > Skeleton Overvide Controller`).

{: .important-title }
> Creating Your Own Animator
>
> If you want your custom monster to have unique animations, you can create a new animator override for it. Right click in your assets folder and select `Create > Animation > Animator Override Controller`. Then, in the `Controller` slot, drag in the `Player Animator` (which is found at `Core > Animator Controllers > Player Animator`). You can now replace any of the animations used by the player with custom ones specific to your unique monster.

## Changing the Monster Stats
To change the monster's stats, select the Monster and go to the `Monster` component in the inspector. This component manages all of the stats and abilities for the monster.