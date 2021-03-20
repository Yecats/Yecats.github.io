---
layout: post
tutorial_title: Animate runtime progress bars with UI Toolkit
page_title:  Design 2 - Hook up the progress bar to an existing animation
date: 2021-03-19
author: Stacey
menubar: 
published: true
hide_footer: true
hero_height: is-small
comments: true
---
# Design 2: Hook up the progress bar to an existing animation

Open the **CircularProgressBar_Start** scene located under **Assets** > **WUG** > **Scenes**. The scene is minimal and comes with a character who is setup to drum. Push play to see the animation workflow:

![]({{page.dir}}/images/7-initial animation.gif) 

> You are probably wondering why you are looking at a fantasy character who is drumming. The short answer? Because he is adorable, and I thought drumming was a fun action to watch him do. :D I used Adobe’s [Mixamo](https://www.mixamo.com/) site for both the character and the animations. 

As you can see, when the “Drum” trigger is enabled, the Animation Controller has three different animations that it plays. For this scenario, you will hook the Circular Progress Bar to appear, run and disappear during the “Drum” animation only. This can be achieved by using [Animation Events]( https://docs.unity3d.com/Manual/script-AnimationWindowEvent.html). 

Before you can add the Animation Event, you first need a new method for it to call. Animation Events can only call methods that are part of MonoBehaviors that are on the Game Object as the Animation. In this case, the tutorial project came with a `CharacterController` class that is on the Character Game Object. Open it, and add the following code:

```csharp
private void AnimateProgressBar()
{
    //Gets a reference to the "Drum" clip on the controller
    AnimationClip clip = m_AnimatorController.runtimeAnimatorController.animationClips.Where(x => x.name.Equals("drumming")).FirstOrDefault();

    //Call the method that controls the circular animations
    CircularProgressBarAnimation.Instance.AnimateCircularProgressBar(clip == null ? 5f: clip.length);        
}
```

` AnimateProgressBar` searches the Animator Controller’s runtime animation clips for a reference to the “drumming” clip. The information is then used to pass the length into the Circular Progress Bar so that DOTween can use it.

The project also comes with a ` CircularProgressBarAnimation` class that inherits from `MonoBehaviour`. The current behavior mirrors the setup of `LoadingProgressBarAnimation` in that it gets references to UI Document and root visual element. Open it and add a method stub (you will fill this in shortly):

```csharp
public static void AnimateCircularProgressBar(float duration) {   }
```

Finally, you will add a reference to `CharacterController.AnimateProgressBar()` directly in your animation:

1. Open the **Animation window** by going to **Window** > **Animation** > **Animation**.
2. In the Hierarchy window, select **Character** game object. This will populate all of the associated animations as a drop down in the Animation Window. 
3. Select **drumming** in the dropdown.
4. On the first keyframe, click the **Add Event** button. Unity will add a tall square-ish looking item at the top of the Animation. 
5. Click the new event icon. In the inspector window, set the **Function** to **AnimateProgressBar**.

![]({{page.dir}}/images/7-add-animation-event.gif) 


