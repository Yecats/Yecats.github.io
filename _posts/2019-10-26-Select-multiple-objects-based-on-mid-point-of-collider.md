---
layout: post
tutorial_title: How to select multiple objects based on the center of a collider
page_title:  "Introduction"
date:   2019-10-26
author: Stacey Haffner
short-description: "Select multiple game objects "
long-description: Learn how to create an RTS/RPG “drag-to-select multiple characters” game mechanic without using raycasts to detect collisions. Instead, we’ll use the center point of the collider’s bounds to detect if it is within the radius of a panel drawn on the UI via the mouse start/end positions. This approach supports perspective camera setups and a can be altered to use any vector3 point.
menubar: menu-select-multiple-objects-based-on-mid-point-of-collider
repo_Link: /Unity/Select-multiple-objects-based-on-center-of-collider
folder_path: Select-multiple-objects-based-on-center-of-collider
image: pt-5-4-final-demo.gif
tags: unity input-system C# ui mouse-events
published: true
include_header: true
hide_footer: true
hero_height: is-small
---

> This tutorial was created with Unity version 2019.2.

Learn how to create an RTS/RPG "drag-to-select multiple characters" game mechanic without using raycasts to detect collisions. Instead, we'll use the center point of the collider's bounds to detect if it is within the radius of a panel drawn on the UI via the mouse start/end positions. This approach supports perspective camera setups and a can be altered to use any vector3 point. 

## Learning Outcomes

1. Continue to work with the Input System by setting up more action / binding mappings.
2. Understand what the colliders "bounds" is and how you can work with it to get useful information.
3. Learn about the different 'spaces' (Screen, World, Local) within Unity. 
4. Learn how to convert a world point to UI screen space. 

## Prerequisites
This is a continuation of the [Listen for the Input System Action events via CSharp]({{site.baseurl}}/2019/10/19/Listen-for-the-Input-System-Action-events-via-CSharp.html) tutorial, which is part two of the Input System series. You can skip previous tutorials by cloning the **starterProject** in the repository.

> Note: This tutorial will not cover previous topics in depth (such as how the Input Manager works). It is recommended that you start from the beginning of the series if you are missing any concepts. 

![Demo of Final Result]({{site.baseurl}}/tutorial/Select-multiple-objects-based-on-center-of-collider/images/pt-5-4-final-demo.gif)

## Previous Tutorials in this Series
1. Part 2: [Listen for the Input System Action events via CSharp]({{site.baseurl}}/2019/10/19/Listen-for-the-Input-System-Action-events-via-CSharp.html)
2. Part 1: [How to make a configurable camera with the new Input System]({{site.baseurl}}/2019/10/17/How-to-make-a-configurable-camera-with-the-new-Input-System.html)

## Resources
1. Comments, concerns and/or questions can be posted [here](https://github.com/Yecats/GameDevTutorials/issues/4).
2. This project uses the [Low Poly: Free Pack](https://www.assetstore.unity3d.com/en/#!/content/58821) by AxeyWorks.

