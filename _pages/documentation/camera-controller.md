---
title: Camera Controller
layout: default
parent: Code Documentation
---

# Camera Controller
The Camera Controller class controls the game camera for the main experience.

## Repositioning the Camera
You can change the offset of the camera (including as its angle and distance from the player) by changing its location in the scene relative to the player. When the game starts, it will calculate the difference in location between the player and the camera and match this for the entire game.

## Highlighting Points of Interest
You can highlight points of interest in the game, which will allow you to pan to the given location.