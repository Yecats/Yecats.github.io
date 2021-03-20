---
layout: post
tutorial_title: Animate runtime progress bars with UI Toolkit
page_title:  Design 2 - Animate the progress bar
date: 2021-03-19
author: Stacey
menubar: 
published: true
hide_footer: true
hero_height: is-small
comments: true
---
# Design 2: Animate the progress bar

As I mentioned above, this progress bar will have three distinct animations all tied to the progress of the Drum clip:

1. **Percentage Text**: Goes from 1% to 100%.
2. **Outer Ring**: Quickly pivots around the center clockwise.
3. **Inner Ring**: Slowly pivots around the center counterclockwise. 

Additionally, the progress bar will only become visible while animating and will hide from the screen once complete. 
Add the following global methods and update `Start` to set the references and disable the m_Root’s visibility on load:

```csharp
private Label m_PercentageText;
private VisualElement m_OuterPivot;
private VisualElement m_InnerPivot;

private void Start()
{
    //Grab a reference to the root element that is drawn
    m_Root = GetComponent<UIDocument>().rootVisualElement;

    //Grab progress bar references
    m_PercentageText = m_Root.Q<Label>("txt_Percentage");
    m_OuterPivot = m_Root.Q<VisualElement>("Outer_Pivot");
    m_InnerPivot = m_Root.Q<VisualElement>("Inner_Pivot");

    //Display the view of the panel
    m_Root.style.visibility = Visibility.Hidden;
}
```
Next, add a new Coroutine which will animate the UI:

```csharp
private IEnumerator AnimateUI(float duration)
{
    //Reset the text
    m_PercentageText.text = "1%";

    //Toggle visibility on
    m_Root.style.visibility = Visibility.Visible;

    //Set the tweens
    Tween outerTween = DOTween.To(() => m_OuterPivot.worldTransform.rotation.eulerAngles, x => m_OuterPivot.transform.rotation = Quaternion.Euler(x), new Vector3(0, 0, 360), 5 / 0.5f).SetEase(Ease.Linear).SetLoops(-1);
    Tween innerTween = DOTween.To(() => m_InnerPivot.worldTransform.rotation.eulerAngles, x => m_InnerPivot.transform.rotation = Quaternion.Euler(x), new Vector3(0, 0, -360), duration / 0.5f).SetEase(Ease.Linear).SetLoops(-1);
    DOTween.To(() => 5, x => m_PercentageText.text = $"{x}%", 100, duration).SetEase(Ease.Linear).OnComplete(() => { outerTween.Kill(); innerTween.Kill(); });

    //Wait until tweens finish (+1 extra second for display purposes) 
    yield return new WaitForSeconds(duration + 1f);

    //Disable the visiblity
    m_Root.style.visibility = Visibility.Hidden;
}
```

The `AnimateUI` Coroutine does three major things:

1. Resets the text on m_Percentage and toggles the visibility of the whole bar on.
2. Instantiates the three Tweens with the appropriate parameters. The OuterPivot and InnerPivot tweens are rotating in a circle. InnerPivot is told to go counterclockwise by providing a -360 z parameter in the Vector3. `SetLoops` is telling the Tween how many times to loop with **-1** meaning “infinite”. The last new concept introduced is the `OnComplete()` method, which in this case is telling the outerTween and innerTweens to stop. If you were to take the OnComplete out, you would see the text hit 100% but the inner and outer images would continue to rotate.
3. Waits one second longer than the Tweens so that the player can see the 100% result prior to the progress bar disappearing from the screen. 

The last thing you need to do is start the coroutine. Add `StartCoroutine(AnimateUI(duration));` to to `AnimateCircularProgressBar`. Push play and you should see the progress bar appear when he starts to drum.

![]({{page.dir}}/images/9-design-2-final.gif) 
