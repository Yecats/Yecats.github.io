---
layout: post
tutorial_title: Animate runtime progress bars with UI Toolkit
page_title:  Design 1 - Loading Progress Bar
date: 2021-03-19
author: Stacey
menubar: 
published: true
hide_footer: true
hero_height: is-small
comments: true
---
# Design 1: Loading Progress Bar
Now it is time to create the first progress bar. This is a basic square progress bar made entirely using properties with UI Toolkit. In other words, there is no sprites just yet. Here is what you will be building:

![]({{page.dir}}/images/3-final-result-not-animated.png)

Inside UI Builder, click on the first item in the **Hierarchy window**, called **<unsaved window>.uxml**. This pulls up the base properties in the Inspector window. Set the **width** to **360** and the **height** to **130**. 

Drag a **VisualElement** from the library and drop it in the Hierarchy window. Click on it to pull up the properties. Set the following:

1. **Name**: Container
2. **Size** > **Width**: 350 px

Drag another **VisualElement** into the hierarchy window and make it a **child of the Container**. Set the following properties:

1. **Name**: Container_Header
2. **Flex** > **Direction**: row 
3. **Text** > **Font**: Recursive
4. ** Text** > **Size**: 25px.

Add a **Label** control as a **child of Container_Header**. Set the following properties:

1. **Name**: txt_Loading
2. **Text**: LOADING….
3. **Flex** > **Grow**: 1 
4. **Font Style**: Bold
5. **Text** > **Color**: # 00E6FF

Add a ** Label** control as the **last child of Container_Header**. Set the following properties:

1. **Name**: txt_Percentage
2. **Text**: 0%
3. **Font Style**: Italic
4. **Text** > **Color**: # 00E6FF

Add another **VisualElement** as the **last child of Container**. Set the following properties:

1. **Name**: Container_Bar
2. **Size** > **Height**: 75px
3. **Border** > **Color**: # 00E6FF
4. **Border** > **Width**: 3px

Add one final **VisualElement** as the **last child of Container_Bar**. Set the following properties:

1. **Name**: bar_Progress
2. **Size** > **Height**: 100%
3. **Size** > **Width**: 0%
3. **Margin & Padding** > **Margin**: 10px
4. **Background** > **Color**: # 00E6FF


**Save** your UXML document by going to **File** > **Save As** at the top of the **Viewport** section and name it **Progressbar_Straight_Border**.  You should now have a window that looks like this if you were to set the width of b_Progress to 100% and the percentage text to 85%:

![]({{page.dir}}/images/3-final-result-in-ui-builder.png)

> This tutorial is using In-line styles. If you’d like to organize a bit more using stylesheets or learn more about the post common properties, check out [Create the stylesheet](https://yecats.github.io/tutorial/Create-an-Inventory-UI-with-UI-Toolkit/pt3.html) section in [Create an in-game Inventory UI with UI Toolkit](https://yecats.github.io/2021/02/02/Create-an-in-game-inventory-with-UI-Toolkit.html). 

> The layout engine that UI Toolkit uses is the open source project called  [Yoga](https://github.com/facebook/yoga), which implements a subset of Flexbox. Flexbox is an HTML/CSS based layout system. A useful guide to Flexbox can be found [here](https://css-tricks.com/snippets/css/a-guide-to-flexbox/).

