# cp.apple.finalcutpro.main.BackgroundTasksDialog

Represents the Background Tasks warning dialog.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [matches](#matches)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [BackgroundTasksDialog](#backgroundtasksdialog)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [cancel](#cancel)
 * [continue](#continue)


---

## API Documentation

#### Functions


### [matches](#matches)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.main.BackgroundTasksDialog.matches(element) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks if the element is an `BackgroundTasksDialog` instance.                                                                     |
| **Parameters**                              | <ul><li>element - The `axuielement` to check.</li></ul> |
| **Returns**                                 | <ul><li>`true` if it matches the pattern for a `BackgroundTasksDialog``.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/main/BackgroundTasksDialog.lua line 18](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/main/BackgroundTasksDialog.lua#L18) |

---

#### Constructors


### [BackgroundTasksDialog](#backgroundtasksdialog)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.main.BackgroundTasksDialog(cpApp)`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new Background Tasks [Dialog](cp.ui.Dialog.md)                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/main/BackgroundTasksDialog.lua line 38](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/main/BackgroundTasksDialog.lua#L38) |

---

#### Fields


### [cancel](#cancel)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.main.BackgroundTasksDialog.cancel <cp.ui.Button>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The Cancel button.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/main/BackgroundTasksDialog.lua line 55](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/main/BackgroundTasksDialog.lua#L55) |

---


### [continue](#continue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.main.BackgroundTasksDialog.continue <cp.ui.Button>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The Continue button.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/main/BackgroundTasksDialog.lua line 66](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/main/BackgroundTasksDialog.lua#L66) |

---

