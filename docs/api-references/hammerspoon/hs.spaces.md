# hs.spaces

This module provides some basic functions for controlling macOS Spaces.

The functionality provided by this module is considered experimental and subject to change. By using a combination of private APIs and Accessibility hacks (via hs.axuielement), some basic functions for controlling the use of Spaces is possible with Hammerspoon, but there are some limitations and caveats.

It should be noted that while the functions provided by this module have worked for some time in third party applications and in a previous experimental module that has received limited testing over the last few years, they do utilize some private APIs which means that Apple could change them at any time.

The functions which allow you to create new spaes, remove spaces, and jump to a specific space utilize `hs.axuielement` and perform accessibility actions through the Dock application to manipulate Mission Control. Because we are essentially directing the Dock to perform User Interactions, there is some visual feedback which we cannot entirely suppress. You can minimize, but not entirely remove, this by enabling "Reduce motion" in System Preferences -> Accessibility -> Display.

It is recommended that you also enable "Displays have separate Spaces" in System Preferences -> Mission Control.

This module is a distillation of my previous `hs._asm.undocumented.spaces` module, changes inspired by reviewing the `Yabai` source, and some experimentation with `hs.axuielement`. If you require more sophisticated control, I encourage you to check out https://github.com/koekeishiya/yabai -- it does require some additional setup (changes to SIP, possibly edits to `sudoers`, etc.) but may be worth the extra steps for some power users.

---

## Submodules
 * [hs.spaces.watcher](hs.spaces.watcher.md)

---

