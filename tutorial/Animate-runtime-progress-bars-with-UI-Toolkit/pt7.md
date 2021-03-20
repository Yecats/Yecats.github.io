---
layout: post
tutorial_title: Animate runtime progress bars with UI Toolkit
page_title:  Design 2 - Add the UI to the game
date: 2021-03-19
author: Stacey
menubar: 
published: true
hide_footer: true
hero_height: is-small
comments: true
---
Once again, you will need a full screen UI Container. In UI Builder, go to **File** > **New**.  Click on **<unsaved window>.uxml** in the **Hierarchy window** and enable **Match Game View**. 

Next, you will add the circular bar to the bottom of the screen. In the **Library** section, click on the **Project** tab and expand the tree view until you find **Progressbar_Circular.uxml**. Drag it into the Hierarchy. Click on it, and set the following properties:

1. **Flex** > **Grow**: 1
2. **Align** > **Align Items**: center
3. **Align** > **Justify Content**: bottom
4. **Margin & Padding** > **Margin** > **Bottom**: 20px

Save the file and call it **GameScreen**.

![]({{page.dir}}/images/6-game-screen.png) 

Hop back into your scene and click on the ProgressBar game object. This is where the **UI Document** component and `CircularProgressBarAnimation` script live. Set the **UI Document** > **Source Asset** reference to **GameScreen**.

