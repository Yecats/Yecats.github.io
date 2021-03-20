---
layout: post
tutorial_title: Animate runtime progress bars with UI Toolkit
page_title:  Design 1 - Add the UI to the game
date: 2021-03-19
author: Stacey
menubar: menu-Animate-runtime-progress-bars-with-UI-Toolkit
published: true
hide_footer: true
hero_height: is-small
comments: true
---
Before you can add this to your game, you will need a full screen UI Container. In UI Builder, go to **File** > **New**.  Click on **<unsaved window>.uxml** in the **Hierarchy window** and enable **Match Game View**.  This property will automatically set the width and the height of the UI to match the game window.

Next, you will add the progress bar to the center of the screen. In the **Library** section, click on the **Project** tab and expand the tree view until you find **Progressbar_Straight_Border.uxml**. Drag it into the Hierarchy. Click on it, and set the following properties:

1. **Flex** > **Grow**: 1
2. **Align** > **Align Items**: center
3. **Align** > **Justify Content**: center

Save the file and call it **LoadScreen**.

> You may want to have the loading progress bar appear on top of a nice full screen image. To do this, first add a new **VisualElement** to the **LoadScreen** root and set **Background** > **Image** to your sprite. **Progressbar_Straight_Border** should be a child of your new **VisualElement**.

![]({{page.dir}}/images/4-game-screen.gif)

## Display the progress bar in your scene

UI Toolkit comes with a new component/game object type called **UI Document**. Add it to a new, empty scene by going **GameObject** > **UI Toolkit** > **UI Document**. Rename it to **ProgressBar**. 

In your scene, you should now see a game object with a **UI Document** component. The Component has three properties:

1. **Panel Settings**: The panel is the root VisualElement that all UI Documents are attached to. It is what handles drawing the UI in the Scene at runtime. The Panel Settings file has various properties that you can set which impact runtime.
2. **Source Asset**:  Reference to UXML files that should be associated with the panel (root VIsualElement). You can have multiple of these.
3. **Sort Order**: Specifies the order that this UI document will show up in relation to other UI documents that are part of the same PanelSettings or UI Document parent.

There is only one property to change. Set **Source Asset** to **LoadScreen**. Push **play** and you should now see a static progress bar on the bottom of your Game window.

![]({{page.dir}}/images/4-in-game.png)

