---
layout: post
tutorial_title: Get started with Behavior Trees
page_title:  "Introduction"
date:   2020-11-16
author: Stacey Haffner
short-description: "Select multiple game objects "
long-description: Write an AI that will pick up all objects in the scene by navigating to random way points. At the end of this tutorial you will have fundamental knowledge of how a behavior tree works and will have created foundational nodes that can be reused in all your future projects.
menubar: menu_Get-started-with-behavior-trees
repo_Link: /Unity/Get-started-with-behavior-trees
folder_path: Get-started-with-behavior-trees
image: treeExample.gif
tags: unity AI artificial-intelligence behavior-trees C#
published: true
include_header: true
hide_footer: true
hero_height: is-small
comments: true
---

# Get started with Behavior Trees

> You will need Unity 2020.1.13f1 to follow along. This tutorial assumes knowledge of C# and Unity.

> This tutorial uses [Behavior Tree Visualizer](https://github.com/Yecats/UnityBehaviorTreeVisualizer), an open source tool to help view and debug trees.

Writing a good AI is challenging for many reasons. Not only do you need it to be believable but also easy to maintain. It can grow along side your game, getting more complex as each new feature is added. Behavior trees are an AI technique designed for just that! It is a modular AI framework that works great for more complex AI logic. 

You will write an AI that will pick up all objects in the scene by navigating to random way points. At the end of this tutorial you will have fundamental knowledge of how a behavior tree works and will have created foundational nodes that can be reused in all your future projects.

![BTG Example]({{site.baseurl}}/tutorial/Get-started-with-behavior-trees/images/treeExample.gif)

## Learning Outcomes 
You will learn:

- What a Behavior Tree is.
- About the guiding principles of a Behavior Tree.
- The different types of nodes and their purposes.
- How to create the fundamental nodes using inheritance.
- How to drive the AI behavior within Unity.

## Prerequisites

1. Knowledge of C#.
2. Unity 2020.1.0f1 should be installed.
3. Download the starter project from the [GitHub repository](https://github.com/Yecats/GameDevTutorials).

## Resources

1. [Behavior Tree Visualizer](https://github.com/Yecats/UnityBehaviorTreeVisualizer)