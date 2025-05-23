# plugins.finalcutpro.browser.playhead

Browser Playhead Plugin.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [changeHighlightColor](#changehighlightcolor)
 * [deleteHighlight](#deletehighlight)
 * [getHighlightColor](#gethighlightcolor)
 * [getHighlightCustomColor](#gethighlightcustomcolor)
 * [getHighlightShape](#gethighlightshape)
 * [getHighlightTime](#gethighlighttime)
 * [highlight](#highlight)
 * [highlightFrame](#highlightframe)
 * [setHighlightColor](#sethighlightcolor)
 * [setHighlightCustomColor](#sethighlightcustomcolor)
 * [setHighlightShape](#sethighlightshape)
 * [setHighlightTime](#sethighlighttime)


---

## API Documentation

#### Functions


### [changeHighlightColor](#changehighlightcolor)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.changeHighlightColor([value]) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Prompts the user to change the Playhead Highlight Colour.                                                                     |
| **Parameters**                              | <ul><li>value - An RGB table with the selected colour (see `hs.drawing.color`)</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 100](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L100) |

---


### [deleteHighlight](#deletehighlight)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.deleteHighlight() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Delete's the highlight if it's currently visible on the screen.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 273](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L273) |

---


### [getHighlightColor](#gethighlightcolor)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.getHighlightColor() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the current highlight colour.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An RGB table with the selected colour (see `hs.drawing.color`) or `nil`</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 48](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L48) |

---


### [getHighlightCustomColor](#gethighlightcustomcolor)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.getHighlightCustomColor() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the current custom highlight colour.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An RGB table with the selected colour (see `hs.drawing.color`) or `nil`</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 74](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L74) |

---


### [getHighlightShape](#gethighlightshape)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.getHighlightShape() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the current highlight shape.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>"Rectangle", "Circle" or "Diamond" or `nil`.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 123](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L123) |

---


### [getHighlightTime](#gethighlighttime)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.getHighlightTime() -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the current highlight playhead time.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A number or `nil`</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 149](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L149) |

---


### [highlight](#highlight)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.highlight() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Highlight's the Final Cut Pro Browser Playhead.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 175](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L175) |

---


### [highlightFrame](#highlightframe)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.highlightFrame([frame]) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Highlights a specific frame.                                                                     |
| **Parameters**                              | <ul><li>frame - Frame as per `hs.geometry.rect`</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 200](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L200) |

---


### [setHighlightColor](#sethighlightcolor)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.setHighlightColor([value]) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets the Playhead Highlight Colour.                                                                     |
| **Parameters**                              | <ul><li>value - An RGB table with the selected colour (see `hs.drawing.color`)</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 61](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L61) |

---


### [setHighlightCustomColor](#sethighlightcustomcolor)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.setHighlightCustomColor([value]) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets the Custom Playhead Highlight Colour.                                                                     |
| **Parameters**                              | <ul><li>value - An RGB table with the selected colour (see `hs.drawing.color`)</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 87](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L87) |

---


### [setHighlightShape](#sethighlightshape)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.setHighlightShape([value]) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets the Custom Playhead Highlight Shape.                                                                     |
| **Parameters**                              | <ul><li>value - A string which can be "Rectangle", "Circle" or "Diamond".</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 136](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L136) |

---


### [setHighlightTime](#sethighlighttime)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.browser.playhead.setHighlightTime([value]) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets the Custom Playhead Highlight Time.                                                                     |
| **Parameters**                              | <ul><li>value - A number</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/browser/playhead.lua line 162](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/browser/playhead.lua#L162) |

---

