# plugins.core.controlsurfaces.manager.panel

CommandPost Control Surfaces Panel.

---

## API Overview
**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [new](#new)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [addButton](#addbutton)
 * [addCheckbox](#addcheckbox)
 * [addContent](#addcontent)
 * [addHandler](#addhandler)
 * [addHeading](#addheading)
 * [addParagraph](#addparagraph)
 * [addPassword](#addpassword)
 * [addSelect](#addselect)
 * [addTextbox](#addtextbox)
 * [getToolbarItem](#gettoolbaritem)


---

## API Documentation

#### Constructors


### [new](#new)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel.new(params, manager) -> cp.core.controlsurfaces.manager.panel`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Constructs a new panel with the specified priority and ID.                                                                     |
| **Parameters**                              | <ul><li>params - A table of parameters</li><li>manager - The manager</li></ul> |
| **Returns**                                 | <ul><li>The new object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 16](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L16) |

---

#### Methods


### [addButton](#addbutton)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel:addButton(params) -> panel`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Adds a button to the panel.                                                                     |
| **Parameters**                              | <ul><li>params - The list of parameters.</li></ul> |
| **Returns**                                 | <ul><li>The same panel.</li></ul>          |
| **Notes**                                   | <ul><li>The `params` table may contain:</li><li> ** `id`        - (optional) the unique ID for the button. If none is provided, one is generated.</li><li> ** `value`     - The value of the button. This is sent to the `onclick` function.</li><li> ** `label`     - The text label for the button. Defaults to the `value` if not provided.</li><li> ** `width`     - The width of the button in pixels.</li><li> ** `onclick`   - the function to execute when the button is clicked. The function should have the signature of `function(id, value)`, where `id` is the id of the button that was clicked, and `value` is the value of the button.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 305](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L305) |

---


### [addCheckbox](#addcheckbox)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel:addCheckbox(priority, params) -> panel`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Adds a checkbox to the panel with the specified `priority` and `params`.                                                                     |
| **Parameters**                              | <ul><li>`priority`   - The priority number for the checkbox.</li><li>`params`     - The set of parameters for the checkbox.</li></ul> |
| **Returns**                                 | <ul><li>The panel.</li></ul>          |
| **Notes**                                   | <ul><li>The `params` can contain the following fields:</li><li> ** `id`         - (optional) The unique ID. If none is provided, one will be generated.</li><li> ** `name`       - (optional) The name of the checkbox field.</li><li> ** `label`      - (optional) The text label to display after the checkbox.</li><li> ** `onchange`   - (optional) a function that will get called when the checkbox value changes. It will be passed two parameters, `id` and `params`, the latter of which is a table containing the `value` and `checked` values of the checkbox.</li><li> ** `class`      - (optional) the CSS class list to apply to the checkbox.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 200](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L200) |

---


### [addContent](#addcontent)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel:addContent(priority, content[, escaped]) -> panel`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Adds the specified `content` to the panel, with the specified `priority` order.                                                                     |
| **Parameters**                              | <ul><li>`priority`        - the priority order of the content.</li><li>`content`         - a value that can be converted to a string.</li><li>`escaped`         - if `true`, the content will be escaped.</li></ul> |
| **Returns**                                 | <ul><li>The panel.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 109](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L109) |

---


### [addHandler](#addhandler)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel:addHandler(event, id, handlerFn, keys) -> none`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets a handler from an Handler ID                                                                     |
| **Parameters**                              | <ul><li>event - The event</li><li>id - the Handler ID</li><li>handlerFn - The Handler function</li><li>keys - Keys</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 132](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L132) |

---


### [addHeading](#addheading)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel:addHeading(text) -> panel`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Adds a heading to the panel                                                                     |
| **Parameters**                              | <ul><li>text - The text of the heading as a string</li></ul> |
| **Returns**                                 | <ul><li>The panel object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 238](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L238) |

---


### [addParagraph](#addparagraph)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel:addParagraph(content[, escaped[, class]]) -> panel`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Adds a Paragraph to the panel                                                                     |
| **Parameters**                              | <ul><li>content - The content as a string</li><li>escaped - Whether or not the HTML should be escaped as a boolean. Defaults to `true` for simple text.</li><li>class - The class as a string</li></ul> |
| **Returns**                                 | <ul><li>The panel object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 185](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L185) |

---


### [addPassword](#addpassword)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel:addPassword(params) -> panel`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Adds a password text-box to the panel.                                                                     |
| **Parameters**                              | <ul><li>params - A table of parameters</li></ul> |
| **Returns**                                 | <ul><li>The panel object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 278](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L278) |

---


### [addSelect](#addselect)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel:addSelect(priority, params) -> panel`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Adds a select to the panel.                                                                     |
| **Parameters**                              | <ul><li>priority - Priority of the item as number.</li><li>params - A table of parameters</li></ul> |
| **Returns**                                 | <ul><li>The panel object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 334](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L334) |

---


### [addTextbox](#addtextbox)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel:addTextbox(params) -> panel`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Adds a text-box to the panel                                                                     |
| **Parameters**                              | <ul><li>params - A table of parameters</li></ul> |
| **Returns**                                 | <ul><li>The panel object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 251](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L251) |

---


### [getToolbarItem](#gettoolbaritem)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.controlsurfaces.manager.panel:getToolbarItem() -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the Tool Bar as a table                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The toolbar item as a table.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/controlsurfaces/manager/panel.lua line 46](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/controlsurfaces/manager/panel.lua#L46) |

---

