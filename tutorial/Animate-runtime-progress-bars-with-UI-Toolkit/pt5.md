---
layout: post
tutorial_title: Animate runtime progress bars with UI Toolkit
page_title:  Design 1 - Animate the progress bar
date: 2021-03-19
author: Stacey
menubar: 
published: true
hide_footer: true
hero_height: is-small
comments: true
---
# Design 1: Animate the progress bar
I have found that there are two main ways to animate the new UI, depending on the complexity of what you need to do. The first is with the experimental animation functionality that comes built in with UI Toolkit. The second is using a free (but with a paid option) tool called DOTween. For this tutorial, you will use DOTween as you will be animating both the scale of the bar and the text value of the label. 

> The experimental animation features currently only support Layout, Position, Rotation, Scale, Size and animating float style properties. You can read more on the API [here]( https://docs.unity3d.com/ScriptReference/UIElements.Experimental.ITransitionAnimations.html)
Create a new script called **LoadingProgressBarAnimation**. This is where you will write the code for animating both of your progress bars. Add the following new references:

```csharp
using UnityEngine;
using UnityEngine.UIElements;
using DG.Tweening;
```

Next add some global variables and a Start method:

```csharp
private VisualElement m_Root;
private VisualElement m_LoadingProgressBar;
private Label m_LoadingPercentageText;

void Start()
{
    //Grab a reference to the root element that is drawn
    m_Root = GetComponent<UIDocument>().rootVisualElement;

    //Search the root for the two dynamic elements that need to be animated
    m_LoadingProgressBar = m_Root.Q<VisualElement>("bar_Progress");
    m_LoadingPercentageText = m_Root.Q<Label>("txt_Percentage");
}
```
Start is doing two important things:

1. m_Root is getting the root Visual Element from the UIDocument component for easy access later.
2. m_ProgressBar and m_PercentageText references are set by querying m_Root based on the element type and name. 

> You can use either Q or Query to search for a specific element within the hierarchy. Providing either the type or the name is optional. You can also return the first result of the query by appending .First() at the end and the last by appending .Last(). For example: `m_ProgressBar = m_Root.Q<VisualElement>("bar_Progress").First();`

Finally, add a new `AnimateLoadingBar()` method, with the following code:

```csharp
private void AnimateLoadingBar()
{
    //Grab the final width of the progress bar based on the parent and
    //remove 25px to account for margins
    float endWidth = m_LoadingProgressBar.parent.worldBound.width - 25;

    DOTween.To(() => 5, x=> m_LoadingPercentageText.text = $"{x}%", 
        100, 5f).SetEase(Ease.Linear);
    
    DOTween.To(() => m_LoadingProgressBar.worldBound.width, x =>
        m_LoadingProgressBar.style.width = x, endWidth, 5f).SetEase(Ease.Linear);
}
```

As mentioned before, DOTween is a very versatile way to animate objects in C#. Calling `DOTween.To()` gives you the ability to animate anything, all you need to do is provide a few parameters. Here is a deeper look at the text animation:
![]({{page.dir}}/images/5-dotween-example.png)

The difference in the m_ProgressBar animation is minor, in that instead of setting the text property you are changing the width of the visual element. Duration and ease are the same.

Push play and you should see a full animated bar start after a couple of seconds:

![]({{page.dir}}/images/5-final-result-animated.gif)

