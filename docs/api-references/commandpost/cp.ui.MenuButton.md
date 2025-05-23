# cp.ui.MenuButton

Menu Button Module.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [matches](#matches)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [MenuButton](#menubutton)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [menuUI](#menuui)
 * [title](#title)
 * [value](#value)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [doPress](#dopress)
 * [doSelectItem](#doselectitem)
 * [doSelectItemMatching](#doselectitemmatching)
 * [doSelectValue](#doselectvalue)
 * [doShowMenu](#doshowmenu)
 * [getTitle](#gettitle)
 * [getValue](#getvalue)
 * [loadLayout](#loadlayout)
 * [press](#press)
 * [saveLayout](#savelayout)
 * [selectItem](#selectitem)
 * [selectItemMatching](#selectitemmatching)
 * [setValue](#setvalue)
 * [show](#show)


---

## API Documentation

#### Functions


### [matches](#matches)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton.matches(element) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks to see if an element matches what we think it should be.                                                                     |
| **Parameters**                              | <ul><li>element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                 | <ul><li>`true` if matches otherwise `false`</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 26](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L26) |

---

#### Constructors


### [MenuButton](#menubutton)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton(parent, uiFinder) -> MenuButton`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new MenuButton.                                                                     |
| **Parameters**                              | <ul><li>parent        - The parent object. Should have an `isShowing` property.</li><li>uiFinder      - A `cp.prop` or function which will return a `hs.axuielement`, or `nil` if it's not available.</li></ul> |
| **Returns**                                 | <ul></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 39](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L39) |

---

#### Fields


### [menuUI](#menuui)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton.menuUI <cp.prop: hs.axuielement; read-only; live?>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns the `AXMenu` for the MenuButton if it is currently visible.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 80](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L80) |

---


### [title](#title)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton.title <cp.prop: string; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns the title for the MenuButton.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 100](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L100) |

---


### [value](#value)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton.value <cp.prop: anything>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns or sets the current MenuButton value.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 47](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L47) |

---

#### Methods


### [doPress](#dopress)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:doPress() -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that presses the `MenuButton`.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The [Statement](cp.rx.go.Statement.md)</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 311](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L311) |

---


### [doSelectItem](#doselectitem)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:doSelectItem(index) -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that will select an item on the `MenuButton` by index.                                                                     |
| **Parameters**                              | <ul><li>index - The index number of the item to match.</li></ul> |
| **Returns**                                 | <ul><li>the `Statement`.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 154](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L154) |

---


### [doSelectItemMatching](#doselectitemmatching)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:doSelectItemMatching(pattern[, altPattern]) -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that will select an item on the `MenuButton` by pattern.                                                                     |
| **Parameters**                              | <ul><li>pattern - The pattern to match.</li><li>[altPattern] - An optional alternate pattern to match if the first pattern fails.</li></ul> |
| **Returns**                                 | <ul><li>the `Statement`.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 237](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L237) |

---


### [doSelectValue](#doselectvalue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:doSelectValue(value) -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that will select an item on the `MenuButton` by value.                                                                     |
| **Parameters**                              | <ul><li>value - The value of the item to match.</li></ul> |
| **Returns**                                 | <ul><li>the `Statement`.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 170](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L170) |

---


### [doShowMenu](#doshowmenu)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:doShowMenu() -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that presses the `MenuButton` if the menu is not showing.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The [Statement](cp.rx.go.Statement.md)</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 330](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L330) |

---


### [getTitle](#gettitle)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:getTitle() -> string | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the `MenuButton` title.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `MenuButton` title as string, or `nil` if the title cannot be determined.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 254](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L254) |

---


### [getValue](#getvalue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:getValue() -> string | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the `MenuButton` value.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `MenuButton` value as string, or `nil` if the value cannot be determined.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 267](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L267) |

---


### [loadLayout](#loadlayout)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:loadLayout(layout) -> none`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Loads a `MenuButton` layout.                                                                     |
| **Parameters**                              | <ul><li>layout - A table containing the `MenuButton` layout settings - created using [saveLayout](#saveLayout).</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 360](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L360) |

---


### [press](#press)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:press() -> self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Presses the MenuButton.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>self</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 294](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L294) |

---


### [saveLayout](#savelayout)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:saveLayout() -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Saves the current `MenuButton` layout to a table.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table containing the current `MenuButton` Layout.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 345](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L345) |

---


### [selectItem](#selectitem)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:selectItem(index) -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Select an item on the `MenuButton` by index.                                                                     |
| **Parameters**                              | <ul><li>index - The index of the item you want to select.</li></ul> |
| **Returns**                                 | <ul><li>`true` if successfully selected, otherwise `false`.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 124](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L124) |

---


### [selectItemMatching](#selectitemmatching)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:selectItemMatching(pattern) -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Select an item on the `MenuButton` by pattern.                                                                     |
| **Parameters**                              | <ul><li>pattern - A pattern used to select the `MenuButton` item.</li></ul> |
| **Returns**                                 | <ul><li>`true` if successfully selected, otherwise `false`.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 186](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L186) |

---


### [setValue](#setvalue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:setValue(value) -> self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the `MenuButton` value.                                                                     |
| **Parameters**                              | <ul><li>value - The value you want to set the `MenuButton` to.</li></ul> |
| **Returns**                                 | <ul><li>self</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 280](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L280) |

---


### [show](#show)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.MenuButton:show() -> self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Show's the MenuButton.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>self</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/MenuButton.lua line 107](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/MenuButton.lua#L107) |

---

