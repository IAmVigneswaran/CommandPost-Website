# plugins.finalcutpro.console.font

Final Cut Pro Font Console

---

## API Overview
**Variables** - _Configurable values_
 * [processedFonts](#processedfonts)

**Functions** - _API calls offered directly by the extension_
 * [onActivate](#onactivate)
 * [show](#show)


---

## API Documentation

#### Variables


### [processedFonts](#processedfonts)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.console.font.processedFonts -> table`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Table of font paths which have already been loaded or skipped.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/finalcutpro/console/font.lua line 37](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/console/font.lua#L37) |

---

#### Functions


### [onActivate](#onactivate)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.console.font.onActivate(_, action) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Handles Console Activations.                                                                     |
| **Parameters**                              | <ul><li>_ - Placeholder</li><li>action - Action table.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/console/font.lua line 106](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/console/font.lua#L106) |

---


### [show](#show)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.console.font.show() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Shows the Font Console.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/console/font.lua line 196](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/console/font.lua#L196) |

---

