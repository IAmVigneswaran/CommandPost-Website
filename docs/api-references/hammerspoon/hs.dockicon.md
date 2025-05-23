# hs.dockicon

Control Hammerspoon's dock icon

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [bounce](#bounce)
 * [hide](#hide)
 * [setBadge](#setbadge)
 * [show](#show)
 * [tileCanvas](#tilecanvas)
 * [tileSize](#tilesize)
 * [tileUpdate](#tileupdate)
 * [visible](#visible)


---

## API Documentation

#### Functions


### [bounce](#bounce)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.dockicon.bounce(indefinitely)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Bounce Hammerspoon's dock icon                                                                     |
| **Parameters**                              | <ul><li>indefinitely - A boolean value, true if the dock icon should bounce until the dock icon is clicked, false if the dock icon should only bounce briefly</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/dockicon/libdockicon.m line 50](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/dockicon/libdockicon.m#L50) |

---


### [hide](#hide)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.dockicon.hide()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Hide Hammerspoon's dock icon                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/dockicon/libdockicon.m line 36](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/dockicon/libdockicon.m#L36) |

---


### [setBadge](#setbadge)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.dockicon.setBadge(badge)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Set Hammerspoon's dock icon badge                                                                     |
| **Parameters**                              | <ul><li>badge - A string containing the label to place inside the dock icon badge. If the string is empty, the badge will be cleared</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/dockicon/libdockicon.m line 64](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/dockicon/libdockicon.m#L64) |

---


### [show](#show)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.dockicon.show()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Make Hammerspoon's dock icon visible                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/dockicon/libdockicon.m line 22](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/dockicon/libdockicon.m#L22) |

---


### [tileCanvas](#tilecanvas)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.dockicon.tileCanvas([canvas]) -> canvasObject | nil`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get or set a canvas object to be displayed as the Hammerspoon dock icon                                                                     |
| **Parameters**                              | <ul><li>`canvas` - an optional `hs.canvas` object specifying the canvas to be displayed as the dock icon for Hammerspoon. If an explicit `nil` is specified, the dock icon will revert to the Hammerspoon application icon.</li></ul> |
| **Returns**                                 | <ul><li>If the dock icon is assigned a canvas object, that canvas object will be returned, otherwise returns nil.</li></ul>          |
| **Notes**                                   | <ul><li>If you update the canvas object by changing any of its components, it will not be reflected in the dock icon until you invoke [hs.dockicon.tileUpdate](#tileUpdate).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/dockicon/libdockicon.m line 83](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/dockicon/libdockicon.m#L83) |

---


### [tileSize](#tilesize)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.dockicon.tileSize() -> size table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table containing the size of the tile representing the dock icon.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a table containing the size of the tile representing the dock icon for Hammerspoon. This table will contain `h` and `w` keys specifying the tile height and width as numbers.</li></ul>          |
| **Notes**                                   | <ul><li>the size returned specifies the display size of the dock icon tile. If your canvas item is larger than this, then only the top left portion corresponding to the size returned will be displayed.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/dockicon/libdockicon.m line 118](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/dockicon/libdockicon.m#L118) |

---


### [tileUpdate](#tileupdate)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.dockicon.tileUpdate() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Force an update of the dock icon.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>Changes made to a canvas object are not reflected automatically like they are when a canvas is being displayed on the screen; you must invoke this method after making changes to the canvas for the updates to be reflected in the dock icon.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/dockicon/libdockicon.m line 139](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/dockicon/libdockicon.m#L139) |

---


### [visible](#visible)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.dockicon.visible() -> bool`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Determine whether Hammerspoon's dock icon is visible                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A boolean, true if the dock icon is visible, false if not</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/dockicon/libdockicon.m line 7](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/dockicon/libdockicon.m#L7) |

---

