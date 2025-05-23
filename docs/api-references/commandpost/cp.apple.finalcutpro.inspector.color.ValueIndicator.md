# cp.apple.finalcutpro.inspector.color.ValueIndicator

ValueIndicator Module.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [matches](#matches)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [ValueIndicator](#valueindicator)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [decrement](#decrement)
 * [increment](#increment)
 * [isShowing](#isshowing)
 * [loadLayout](#loadlayout)
 * [saveLayout](#savelayout)
 * [shiftValue](#shiftvalue)


---

## API Documentation

#### Functions


### [matches](#matches)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ValueIndicator.matches(element) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks to see if an element matches what we think it should be.                                                                     |
| **Parameters**                              | <ul><li>element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                 | <ul><li>`true` if matches otherwise `false`</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 14](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L14) |

---

#### Constructors


### [ValueIndicator](#valueindicator)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ValueIndicator(parent, uiFinder, minValue, maxValue, toAXValueFn, fromAXValueFn) -> ValueIndicator`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new ValueIndicator.                                                                     |
| **Parameters**                              | <ul><li>`parent`         - The parent table.</li><li>`uiFinder`       - The function which returns the `axuielement`.</li><li>`minValue`       - The minimum value allowed for the value.</li><li>`maxValue`       - The maximum value allowed for the value.</li><li>`toAXValueFn`    - The function which will convert the user value to the actual AXValue.</li><li>`fromAXValueFn`  - The function which will convert the current AXValue to a user value.</li></ul> |
| **Returns**                                 | <ul><li>New `ValueIndicator` instance.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 27](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L27) |

---

#### Methods


### [decrement](#decrement)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ValueIndicator:decrement() -> cp.apple.finalcutpro.inspector.color.ValueIndicator`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Decrements the value indicator.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `cp.apple.finalcutpro.inspector.color.ValueIndicator` object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 145](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L145) |

---


### [increment](#increment)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ValueIndicator:increment() -> cp.apple.finalcutpro.inspector.color.ValueIndicator`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Increments the value indicator.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `cp.apple.finalcutpro.inspector.color.ValueIndicator` object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 128](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L128) |

---


### [isShowing](#isshowing)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ValueIndicator:isShowing() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Is the Value Indicator currently showing?                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if showing, otherwise `false`</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 50](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L50) |

---


### [loadLayout](#loadlayout)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ValueIndicator:loadLayout(layout) -> none`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Loads a layout.                                                                     |
| **Parameters**                              | <ul><li>`layout` - The layout table you want to load.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 177](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L177) |

---


### [saveLayout](#savelayout)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ValueIndicator:saveLayout() -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Saves the layout.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table containing the layout.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 162](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L162) |

---


### [shiftValue](#shiftvalue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ValueIndicator:shiftValue(value) -> cp.apple.finalcutpro.inspector.color.ValueIndicator`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Shifts the Value Indicator value.                                                                     |
| **Parameters**                              | <ul><li>`value` - The amount to shift the value indicator by as a number.</li></ul> |
| **Returns**                                 | <ul><li>The `cp.apple.finalcutpro.inspector.color.ValueIndicator` object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 91](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L91) |

---

