# plugins.core.tangent.manager.named

Provides common functions for 'named' Tangent nodes

Tables with `named` in it's metatable chain will have `name` methods added
as described below.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [is](#is)
 * [xml](#xml)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [named](#named)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [active](#active)
 * [enabled](#enabled)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [controls](#controls)
 * [name](#name)
 * [nameX](#namex)
 * [parent](#parent)
 * [tangent](#tangent)


---

## API Documentation

#### Functions


### [is](#is)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.tangent.manager.named.is(thing) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Check if the `thing` is a `named` table.                                                                     |
| **Parameters**                              | <ul><li>thing     - The thing to check.</li></ul> |
| **Returns**                                 | <ul><li>`true` if it is `named.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/tangent/manager/named.lua line 238](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/tangent/manager/named.lua#L238) |

---


### [xml](#xml)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.tangent.manager.named.xml(thing) -> cp.web.xml`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the `xml` configuration for the Action.                                                                     |
| **Parameters**                              | <ul><li>thing     - The thing to retrieve the names from.</li></ul> |
| **Returns**                                 | <ul><li>The `xml` for the Action.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/tangent/manager/named.lua line 205](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/tangent/manager/named.lua#L205) |

---

#### Constructors


### [named](#named)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.tangent.manager.named(id, name, parent) -> named`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new `named` instance, with the specified base name.                                                                     |
| **Parameters**                              | <ul><li>id - the unique ID for the value.</li><li>name - The base name of the</li><li>parent - the parent</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/tangent/manager/named.lua line 24](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/tangent/manager/named.lua#L24) |

---

#### Fields


### [active](#active)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.tangent.manager.named.active <cp.prop: boolean; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Indicates if the parameter is active. It will only be active if                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/tangent/manager/named.lua line 48](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/tangent/manager/named.lua#L48) |

---


### [enabled](#enabled)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.tangent.manager.named.enabled <cp.prop: boolean>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Indicates if the parameter is enabled.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/tangent/manager/named.lua line 41](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/tangent/manager/named.lua#L41) |

---

#### Methods


### [controls](#controls)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.tangent.manager.named:controls()`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the `controls` the parameter belongs to.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `controls`, or `nil` if not specified.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/tangent/manager/named.lua line 83](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/tangent/manager/named.lua#L83) |

---


### [name](#name)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.tangent.manager.named:name(value) -> string | self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets or sets the full name.                                                                     |
| **Parameters**                              | <ul><li>value - The new name value.</li></ul> |
| **Returns**                                 | <ul><li>The current value, or `self` if a new value was provided.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/tangent/manager/named.lua line 133](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/tangent/manager/named.lua#L133) |

---


### [nameX](#namex)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.tangent.manager.named:nameX(value) -> string | self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the name `X`, where `X` is a number as defined when the `named` was created.                                                                     |
| **Parameters**                              | <ul><li>value - The new name value.</li></ul> |
| **Returns**                                 | <ul><li>The current value, or `self` if a new value was provided.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/tangent/manager/named.lua line 170](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/tangent/manager/named.lua#L170) |

---


### [parent](#parent)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.tangent.manager.named:parent() -> group | controls`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the `group` or `controls` that contains this parameter.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The parent.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/tangent/manager/named.lua line 57](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/tangent/manager/named.lua#L57) |

---


### [tangent](#tangent)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.tangent.manager.named:tangent() -> hs.tangent`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | The Tangent Hub connection for this value, from the `parent`.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `hs.tangent`, if available.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/tangent/manager/named.lua line 70](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/tangent/manager/named.lua#L70) |

---

