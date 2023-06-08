# [docs](index.md) » plugins.core.setup
---

Manager for the CommandPost Setup Screen.

## Submodules
 * [plugins.core.setup.panel](plugins.core.setup.panel.md)

## API Overview
* Constants - Useful values which cannot be changed
 * [DEFAULT_HEIGHT](#DEFAULT_HEIGHT)
 * [DEFAULT_TITLE](#DEFAULT_TITLE)
 * [DEFAULT_WIDTH](#DEFAULT_WIDTH)
 * [enabled](#enabled)
 * [FIRST_PRIORITY](#FIRST_PRIORITY)
 * [LAST_PRIORITY](#LAST_PRIORITY)
 * [visible](#visible)
* Variables - Configurable values
 * [onboardingRequired](#onboardingRequired)
 * [position](#position)
* Functions - API calls offered directly by the extension
 * [addPanel](#addPanel)
 * [currentPanel](#currentPanel)
 * [delete](#delete)
 * [focus](#focus)
 * [getLabel](#getLabel)
 * [injectScript](#injectScript)
 * [new](#new)
 * [nextPanel](#nextPanel)
 * [setPanelRenderer](#setPanelRenderer)
 * [show](#show)
 * [update](#update)

## API Documentation

### Constants

| [DEFAULT_HEIGHT](#DEFAULT_HEIGHT)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.DEFAULT_HEIGHT -> number`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The default panel height.                                                                     |

| [DEFAULT_TITLE](#DEFAULT_TITLE)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.DEFAULT_TITLE -> string`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The default panel title.                                                                     |

| [DEFAULT_WIDTH](#DEFAULT_WIDTH)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.DEFAULT_WIDTH -> number`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The default panel width.                                                                     |

| [enabled](#enabled)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.enabled <cp.prop: boolean>`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Set to `true` if the manager is enabled. Defaults to `false`.                                                                     |

| [FIRST_PRIORITY](#FIRST_PRIORITY)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.FIRST_PRIORITY -> number`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The first panel priority.                                                                     |

| [LAST_PRIORITY](#LAST_PRIORITY)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.LAST_PRIORITY -> number`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The last panel priority.                                                                     |

| [visible](#visible)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.visible <cp.prop: boolean; read-only>`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A property indicating if the welcome window is visible on screen.                                                                     |

### Variables

| [onboardingRequired](#onboardingRequired)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.onboardingRequired <cp.prop: boolean>`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Set to `true` if on-boarding is required otherwise `false`. Defaults to `true`.                                                                     |

| [position](#position)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.position <cp.prop: table>`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | The last known position of the Setup Window as a frame.                                                                     |

### Functions

| [addPanel](#addPanel)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.addPanel(newPanel) -> panel`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Adds the new panel to the manager. Panels are created via the `plugins.core.setup.panel.new(...)` function.                                                                     |
| **Parameters**                              | <ul><li>`newPanel`   - The panel to add.</li></ul> |
| **Returns**                                 | <ul><li>The manager.</li></ul>          |
| **Notes**                                   | <ul><li>If the Setup Manager is `enabled`, the window will be displayed immediately when a panel is added.</li></ul>                |

| [currentPanel](#currentPanel)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.currentPanel() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | The Current Panel                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The current panel as a string</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [delete](#delete)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.delete() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Deletes the Setup Panels.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [focus](#focus)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.focus() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Focuses on the Setup Panels window.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [getLabel](#getLabel)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.getLabel() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the Webview label.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The Webview label as a string.</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [injectScript](#injectScript)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.injectScript(script) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Injects JavaScript into the Setup Panels.                                                                     |
| **Parameters**                              | <ul><li>script - The JavaScript you want to inject as a string.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [new](#new)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.new() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Creates the Setup Panels.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [nextPanel](#nextPanel)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.nextPanel() -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Moves to the next panel. If the window is visible, the panel will be updated. If no panels are left in the queue, the window will be closed.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if there was another panel to move to, or `false` if no panels remain.</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [setPanelRenderer](#setPanelRenderer)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.setPanelRenderer(renderer) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets a Panel Renderer                                                                     |
| **Parameters**                              | <ul><li>renderer - The renderer</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [show](#show)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.show() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Shows the Setup Panels.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [update](#update)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.setup.update() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Updates the Setup Panels.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |
