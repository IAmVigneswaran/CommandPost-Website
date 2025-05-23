# plugins.finalcutpro.timeline.colorboard

Color Board Plugins.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [colorBoardMousePuckRelease](#colorboardmousepuckrelease)
 * [nextAspect](#nextaspect)
 * [startMousePuck](#startmousepuck)
 * [startShiftingPuck](#startshiftingpuck)
 * [stopShiftingPuck](#stopshiftingpuck)


---

## API Documentation

#### Functions


### [colorBoardMousePuckRelease](#colorboardmousepuckrelease)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.timeline.colorboard.colorBoardMousePuckRelease() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Color Board Mouse Puck Release                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/timeline/colorboard.lua line 111](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/timeline/colorboard.lua#L111) |

---


### [nextAspect](#nextaspect)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.timeline.colorboard.nextAspect() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Goes to the next Color Board aspect.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/timeline/colorboard.lua line 127](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/timeline/colorboard.lua#L127) |

---


### [startMousePuck](#startmousepuck)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.timeline.colorboard.startMousePuck(aspect, property) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Color Board - Puck Control Via Mouse                                                                     |
| **Parameters**                              | <ul><li>aspect - "global", "shadows", "midtones" or "highlights"</li><li>property - "Color", "Saturation" or "Exposure"</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/timeline/colorboard.lua line 81](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/timeline/colorboard.lua#L81) |

---


### [startShiftingPuck](#startshiftingpuck)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.timeline.colorboard.startShiftingPuck(puck, percentShift, angleShift) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Starts shifting the puck, repeating at the keyboard repeat rate. Runs until `stopShiftingPuck()` is called.                                                                     |
| **Parameters**                              | <ul><li>puck         - The puck to shift</li><li>property     - The property to shift (typically the `percent` or `angle` value for the puck)</li><li>amount       - The amount to shift the property.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/timeline/colorboard.lua line 23](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/timeline/colorboard.lua#L23) |

---


### [stopShiftingPuck](#stopshiftingpuck)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.timeline.colorboard.stopShiftingPuck() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Stops the puck from shifting with the keyboard.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/timeline/colorboard.lua line 68](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/timeline/colorboard.lua#L68) |

---

