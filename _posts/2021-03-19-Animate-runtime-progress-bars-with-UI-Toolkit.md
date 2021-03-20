---
layout: post
tutorial_title: Animate runtime progress bars with UI Toolkit
page_title:  Introduction
date: 2021-03-19
author: Stacey
short-description: Learn how to animate UI Toolkit runtime elements by creating two in-game progress bars.
long-description: A lot goes into creating an intuitive experience for your player. Progress bars are often used to reassure the player that something is happening (such as the game loading) or give them an idea on how long something will take. In this tutorial, you will learn some techniques for creating and animating progress bars using UI Toolkit and DOTween.
image: 1-final.gif
menubar: menu-Animate-runtime-progress-bars-with-UI-Toolkit
repo_Link: Unity/Animate-runtime-progress-bars-with-UI-Toolkit
folder_path: Animate-runtime-progress-bars-with-UI-Toolkit
tags: unity c# ui-toolkit ui animation
published: true
include_header: true
hide_footer: true
hero_height: is-small
comments: true
---
A lot goes into creating an intuitive experience for your player and one of the more common one is a progress bar. Progress bars often appear on loading screens or when the character is doing a long action that the player must wait for. In this tutorial, you will learn some techniques for creating and animating progress bars using UI Toolkit and DOTween.

![Example]({{site.baseurl}}/tutorial/Animate-runtime-progress-bars-with-UI-Toolkit/images/1-final.gif)

## Learning Outcomes
UI Toolkit does not have the ability to do masking, nor does it hook directly into the Animation system. You will learn techniques for working around these two limitations. At the end of the tutorial, you will be able to:

1.	Design UIs by using the UI Builder tool.
2.	Add a runtime UI to your game.
3.	Animate the UI through DOTween
4.	Hook up DOTween animations to trigger at specific points of a “regular” animation.

## Prerequisites

1.	You need [Unity 2020.3.0f1 (LTS)](https://unity3d.com/get-unity/download) or later to follow along with this tutorial.
2.	This tutorial assumes you already have basic knowledge of Unity and intermediate knowledge of C#.

> Tutorials may work with earlier versions. The version referenced is the on I used.

## Resources

1. [Unity Manual: UI Toolkit](https://docs.unity3d.com/2020.1/Documentation/Manual/UIElements.html)
2. [Unity Manual: UI Event System](https://docs.unity3d.com/2020.1/Documentation/Manual/UIE-Events.html)
3. [Unity Manual: UI Builder](https://docs.unity3d.com/Packages/com.unity.ui.builder@1.0/manual/index.html)
4. [DOTween Documentation](http://dotween.demigiant.com/documentation.php)

