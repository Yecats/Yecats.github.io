---
layout: post
tutorial_title: Create an in-game Inventory UI with UI Toolkit
page_title:  "Design the Inventory UI"
date:   2021-02-02
author: Stacey Haffner
published: true
menubar: menu-create-inventory-ui-toolkit
hide_footer: true
hero_height: is-small
comments: false
---
UI Builder is a way to visually create and edit UXML and USS files. It is also highly useful if you are creating your assets via code and want to mockup how something might look or to see what the proper syntax is for a style variable. Open the window by going to **Window** > **UI Toolkit** > **UI Builder**.

UI Builder is broken out into six different sections:

1. **StyleSheets**: Manage the stylesheets and individual selectors that are used in this document. Style Sheets can be shared across multiple documents, thereby maximizing reusability.
1. **Hierarchy**: A list of all elements that are within the document. 
1. **Library**: Contains a list of standard elements that can be instantiated. The **Standard** tab contains UI Documents from Unity. The **Project** tab contains UI Documents created in your project.
1. **Viewport**: Visual of the UI document. 
1. **Inspector**: Contains modifiable attributes and style properties for the element currently selected in the hierarchy or StyleSheet sections.
1. **Code Preview**: Displays the UXML and USS code that UI Builder is generating based on your decisions. 

![]({{page.dir}}/images/2-design-ui-builder-overview.png)

Now it’s time to create the Inventory UI. Inside UI Builder, click on the first item in the **Hierarchy window**, called **<<unsaved window>>.uxml**. This pulls up the base properties. Check the **Match Game View** checkbox. This ensures that the UI scales with the screen.

![]({{page.dir}}/images/2-design-match-game-view.png)

Next, Drag VisualElement from the library and drop it in the Hierarchy window. Click on it to pull up the properties. Set the following:

1. **Name**: Container
2. **Flex** > **Grow** is **1**.
3. **Align** > **Align Items**: center
4. **Align** > **Justify Content**: center

Drag another **VisualElement** into the hierarchy window and make it a **child of the Container**. Set the following properties:

1. **Name**: Inventory
2. **Flex** > **Grow** is **1**
2. **Size** > **Width & Height**: 50% and 75%
2. **Size** > **Max** > **Width & Height**: 50% and 75%
2. **Margin & Padding** > **Padding**: 10px
2. **Background** > **Color**: #1C2024
2. **Border** > **Color** > Top: #FFC500
2. **Border** > **Width** > Top: 5

Add a **Label** control as a **child of Inventory**. Set the following properties:

1. **Name**: Header
1. **Text**: Inventory
1. **Text** > **Size**: 24
1. **Text** > **Color**: #FFC500
1. **Margin & Padding** > **Margin** > **Bottom** >: 10px
1. **Border** > **Color** > **Bottom**: #404A52
1. **Border** > **Width** > **Bottom**: 1

Add a **VisualElement** control as a **child of Inventory**. Set the following properties:

1. **Name**: SlotContainer
1. **Flex** > **Grow** is **1**.
1. **Flex** > **Direction**: Row
1. **Flex** > **Wrap**: Wrap
1. **Align** > **Justify Content**:  center

**Save** your UXML document by going to **File** > **Save As** at the top of the **Viewport** section and name it **Inventory**. You should now have a window that looks like this:

![]({{page.dir}}/images/2-design-final.png)

> The layout engine that UI Toolkit uses is the open source project called  [Yoga](https://github.com/facebook/yoga), which implements a subset of Flexbox. Flexbox is an HTML/CSS based layout system. A useful guide to Flexbox can be found [here](https://css-tricks.com/snippets/css/a-guide-to-flexbox/).