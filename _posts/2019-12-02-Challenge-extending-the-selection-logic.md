---
layout: post
tutorial_title: Challenge Solution - Extending the selection logic
page_title: "Introduction"
date: 2019-12-10
author: Stacey Haffner
short-description: "Extend the RTS/RPG “drag-to-select multiple characters” game mechanic."
long-description: Extends the RTS/RPG “drag-to-select multiple characters” game mechanic by adding additional support for routine player actions. Players will be able to add/remove objects to an existing selection and clear the entire selection with a single button click. This tutorial coninues use of the new Unity input system.
menubar: menu-challenge-extending-selection-logic
repo_Link: /Unity/Challenge-review-select-multiple-objects-with-shift
folder_path: challenge-extending-selection-logic
image: 
tags: unity input-system C# ui mouse-events
published: true
include_header: true
hide_footer: true
hero_height: is-small
comments: true
---

> This tutorial was created with Unity version 2019.2.

A challenge was issued at the end of the [How to select multiple objects based on the center of a collider]({{site.baseurl}}/2019/10/26/Select-multiple-objects-based-on-mid-point-of-collider.html) tutorial to extend the mechanic by adding the ability to add/remove objects from an existing selection and clear the selection with a button click. This tutorial walks through how I chose to solve that challenge.

## Learning Outcomes

1. Apply knowledge gained from the tutorial series.

## Prerequisites
This is a continuation of the [How to select multiple objects based on the center of a collider]({{site.baseurl}}/2019/10/26/Select-multiple-objects-based-on-mid-point-of-collider.html) tutorial, which is part two of the Input System series. You can skip previous tutorials by cloning the **starterProject** in the repository.

> Note: This tutorial will not cover previous topics in depth (such as how the Input Manager works). It is recommended that you start from the beginning of the series if you are missing any concepts. 

![Demo of Final Result]({{site.baseurl}}/tutorial/challenge-extending-selection-logic/images/final.gif)

## Tutorials in this Series
1. Part 1: [How to make a configurable camera with the new Input System]({{site.baseurl}}/2019/10/17/How-to-make-a-configurable-camera-with-the-new-Input-System.html)
2. Part 2: [Listen for the Input System Action events via CSharp]({{site.baseurl}}/2019/10/19/Listen-for-the-Input-System-Action-events-via-CSharp.html)
3. Part 3: [How to select multiple objects based on the center of a collider]({{site.baseurl}}/2019/10/26/Select-multiple-objects-based-on-mid-point-of-collider.html)
4. Part 4:  [Challenge Solution: Extending the selection logic]({{site.baseurl}}/2019/12/02/2019-12-02-Challenge-extending-the-selection-logic.html)

## Resources
1. This project uses the [Low Poly: Free Pack](https://www.assetstore.unity3d.com/en/#!/content/58821) by AxeyWorks.