---
layout: post
tutorial_title: Challenge Solution - Extending the selection logic
page_title:  "Mass deselecting all objects"
date: 2019-12-10
author: Stacey Haffner
published: true
menubar: menu-challenge-extending-selection-logic
hide_footer: true
hero_height: is-small
comments: true
---
The first part of the challenge that we'll solve is deselecting all of the objects when the escape button is pushed on the keyboard. This will require a few steps:

1. Add a new action for the escape key
2. Create a new method that loops through all of the characters and sets their selected state to false. 

## Add the action binding
Add the new action binding by opening the **PlayerInputMapping** file located in the **Settings** folder of the project files.

1. Click the **+** button next to **Actions** and name it **Player_Deselect**. 
2. Set the **binding** **path** to **Escape [Keyboard]**.
3. **Save** the asset.

![Add action]({{page.dir}}/images/pt-1-1.gif)

## Clear selected party members
Create a new `ClearAllPartyMembers()` method in the `PartyManager` class. This method will loop through all known characters, which are registered upon creation in the `Characters` list, and set `IsSelected` to `false`. 

```csharp
/// <summary>
/// Clears the entire selection of objects
/// </summary>
private void ClearAllPartyMembers()
{
    //loop through all characters and set the status to false
    foreach (PlayerDetail character in Characters)
    {
        character.IsSelected = false;
    }
}
```

Next, you will need to monitor for the escape button to be pushed and call `ClearAllPartyMembers()` once it has been. Add the following method in the `PartyManager` class:

```csharp
public void EscapeDown_OnClick(InputAction.CallbackContext context)
{
    //Started phase ensures that we only trigger at the start of the button push
    if (context.phase != InputActionPhase.Started)
    {
        return;
    }

    //clear out the members
    ClearAllPartyMembers();
}

```
The final step is to add a new listener to the `Awake` method of the `InputManager` class. This listener will call `EscapeDown_OnClick` when the escape button is pushed. 

Add the following code to the end of `Awake` in the `InputManager` class:

```csharp
_input.Player.Player_Deselect.started += PartyManager.EscapeDown_OnClick;
```