## API Overview
**Variables** - _Configurable values_
 * [MCwaitTime](#mcwaittime)

**Functions** - _API calls offered directly by the extension_
 * [activeSpaceOnScreen](#activespaceonscreen)
 * [activeSpaces](#activespaces)
 * [addSpaceToScreen](#addspacetoscreen)
 * [allSpaces](#allspaces)
 * [closeMissionControl](#closemissioncontrol)
 * [data_managedDisplaySpaces](#data_manageddisplayspaces)
 * [data_missionControlAXUIElementData](#data_missioncontrolaxuielementdata)
 * [focusedSpace](#focusedspace)
 * [gotoSpace](#gotospace)
 * [missionControlSpaceNames](#missioncontrolspacenames)
 * [moveWindowToSpace](#movewindowtospace)
 * [openMissionControl](#openmissioncontrol)
 * [removeSpace](#removespace)
 * [screensHaveSeparateSpaces](#screenshaveseparatespaces)
 * [setDefaultMCwaitTime](#setdefaultmcwaittime)
 * [spaceDisplay](#spacedisplay)
 * [spacesForScreen](#spacesforscreen)
 * [spaceType](#spacetype)
 * [toggleAppExpose](#toggleappexpose)
 * [toggleLaunchPad](#togglelaunchpad)
 * [toggleMissionControl](#togglemissioncontrol)
 * [toggleShowDesktop](#toggleshowdesktop)
 * [windowsForSpace](#windowsforspace)
 * [windowSpaces](#windowspaces)


---

## API Documentation

#### Variables


### [MCwaitTime](#mcwaittime)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.MCwaitTime`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Specifies how long to delay before performing the accessibility actions for [hs.spaces.gotoSpace](#gotoSpace) and [hs.spaces.removeSpace](#removeSpace)                                                                     |
| **Notes**                                   | <ul><li>The above mentioned functions require that the Mission Control accessibility objects be fully formed before the necessary action can be triggered. This variable specifies how long to delay before performing the action to complete the function. Experimentation on my machine has found that 0.3 seconds provides sufficient time for reliable functionality.</li><li>If you find that the above mentioned functions do not work reliably with your setup, you can try adjusting this variable upwards -- the down side is that the larger this value is, the longer the Mission Control display is visible before returning the user to what they were working on.</li><li>Once you have found a value that works reliably on your system, you can use [hs.spaces.setDefaultMCwaitTime](#setDefaultMCwaitTime) to make it the default value for your system each time the `hs.spaces` module is loaded.</li></ul> |
| **Source**                                  | [extensions/spaces/spaces.lua line 215](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L215) |

---

#### Functions


### [activeSpaceOnScreen](#activespaceonscreen)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.activeSpaceOnScreen([screen]) -> integer | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the currently visible (active) space for the specified screen.                                                                     |
| **Parameters**                              | <ul><li>`screen` - an optional screen specification identifying the screen to return the active space for. The screen may be specified by its ID (`hs.screen:id()`), its UUID (`hs.screen:getUUID()`), the string "Main" (a shortcut for `hs.screen.mainScreen()`), the string "Primary" (a shortcut for `hs.screen.primaryScreen()`), or as an `hs.screen` object. If no screen is specified, the screen returned by `hs.screen.mainScreen()` is used.</li></ul> |
| **Returns**                                 | <ul><li>an integer specifying the ID of the space displayed, or nil and an error message if an error occurs.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 425](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L425) |

---


### [activeSpaces](#activespaces)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.activeSpaces() -> table | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a key-value table specifying the active spaces for all screens.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a key-value table in which the keys are the UUIDs for the current screens and the value for each key is the space ID of the active space for that display.</li></ul>          |
| **Notes**                                   | <ul><li>the table returned has its __tostring metamethod set to `hs.inspect` to simplify inspecting the results when using the Hammerspoon Console.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 488](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L488) |

---


### [addSpaceToScreen](#addspacetoscreen)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.addSpaceToScreen([screen], [closeMC]) -> true | nil, errMsg`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Adds a new space on the specified screen                                                                     |
| **Parameters**                              | <ul><li>`screen` - an optional screen specification identifying the screen to create the new space on. The screen may be specified by its ID (`hs.screen:id()`), its UUID (`hs.screen:getUUID()`), the string "Main" (a shortcut for `hs.screen.mainScreen()`), the string "Primary" (a shortcut for `hs.screen.primaryScreen()`), or as an `hs.screen` object. If no screen is specified, the screen returned by `hs.screen.mainScreen()` is used.</li><li>`closeMC` - an optional boolean, default true, specifying whether or not the Mission Control display should be closed after adding the new space.</li></ul> |
| **Returns**                                 | <ul><li>true on success; otherwise return nil and an error message</li></ul>          |
| **Notes**                                   | <ul><li>This function creates a new space by opening up the Mission Control display and then programmatically invoking the button to add a new space. This is unavoidable. You can  minimize, but not entirely remove, the visual shift to the Mission Control display by by enabling "Reduce motion" in System Preferences -> Accessibility -> Display.</li><li>If you intend to perform multiple actions which require the Mission Control display (([hs.spaces.missionControlSpaceNames](#missionControlSpaceNames), [hs.spaces.addSpaceToScreen](#addSpaceToScreen), [hs.spaces.removeSpace](#removeSpace), or [hs.spaces.gotoSpace](#gotoSpace)), you can pass in `false` as the final argument to prevent the automatic closure of the Mission Control display -- this will reduce the visual side-affects to one transition instead of many.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 686](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L686) |

---


### [allSpaces](#allspaces)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.allSpaces() -> table | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a Kay-Value table containing the IDs of all spaces for all screens.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a key-value table in which the keys are the UUIDs for the current screens and the value for each key is a table of space IDs corresponding to the spaces for that screen. Returns nil and an error message if an error occurs.</li></ul>          |
| **Notes**                                   | <ul><li>the table returned has its __tostring metamethod set to `hs.inspect` to simplify inspecting the results when using the Hammerspoon Console.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 396](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L396) |

---


### [closeMissionControl](#closemissioncontrol)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.closeMissionControl() -> None`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Opens the Mission Control display                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>Does nothing if the Mission Control display is not currently visible.</li><li>This function uses Accessibility features provided by the Dock to close Mission Control and is used internally when performing the [hs.spaces.gotoSpace](#gotoSpace), [hs.spaces.addSpaceToScreen](#addSpaceToScreen), and [hs.spaces.removeSpace](#removeSpace) functions.</li><li>It is possible to invoke the above mentioned functions and prevent them from auto-closing Mission Control -- this may be useful if you wish to perform multiple actions and want to minimize the visual side-effects. You can then use this function when you are done.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 315](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L315) |

---


### [data_managedDisplaySpaces](#data_manageddisplayspaces)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.data_managedDisplaySpaces() -> table | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table containing information about the managed display spaces                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a table containing information about all of the displays and spaces managed by the OS.</li></ul>          |
| **Notes**                                   | <ul><li>the format and detail of this table is too complex and varied to describe here; suffice it to say this is the workhorse for this module and a careful examination of this table may be informative, but is not required in the normal course of using this module.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/libspaces.m line 33](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/libspaces.m#L33) |

---


### [data_missionControlAXUIElementData](#data_missioncontrolaxuielementdata)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.data_missionControlAXUIElementData(callback) -> None`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Generate a table containing the results of `hs.axuielement.buildTree` on the Mission Control Accessibility group of the Dock.                                                                     |
| **Parameters**                              | <ul><li>`callback` - a callback function that should expect a table as the results. The table will be formatted as described in the documentation for `hs.axuielement.buildTree`.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>Like [hs.spaces.data_managedDisplaySpaces](#data_managedDisplaySpaces), this function is not required for general usage of this module; rather it is provided for those who wish to examine the internal data that makes this module possible more closely to see if there might be other information or functionality that they would like to explore.</li><li>Getting Accessibility elements for Mission Control is somewhat tricky -- they only exist when the Mission Control display is visible, which is the exact time that you can't examine them. What this function does is trigger Mission Control and then builds a tree of the elements, capturing all of the properties and property values while the elements are valid, closes Mission Control, and then returns the results in a table by invoking the provided callback function.</li><li>  Note that the `hs.axuielement` objects within the table returned will be invalid by the time you can examine them -- this is why the attributes and values will also be contained in the resulting tree.</li><li>  Example usage: `hs.spaces.data_missionControlAXUIElementData(function(results) hs.console.clearConsole() ; print(hs.inspect(results)) end)`</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 174](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L174) |

---


### [focusedSpace](#focusedspace)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.focusedSpace() -> integer`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the space ID of the currently focused space                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the space ID for the currently focused space. The focused space is the currently active space on the currently active screen (i.e. that the user is working on)</li></ul>          |
| **Notes**                                   | <ul><li>*usually* the currently active screen will be returned by `hs.screen.mainScreen()`; however some full screen applications may have focus without updating which screen is considered "main". You can use this function, and look up the screen UUID with [hs.spaces.spaceDisplay](#spaceDisplay) to determine the "true" focused screen if required.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/libspaces.m line 61](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/libspaces.m#L61) |

---


### [gotoSpace](#gotospace)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.gotoSpace(spaceID) -> true | nil, errMsg`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Change to the specified space.                                                                     |
| **Parameters**                              | <ul><li>`spaceID` - an integer specifying the ID of the space</li></ul> |
| **Returns**                                 | <ul><li>true if the space change was initiated, or nil and an error message if there is an error trying to switch spaces.</li></ul>          |
| **Notes**                                   | <ul><li>This function changes to a space by opening up the Mission Control display and then programmatically invoking the button to activate the space. This is unavoidable. You can  minimize, but not entirely remove, the visual shift to the Mission Control display by by enabling "Reduce motion" in System Preferences -> Accessibility -> Display.</li><li>The action of changing to a new space automatically closes the Mission Control display, so unlike ([hs.spaces.missionControlSpaceNames](#missionControlSpaceNames), [hs.spaces.addSpaceToScreen](#addSpaceToScreen), and [hs.spaces.removeSpace](#removeSpace), there is no flag you can specify to leave Mission Control visible. When possible, you should generally invoke this function last if you are performing multiple actions and want to minimize the amount of time the Mission Control display is visible and reduce the visual side affects.</li><li>The Accessibility elements required to change to a space are not created until the Mission Control display is fully visible. Because of this, there is a built in delay when invoking this function that can be adjusted by changing the value of [hs.spaces.MCwaitTime](#MCwaitTime).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 751](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L751) |

---


### [missionControlSpaceNames](#missioncontrolspacenames)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.missionControlSpaceNames([closeMC]) -> table | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table containing the space names as they appear in Mission Control associated with their space ID. This is provided for informational purposes only -- all of the functions of this module use the spaceID to insure accuracy.                                                                     |
| **Parameters**                              | <ul><li>`closeMC` - an optional boolean, default true, specifying whether or not the Mission Control display should be closed after adding the new space.</li></ul> |
| **Returns**                                 | <ul><li>a key-value table in which the keys are the UUIDs for each screen and the value is a key-value table where the screen ID is the key and the Mission Control name of the space is the value.</li></ul>          |
| **Notes**                                   | <ul><li>the table returned has its __tostring metamethod set to `hs.inspect` to simplify inspecting the results when using the Hammerspoon Console.</li><li>This function works by opening up the Mission Control display and then grabbing the names from the Accessibility elements created. This is unavoidable. You can  minimize, but not entirely remove, the visual shift to the Mission Control display by by enabling "Reduce motion" in System Preferences -> Accessibility -> Display.</li><li>If you intend to perform multiple actions which require the Mission Control display ([hs.spaces.missionControlSpaceNames](#missionControlSpaceNames), [hs.spaces.addSpaceToScreen](#addSpaceToScreen), [hs.spaces.removeSpace](#removeSpace), or [hs.spaces.gotoSpace](#gotoSpace)), you can pass in `false` as the final argument to prevent the automatic closure of the Mission Control display -- this will reduce the visual side-affects to one transition instead of many.</li><li>This function attempts to use the localization strings for the Dock application to properly determine the Mission Control names. If you find that it doesn't provide the correct values for your system, please provide the following information when submitting an issue:</li><li>  the desktop or application name(s) as they appear at the top of the Mission Control screen when you invoke it manually (or with `hs.spaces.toggleMissionControl()` entered into the Hammerspoon console).</li><li>  the output from the following commands, issued in the Hammerspoon console:</li><li>    `hs.host.operatingSystemVersionString()`</li><li>    `hs.host.locale.current()`</li><li>    `hs.inspect(hs.host.locale.preferredLanguages())`</li><li>    `hs.inspect(hs.host.locale.details())`</li><li>    `hs.spaces.screensHaveSeparateSpaces()`</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 632](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L632) |

---


### [moveWindowToSpace](#movewindowtospace)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.moveWindowToSpace(window, spaceID[, force]) -> true | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Moves the window with the specified windowID to the space specified by spaceID.                                                                     |
| **Parameters**                              | <ul><li>`window`  - an integer specifying the ID of the window, or an `hs.window` object</li><li>`spaceID` - an integer specifying the ID of the space</li><li>`force` - an optional boolean specifying whether the window should be tried to move even if the spaces aren't compatible</li></ul> |
| **Returns**                                 | <ul><li>true if the window was moved; otherwise nil and an error message.</li></ul>          |
| **Notes**                                   | <ul><li>a window can only be moved from a user space to another user space -- you cannot move the window of a full screen (or tiled) application to another space. you also cannot move a window *to* the same space as a full screen application unless `force` is set to true and even then it works for floating windows only.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/libspaces.m line 134](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/libspaces.m#L134) |

---


### [openMissionControl](#openmissioncontrol)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.openMissionControl() -> None`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Opens the Mission Control display                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>Does nothing if the Mission Control display is already visible.</li><li>This function uses Accessibility features provided by the Dock to open up Mission Control and is used internally when performing the [hs.spaces.gotoSpace](#gotoSpace), [hs.spaces.addSpaceToScreen](#addSpaceToScreen), and [hs.spaces.removeSpace](#removeSpace) functions.</li><li>It is unlikely you will need to invoke this by hand, and the public interface to this function may go away in the future.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 299](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L299) |

---


### [removeSpace](#removespace)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.removeSpace(spaceID, [closeMC]) -> true | nil, errMsg`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Removes the specified space.                                                                     |
| **Parameters**                              | <ul><li>`spaceID` - an integer specifying the ID of the space</li><li>`closeMC` - an optional boolean, default true, specifying whether or not the Mission Control display should be closed after removing the space.</li></ul> |
| **Returns**                                 | <ul><li>true if the space removal was initiated, or nil and an error message if there is an error trying to remove the space.</li></ul>          |
| **Notes**                                   | <ul><li>You cannot remove a currently active space -- move to another one first with [hs.spaces.gotoSpace](#gotoSpace).</li><li>If a screen has only one user space (i.e. not a full screen application window or tiled set), it cannot be removed.</li><li>This function removes a space by opening up the Mission Control display and then programmatically invoking the button to remove the specified space. This is unavoidable. You can  minimize, but not entirely remove, the visual shift to the Mission Control display by by enabling "Reduce motion" in System Preferences -> Accessibility -> Display.</li><li>If you intend to perform multiple actions which require the Mission Control display (([hs.spaces.missionControlSpaceNames](#missionControlSpaceNames), [hs.spaces.addSpaceToScreen](#addSpaceToScreen), [hs.spaces.removeSpace](#removeSpace), or [hs.spaces.gotoSpace](#gotoSpace)), you can pass in `false` as the final argument to prevent the automatic closure of the Mission Control display -- this will reduce the visual side-affects to one transition instead of many.</li><li>The Accessibility elements required to change to a space are not created until the Mission Control display is fully visible. Because of this, there is a built in delay when invoking this function that can be adjusted by changing the value of [hs.spaces.MCwaitTime](#MCwaitTime).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 811](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L811) |

---


### [screensHaveSeparateSpaces](#screenshaveseparatespaces)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.screensHaveSeparateSpaces() -> bool`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Determine if the user has enabled the "Displays Have Separate Spaces" option within Mission Control.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>true or false representing the status of the "Displays Have Separate Spaces" option within Mission Control.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/libspaces.m line 17](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/libspaces.m#L17) |

---


### [setDefaultMCwaitTime](#setdefaultmcwaittime)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.setDefaultMCwaitTime([time]) -> None`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets the initial value for [hs.spaces.MCwaitTime](#MCwaitTime) to be set to when this module first loads.                                                                     |
| **Parameters**                              | <ul><li>`time` - an optional number greater than 0 specifying the initial default for [hs.spaces.MCwaitTime](#MCwaitTime). If you do not specify a value, then the current value of [hs.spaces.MCwaitTime](#MCwaitTime) is used.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>this function uses the `hs.settings` module to store the default time in the key "hs_spaces_MCwaitTime".</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 225](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L225) |

---


### [spaceDisplay](#spacedisplay)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.spaceDisplay(spaceID) -> string | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the screen UUID for the screen that the specified space is on.                                                                     |
| **Parameters**                              | <ul><li>`spaceID` - an integer specifying the ID of the space</li></ul> |
| **Returns**                                 | <ul><li>a string specifying the UUID of the display the space is on, or nil and error message if an error occurs.</li></ul>          |
| **Notes**                                   | <ul><li>the space does not have to be currently active (visible) to determine which screen the space belongs to.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 517](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L517) |

---


### [spacesForScreen](#spacesforscreen)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.spacesForScreen([screen]) -> table | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table containing the IDs of the spaces for the specified screen in their current order.                                                                     |
| **Parameters**                              | <ul><li>`screen` - an optional screen specification identifying the screen to return the space array for. The screen may be specified by its ID (`hs.screen:id()`), its UUID (`hs.screen:getUUID()`), the string "Main" (a shortcut for `hs.screen.mainScreen()`), the string "Primary" (a shortcut for `hs.screen.primaryScreen()`), or as an `hs.screen` object. If no screen is specified, the screen returned by `hs.screen.mainScreen()` is used.</li></ul> |
| **Returns**                                 | <ul><li>a table containing space IDs for the spaces for the screen, or nil and an error message if there is an error.</li></ul>          |
| **Notes**                                   | <ul><li>the table returned has its __tostring metamethod set to `hs.inspect` to simplify inspecting the results when using the Hammerspoon Console.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 331](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L331) |

---


### [spaceType](#spacetype)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.spaceType(spaceID) -> string | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a string indicating whether the space is a user space or a full screen/tiled application space.                                                                     |
| **Parameters**                              | <ul><li>`spaceID` - an integer specifying the ID of the space</li></ul> |
| **Returns**                                 | <ul><li>the string "user" if the space is a regular user space, or "fullscreen" if the space is a fullscreen or tiled window pair. Returns nil and an error message if the space does not refer to a valid managed space.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 550](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L550) |

---


### [toggleAppExpose](#toggleappexpose)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.toggleAppExpose() -> None`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Toggles the current applications Exposé display                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>this is the same functionality as provided by the System Preferences -> Mission Control -> Hot Corners... -> Application Windows setting or the App Exposé trackpad swipe gesture (3 or 4 fingers down).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 271](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L271) |

---


### [toggleLaunchPad](#togglelaunchpad)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.toggleLaunchPad() -> None`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Toggles the Launch Pad display.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>this is the same functionality as provided by the System Preferences -> Mission Control -> Hot Corners... -> Launch Pad setting, the Launch Pad touchbar icon, or the Launch Pad trackpad swipe gesture (Pinch with thumb and three fingers).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 285](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L285) |

---


### [toggleMissionControl](#togglemissioncontrol)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.toggleMissionControl() -> None`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Toggles the Mission Control display                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>this is the same functionality as provided by the System Preferences -> Mission Control -> Hot Corners... -> Mission Control setting, the Mission Control touchbar icon, or the Mission Control trackpad swipe gesture (3 or 4 fingers up).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 257](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L257) |

---


### [toggleShowDesktop](#toggleshowdesktop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.toggleShowDesktop() -> None`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Toggles moving all windows on/off screen to display the desktop underneath.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>this is the same functionality as provided by the System Preferences -> Mission Control -> Hot Corners... -> Desktop setting, the Show Desktop touchbar icon, or the Show Desktop trackpad swipe gesture (Spread with thumb and three fingers).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/spaces.lua line 243](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/spaces.lua#L243) |

---


### [windowsForSpace](#windowsforspace)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.windowsForSpace(spaceID) -> table | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table containing the window IDs of *all* windows on the specified space                                                                     |
| **Parameters**                              | <ul><li>`spaceID` - an integer specifying the ID of the space</li></ul> |
| **Returns**                                 | <ul><li>a table containing the window IDs for *all* windows on the specified space</li></ul>          |
| **Notes**                                   | <ul><li>the table returned has its __tostring metamethod set to `hs.inspect` to simplify inspecting the results when using the Hammerspoon Console.</li><li>The list of windows includes all items which are considered "windows" by macOS -- this includes visual elements usually considered unimportant like overlays, tooltips, graphics, off-screen windows, etc. so expect a lot of false positives in the results.</li><li>In addition, due to the way Accessibility objects work, only those window IDs that are present on the currently visible spaces will be finable with `hs.window` or exist within `hs.window.allWindows()`.</li><li>This function *will* prune Hammerspoon canvas elements from the list because we "own" these and can identify their window ID's programmatically. This does not help with other applications, however.</li><li>Reviewing how third-party applications have generally pruned this list, I believe it will be necessary to use `hs.window.filter` to prune the list and access `hs.window` objects that are on the non-visible spaces.</li><li>  as `hs.window.filter` is scheduled to undergo a re-write soon to (hopefully) dramatically speed it up, I am providing this function *as is* at present for those who wish to experiment with it; however, I hope to make it more useful in the coming months and the contents may change in the future (the format won't, but hopefully the useless extras will disappear requiring less pruning logic on your end).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/libspaces.m line 80](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/libspaces.m#L80) |

---


### [windowSpaces](#windowspaces)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.spaces.windowSpaces(window) -> table | nil, error`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table containing the space IDs for all spaces that the specified window is on.                                                                     |
| **Parameters**                              | <ul><li>`window` - an integer specifying the ID of the window, or an `hs.window` object</li></ul> |
| **Returns**                                 | <ul><li>a table containing the space IDs of all spaces the window is on, or nil and an error message if an error occurs.</li></ul>          |
| **Notes**                                   | <ul><li>the table returned has its __tostring metamethod set to `hs.inspect` to simplify inspecting the results when using the Hammerspoon Console.</li><li>If the window ID does not specify a valid window, then an empty array will be returned.</li><li>For most windows, this will be a single element table; however some applications may create "sticky" windows that may appear on more than one space.</li><li>  For example, the container windows for `hs.canvas` objects which have the `canJoinAllSpaces` behavior set will appear on all spaces and the table returned by this function will contain all spaceIDs for the screen which displays the canvas.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/spaces/libspaces.m line 186](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/spaces/libspaces.m#L186) |

---

