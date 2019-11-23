---
layout: post
tutorial_title: Listen for the Input System's Action events via C#
page_title:  "Cleaning up the CameraController class"
date: 2019-10-19
author: Stacey Haffner
published: true
menubar: menu_listen-for-input-system-events-via-csharp
hide_footer: true
hero_height: is-small
comments: true
---

Now that the project is listening for specific events, we do not have a need to do a validation check for a particular phase before performing the Action. Instead, we can rest assured that the `OnMove()` and `OnZoom()` methods will only be called when we want them to. 

To clean the code, remove the if statement at the beginning that is checking for the proper phase. Your methods should now look like this:

```csharp
        public void OnMove(InputAction.CallbackContext context)
        {
            Vector2 value = context.ReadValue<Vector2>();

            _moveDirection = new Vector3(value.x, 0, value.y);
        }

        public void OnZoom(InputAction.CallbackContext context)
        {
            CurrentZoom = Mathf.Clamp(_currentZoomAmount - context.ReadValue<Vector2>().y, ZoomMax, ZoomMin);
        }

```
