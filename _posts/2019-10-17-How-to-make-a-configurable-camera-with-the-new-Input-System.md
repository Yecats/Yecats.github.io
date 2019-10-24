---
layout: post
tutorial_title: How to make a configurable camera with the new Unity Input System
page_title:  "Introduction"
date:   2019-10-17
author: Stacey Haffner
short-description: "Learn the new Unity Input System (currently in preview) while creating a configurable camera that can be used in your game."
long-description: Build a configurable camera that handles moving, zooming and rotating. This design works great for games that do not want an attached 3rd or 1st person camera, but instead want freedom to move around a scene. Instead of using the old input system, we’ll be hooking it up to the new one and will review key concepts as we go.
image: FinishedExample.gif
menubar: menu_How-to-make-a-configurable-camera-with-the-new-Input-System
repo_Link: /Unity/How-to-make-a-configurable-camera-with-the-new-Input-System/projects
folder_path: How-to-make-a-configurable-camera-with-the-new-Input-System
tags: unity input-system C#
published: true
include_header: true
hide_footer: true
hero_height: is-small
---

> This tutorial was created with Unity version 2019.2.

In this tutorial, you’re going to build a configurable camera that handles moving, zooming and rotating. This design works great for games that do not want an attached 3rd or 1st person camera, but instead want freedom to move around a scene. Instead of using the old input system, we’ll be hooking it up to the new one and will review key concepts as we go.

Configuration features of the camera are:

1. Camera angle
2. Zoom min/max
3. Zoom default
4. Look offset (where you want the camera to focus on the y axis)
5. Rotation speed

## Learning Outcomes

> You can clone this repository to get the starter project and follow along!  

1. Understand key concepts of the new Input System. 
2. Have a configurable camera that can be customized for your game.

## Prerequisites
This tutorial assumes you have basic knowledge of how Unity works. It does not cover the basics, such as what a GameObject is, a component, when Start is called, etc. 

![Demo of Final Result]({{site.baseurl}}/tutorial/How-to-make-a-configurable-camera-with-the-new-Input-System/images/FinishedExample.gif)

## Resources
1. Comments, concerns and/or questions can be posted [here](https://github.com/Yecats/GameDevTutorials/issues/1).
2.	Input System [documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.0/manual/index.html) and [GitHub repository](https://github.com/Unity-Technologies/InputSystem).
3. [Introducing the new Input System - Unite Copenhagen Video](https://youtu.be/hw3Gk5PoZ6A)
1. This project uses the [Low Poly: Free Pack](https://www.assetstore.unity3d.com/en/#!/content/58821) by AxeyWorks.

