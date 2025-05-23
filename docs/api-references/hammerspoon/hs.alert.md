# hs.alert

Simple on-screen alerts

---

## API Overview
**Variables** - _Configurable values_
 * [defaultStyle](#defaultstyle)

**Functions** - _API calls offered directly by the extension_
 * [closeAll](#closeall)
 * [closeSpecific](#closespecific)
 * [show](#show)
 * [showWithImage](#showwithimage)


---

## API Documentation

#### Variables


### [defaultStyle](#defaultstyle)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.alert.defaultStyle[]`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | A table defining the default visual style for the alerts generated by this module.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/alert/alert.lua line 17](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/alert/alert.lua#L17) |

---

#### Functions


### [closeAll](#closeall)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.alert.closeAll([seconds])`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Closes all alerts currently open on the screen                                                                     |
| **Parameters**                              | <ul><li>seconds - Optional number specifying the fade out duration. Defaults to `fadeOutDuration` value currently defined in the [hs.alert.defaultStyle](#defaultStyle)</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/alert/alert.lua line 284](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/alert/alert.lua#L284) |

---


### [closeSpecific](#closespecific)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.alert.closeSpecific(uuid, [seconds])`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Closes the alert with the specified identifier                                                                     |
| **Parameters**                              | <ul><li>uuid    - the identifier of the alert to close</li><li>seconds - Optional number specifying the fade out duration. Defaults to `fadeOutDuration` value currently defined in the [hs.alert.defaultStyle](#defaultStyle)</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>Use this function to close an alert which is indefinite or close an alert with a long duration early.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/alert/alert.lua line 300](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/alert/alert.lua#L300) |

---


### [show](#show)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.alert.show(str, [style], [screen], [seconds]) -> uuid`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Shows a message in large words briefly in the middle of the screen; does tostring() on its argument for convenience.                                                                     |
| **Parameters**                              | <ul><li>str     - The string or `hs.styledtext` object to display in the alert</li><li>style   - an optional table containing one or more of the keys specified in [hs.alert.defaultStyle](#defaultStyle).  If `str` is already an `hs.styledtext` object, this argument is ignored.</li><li>screen  - an optional `hs.screen` userdata object specifying the screen (monitor) to display the alert on.  Defaults to `hs.screen.mainScreen()` which corresponds to the screen with the currently focused window.</li><li>seconds - The number of seconds to display the alert. Defaults to 2.  If seconds is specified and is not a number, displays the alert indefinitely.</li></ul> |
| **Returns**                                 | <ul><li>a string identifier for the alert.</li></ul>          |
| **Notes**                                   | <ul><li>For convenience, you can call this function as `hs.alert(...)`</li><li>This function effectively calls `hs.alert.showWithImage(msg, nil, ...)`. As such, all the same rules apply regarding argument processing</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/alert/alert.lua line 263](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/alert/alert.lua#L263) |

---


### [showWithImage](#showwithimage)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.alert.showWithImage(str, image, [style], [screen], [seconds]) -> uuid`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Shows an image and a message in large words briefly in the middle of the screen; does tostring() on its argument for convenience.                                                                     |
| **Parameters**                              | <ul><li>str     - The string or `hs.styledtext` object to display in the alert</li><li>image   - The image to display in the alert</li><li>style   - an optional table containing one or more of the keys specified in [hs.alert.defaultStyle](#defaultStyle).  If `str` is already an `hs.styledtext` object, this argument is ignored.</li><li>screen  - an optional `hs.screen` userdata object specifying the screen (monitor) to display the alert on.  Defaults to `hs.screen.mainScreen()` which corresponds to the screen with the currently focused window.</li><li>seconds - The number of seconds to display the alert. Defaults to 2.  If seconds is specified and is not a number, displays the alert indefinitely.</li></ul> |
| **Returns**                                 | <ul><li>a string identifier for the alert.</li></ul>          |
| **Notes**                                   | <ul><li>The optional parameters are parsed in the order presented as follows:</li><li>  if the argument is a table and `style` has not previously been set, then the table is assigned to `style`</li><li>  if the argument is a userdata and `screen` has not previously been set, then the userdata is assigned to `screen`</li><li>  if `duration` has not been set, then it is assigned the value of the argument</li><li>  if all of these conditions fail for a given argument, then an error is returned</li><li>The reason for this logic is to support the creation of persistent alerts as was previously handled by the module: If you specify a non-number value for `seconds` you will need to store the string identifier returned by this function so that you can close it manually with `hs.alert.closeSpecific` when the alert should be removed.</li><li>Any style element which is not specified in the `style` argument table will use the value currently defined in the [hs.alert.defaultStyle](#defaultStyle) table.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/alert/alert.lua line 220](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/alert/alert.lua#L220) |

---

