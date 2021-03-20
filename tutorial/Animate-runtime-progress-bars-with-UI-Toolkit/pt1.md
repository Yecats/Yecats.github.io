---
layout: post
tutorial_title: Animate runtime progress bars with UI Toolkit
page_title:  Getting Started
date: 2021-03-19
author: Stacey
menubar: 
published: true
hide_footer: true
hero_height: is-small
comments: true
---
UI Toolkit ([formerly UI Elements](https://forum.unity.com/threads/renaming-uielements-to-ui-toolkit.854245/)) is Unity’s new UI system that can be used as an alternative to IMGUI (editor UI) and UIGUI (runtime UI). 

> UI Toolkit is still in preview, so some of the screenshots in this tutorial are likely to change as new releases occur.

## Download the project files
This tutorial relies on scripts and models that are included in the **starter project**. You can download the **starter project** by:

1. Clone and/or download the [GitHub repository](https://github.com/Yecats/GameDevTutorials). 
2. Navigate to the **Animate-runtime-progress-bars-UI-Toolkit\projects\starterProject** folder in Unity. 

You will see **Animations**, **Fonts**, **Models**, **Scenes**, **Scripts** and a **Sprites** folder in **Assets/WUG**. 

## Install UI Toolkit for runtime & UI Builder
UI Toolkit is now shipped via the Unity Editor. However, the features that are needed to use UI Toolkit at runtime require the installation of the latest package. Since the package is not discoverable in the editor, you will need to add it by doing the following:

1.	Go to **Window** > **Package Manager**.
2.	Click on the **+** button and choose **Add Package from git URL**.
3.	Enter the following URL: **com.unity.ui**.

![]({{page.dir}}/images/1-gs-packagemanager.gif)

You will need to install UI Builder if you are on an editor version earlier than 2021.1:

1.	First make sure **Preview Packages** is turned on by going to **Project Settings** > **Package Manager**. Check **Enable Preview Packages** under the **Advanced Settings** section.
2.	Back in **Package Manager**, search for **UI Builder** and click **Install**.

> As of the writing of this tutorial, there is a bug when first installing the UI Toolkit package that requires you to restart Unity. You will know that this still applies if you get a series of console errors after installing.

## Install DOTween
[DOTween](http://dotween.demigiant.com/) is an awesome tool that you can use to script animations using C#. It supports just about anything, or at least anything I have tried to animate. :D DOTween was created by Demigiant and is available on the Unity Asset Store. There is a free version and a pro version, which comes with extra features including a visual editor. This project will use the free version. Install it by:

1.	Navigate to the [DOTween Asset Store page](https://assetstore.unity.com/packages/tools/animation/dotween-hotween-v2-27676) and login.
2.	Click the **Add to My Assets** button. 
3.	In the **Unity Editor**, open **Package Manager** and change the **Package** filter from **Unity Registry** to **My Assets**.
4.	Select **DoTween (HOTween v2)** and click **Install**.

![]({{page.dir}}/images/pt1-store.gif)

Once installed, DoTween will pop up a wizard that will guide you through setting it up in your project. The most important thing to do is click on the **Setup DOTween…** button, leave all of the modules unchecked, and click **apply**. 

