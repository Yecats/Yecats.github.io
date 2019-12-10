---
layout: post
tutorial_title: Challenge Solution - Extending the selection logic
page_title: "Add new party members"
date: 2019-12-10
author: Stacey Haffner
published: true
menubar: menu-challenge-extending-selection-logic
hide_footer: true
hero_height: is-small
comments: true
---
The next part of the challenge that will be solved is adding new party members to an existing selection. The logic is:

1. If the shift button is held down, new party members will be added to the existing party. 
2. If shift is not held down then no new party members will be added to an existing party.

This means that shift is not required if the party selection is being created for the first time.

## Add the action binding
A new action binding will need to be added to monitor for **left shift** and **right shift** buttons being pushed. Add the new action binding by opening the **PlayerInputMapping** file located in the **Settings** folder of the project files.

1. Click the **+** button next to **Actions** and name it **Player_Select**. 
2. Set the **binding** **path** to **Left Shift [Keyboard]**.
3. Right click on the **Player_Select** and choose **Add Binding**.
2. Set the news **binding** **path** to **Right Shift [Keyboard]**.
4. **Save** the asset.

![Add action]({{page.dir}}/images/pt-2-2.jpg)

## Add the logic
A new global variable and method will be needed in order to track whether the shift buttons are pushed. To do this, add the following code to the `PartyManager` class:

```csharp
private bool _shiftButtonDown = false;

/// <summary>
/// Monitors for whether the shift button is pushed
/// </summary>
public void ShiftDown_OnClick(InputAction.CallbackContext context)
{
    // Logs the current state of the shift button
    _shiftButtonDown = context.phase == InputActionPhase.Started;
}
```

Once again, we need to add new listener to the `Awake` method of the `InputManager` class. This listener will call `ShiftDown_OnClick` when the right or left shift buttons are pushed. 

Add the following code to the end of `Awake` in the `InputManager` class:

```csharp
_input.Player.Player_Select.started += PartyManager.ShiftDown_OnClick;
_input.Player.Player_Select.canceled += PartyManager.ShiftDown_OnClick;
```

## Correct existing logic & hook up the shift button
Currently, the `SelectPartyMembers()` method is doing a global check to see if characters are within the bounds of the drawn rectangle. This is inadvertently causing characters to be unselected that are not within the bounds. 

![Add action]({{page.dir}}/images/pt-2-1.gif)

Add a new global method to track whether the player is creating the initial party setup. 

```csharp
private bool _initialPartySetup;
```

The `LeftMouseDown_OnClick()` method will set the new global variable based on if there's any characters currently selected. Add the following line to the end of the method:

```csharp
_initialPartySetup = Characters.Count(x => x.IsSelected) == 0;  
```

Next, the `SelectPartyMembers()` method will use the `_initialPartySetup` and `_shiftButtonDown` variables to determine if it should execute and if so, who it should mark as selected. By doing this, we'll correct the bad behavior mentioned previously.

```csharp
private void SelectPartyMembers()
{
    //check to see if some party members are selected and if so, verify that the shift button is down
    if (!_initialPartySetup && !_shiftButtonDown)
    {
        return;
    }

    //Loop through all registered characters
    foreach (PlayerDetail character in Characters)
    {
        //Get a point on the UI that represents the equivalent for the collider's center point
        Vector2 screenPosition = WorldToUiSpace(character.MyCollider.bounds.center);

        //Check to see if that point is within the bounds of the selection panel

        //This is an addition to an existing party
        if (!_initialPartySetup && _shiftButtonDown)
        {
            //make sure we're only operating on characters who are not selected. Without this our existing party members would be deselected
            if (!character.IsSelected)
            {
                character.IsSelected = RectTransformUtility.RectangleContainsScreenPoint(_selectedPanel, screenPosition);
            }
        }
        //New party creation
        else
        {
            character.IsSelected = RectTransformUtility.RectangleContainsScreenPoint(_selectedPanel, screenPosition);
        }
    }
}
```

That's it! Players can deselect all party members with the escape button and add new members with either shift buttons:

![Add action]({{page.dir}}/images/final.gif)
