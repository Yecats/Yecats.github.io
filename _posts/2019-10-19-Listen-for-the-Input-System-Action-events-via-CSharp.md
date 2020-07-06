---
layout: post
tutorial_title: Listen for the Input System's Action events via C#
page_title:  "Introduction"
date:   2019-10-19
author: Stacey Haffner
short-description: "Learn the new Unity Input System (currently in preview) while creating a configurable camera that can be used in your game."
long-description: In certain scenarios it may be beneficial to listen for Input System Action callbacks via C#, rather than using the built in Player Input component. This tutorial will walk through writing an `InputManager` script to listen for and route such events. This is a continuation of the How to make a configurable camera with the new Input System tutorial, which covers fundamental knowledge of the Input System.
menubar: menu_listen-for-input-system-events-via-csharp
repo_Link: /Unity/Listen-for-Input-System-events-via-CSharp/projects
folder_path: Listen-for-Input-System-events-via-CSharp
tags: unity input-system C#
published: true
include_header: true
hide_footer: true
hero_height: is-small
comments: true
---

> This tutorial was created with Unity version 2019.2.

In certain scenarios it may be beneficial to listen for Input System Action callbacks via C#, rather than using the built in Player Input component. This tutorial will walk through writing an `InputManager` script to listen for and route such events. 

## Learning Outcomes
1. Understand the different Input System Action callbacks and how to hook them up via C# 

## Prerequisites
This is a continuation of the [How to make a configurable camera with the new Input System]({{site.baseurl}}/2019/10/17/How-to-make-a-configurable-camera-with-the-new-Input-System.html) tutorial, which covers fundamental knowledge of the Input System. While not recommended (unless you are already familiar with the Input System) you can skip tutorial by cloning the **starterProject** in the repository.

## Tutorials in this Series
1. Part 1: [How to make a configurable camera with the new Input System]({{site.baseurl}}/2019/10/17/How-to-make-a-configurable-camera-with-the-new-Input-System.html)
2. Part 2: [Listen for the Input System Action events via CSharp]({{site.baseurl}}/2019/10/19/Listen-for-the-Input-System-Action-events-via-CSharp.html)
3. Part 3: [How to select multiple objects based on the center of a collider]({{site.baseurl}}/2019/10/26/Select-multiple-objects-based-on-mid-point-of-collider.html)
4. Part 4:  [Challenge Solution: Extending the selection logic]({{site.baseurl}}/2019/12/10/Challenge-extending-the-selection-logic.html)

## Resources
1.	Input System [documentation](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.0/manual/index.html) and [GitHub repository](https://github.com/Unity-Technologies/InputSystem).
2. [Introducing the new Input System - Unite Copenhagen Video](https://youtu.be/hw3Gk5PoZ6A)
3. This project uses the [Low Poly: Free Pack](https://www.assetstore.unity3d.com/en/#!/content/58821) by AxeyWorks.

