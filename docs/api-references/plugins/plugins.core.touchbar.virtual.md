# plugins.core.touchbar.virtual

Virtual Touch Bar Manager

---

## API Overview
**Constants** - _Useful values which cannot be changed_
 * [LOCATION_DEFAULT_VALUE](#location_default_value)
 * [LOCATION_DRAGGABLE](#location_draggable)
 * [LOCATION_MOUSE](#location_mouse)

**Variables** - _Configurable values_
 * [updateLocationCallback](#updatelocationcallback)

**Functions** - _API calls offered directly by the extension_
 * [callback](#callback)
 * [hide](#hide)
 * [init](#init)
 * [show](#show)
 * [start](#start)
 * [stop](#stop)
 * [touchbar](#touchbar)
 * [update](#update)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [enabled](#enabled)
 * [isActive](#isactive)
 * [lastLocation](#lastlocation)
 * [macOSVersionSupported](#macosversionsupported)
 * [supported](#supported)


---

## API Documentation

### Constants


### [LOCATION_DEFAULT_VALUE](#location_default_value)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.LOCATION_DEFAULT_VALUE -> string`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Default location value.                                                                     |

---

### [LOCATION_DRAGGABLE](#location_draggable)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.LOCATION_DRAGGABLE -> string`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Location is Draggable.                                                                     |

---

### [LOCATION_MOUSE](#location_mouse)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.LOCATION_MOUSE -> string`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Location is Mouse.                                                                     |

---
### Variables


### [updateLocationCallback](#updatelocationcallback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.updateLocationCallback -> table`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Update Location Callback                                                                     |

---
### Functions


### [callback](#callback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.callback(_, message) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Callback Function for the Virtual Touch Bar                                                                     |
| **Parameters**                              | <ul><li>obj - the touchbarObject the callback is for</li><li>message - the message to the callback, either "didEnter" or "didExit"</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [hide](#hide)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.hide() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Hide the Virtual Touch Bar                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [init](#init)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.init() -> self`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Initialise the module.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>Self</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [show](#show)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.show() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Show the Virtual Touch Bar                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [start](#start)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.start() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Initialises the Virtual Touch Bar                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [stop](#stop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.stop() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Stops the Virtual Touch Bar                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [touchbar](#touchbar)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.touchbar() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the `hs._asm.undocumented.touchbar` object if it exists.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`hs._asm.undocumented.touchbar`</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [update](#update)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.update() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Updates the visibility and location of the Virtual Touch Bar                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---
### Fields


### [enabled](#enabled)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.enabled <cp.prop: boolean>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Is `true` if the plugin is enabled.                                                                     |

---

### [isActive](#isactive)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.isActive <cp.prop: boolean; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Is `true` if the plugin is enabled and the TouchBar is supported on this OS.                                                                     |

---

### [lastLocation](#lastlocation)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.lastLocation <cp.prop: point table>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The last known Virtual Touch Bar Location                                                                     |

---

### [macOSVersionSupported](#macosversionsupported)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.macOSVersionSupported <cp.prop: boolean>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Does the macOS version support the Touch Bar?                                                                     |

---

### [supported](#supported)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.touchbar.virtual.supported <cp.prop: boolean; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Is `true` if the Touch Bar is supported on this version of macOS.                                                                     |

---