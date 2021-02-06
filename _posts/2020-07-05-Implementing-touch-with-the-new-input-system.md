---
layout: post
tutorial_title: Implementing touch with Input System's Enhanced Touch API
page_title:  "Introduction"
date:   2020-07-05
author: Stacey
short-description: "Select multiple game objects "
long-description: User input is a core pillar of an interactive and engaging experience. Once you collect it, it's important you present an experience that feels natural and intuitive to the player. In this tutorial, you'll cover the basics of the new Unity Input System by creating a demo project that can Place a 3D model by dragging it off the User Interface (UI) and dropping it into the world as well as move/zoom the camera.
menubar: menu_Implementing-touch-with-the-new-input-system
repo_Link: /Unity/Implementing-touch-with-the-new-input-system
folder_path: Implementing-touch-with-the-new-input-system
image: finalBuild.gif
tags: unity input-system C# ui touch-events enhancedTouch-API
published: true
include_header: true
hide_footer: true
hero_height: is-small
comments: true
---

> This tutorial was created with Unity version 2019.4.

User input is a core pillar of an interactive and engaging experience. Once you collect it, it's important you present an experience that feels natural and intuitive to the player. In this tutorial, you'll cover the basics of the new **Unity Input System** by creating a demo project that can:

-   Place a 3D model by dragging it off the User Interface (UI) and dropping it into the world.
-   Move the camera by dragging one finger.
-   Zoom the camera by pinching two fingers.

![Demo of Final Result]({{site.baseurl}}/tutorial/Implementing-touch-with-the-new-input-system/images/finalBuild.gif)

## Learning Outcomes 

You'll learn how to:

-   Install the new Input System's package.
-   Enable Touch Simulation mode.
-   Collect and process touch input via the [EnhancedTouch](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.0/api/UnityEngine.InputSystem.EnhancedTouch.html) API.
-   Route Input System events to the UI.

## Prerequisites

1. This tutorial assumes you already have basic knowledge of Unity and intermediate knowledge of C#. 
2. You need [Unity 2019.4](https://unity3d.com/get-unity/download) or later to follow along with this tutorial. 
3. While you can enable simulation mode for testing, the behavior is unpredictable and only simulates a single touch. As a result, you also need a touch device to complete this tutorial.

## Resources

1. Comments, concerns and/or questions can be posted [here](https://github.com/Yecats/GameDevTutorials/issues/6).
2. Check out [How to make a configurable camera with the new Unity Input System](https://yecats.github.io/2019/10/17/How-to-make-a-configurable-camera-with-the-new-Input-System.html) if you want to learn more about Action Assets. You'll build the camera rig used in this tutorial from scratch. 
3. You can also check out [Inventory and Store System - Part 3 (Creating the Store UI)](https://channel9.msdn.com/Shows/dotGAME/Inventory-and-Store-System-Part-3-UI) for a deeper look at the UI system. 
4. Input System [documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.0/manual/index.html) and [GitHub repository](https://github.com/Unity-Technologies/InputSystem).
5. The models in this tutorial are from [What Up Games, LLC](http://whatupgames.com/) and the UI icons are from [Game-Icons.net](https://game-icons.net/).

