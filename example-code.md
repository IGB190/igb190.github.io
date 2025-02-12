---
title: Coding
layout: default
---

# Example Item Code 2
While you are not required to write any code in the development of your experience, if you need to implement complex logic for an item, ability, quest, or other game mechanic, this section will show you how it can be done. This page will focus specifically on how you can build an item with custom logic.





The experience can be developed without any code, but if you do want to use code to develop your items, abilities, quests or other content to control complex logic which cannot easi


<h2 class="text-delta">Contents</h2>
1. TOC
{:toc}




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