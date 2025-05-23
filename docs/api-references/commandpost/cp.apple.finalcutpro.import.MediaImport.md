# cp.apple.finalcutpro.import.MediaImport

Media Import

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [matches](#matches)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [MediaImport](#mediaimport)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [importAll](#importall)
 * [stopImport](#stopimport)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [hide](#hide)
 * [show](#show)


---

## API Documentation

#### Functions


### [matches](#matches)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.import.MediaImport.matches(element) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks to see if an element matches what we think it should be.                                                                     |
| **Parameters**                              | <ul><li>element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                 | <ul><li>`true` if matches otherwise `false`</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/import/MediaImport.lua line 35](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/import/MediaImport.lua#L35) |

---

#### Constructors


### [MediaImport](#mediaimport)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.import.MediaImport(app) -> MediaImport`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new Media Import object.                                                                     |
| **Parameters**                              | <ul><li>app - The `cp.apple.finalcutpro` object.</li></ul> |
| **Returns**                                 | <ul><li>A new MediaImport object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/import/MediaImport.lua line 53](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/import/MediaImport.lua#L53) |

---

#### Fields


### [importAll](#importall)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.import.MediaImport.importAll <cp.ui.Button>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The Import All button.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/import/MediaImport.lua line 74](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/import/MediaImport.lua#L74) |

---


### [stopImport](#stopimport)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.import.MediaImport.stopImport <cp.ui.Button>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The "Stop Import" button.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/import/MediaImport.lua line 81](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/import/MediaImport.lua#L81) |

---

#### Methods


### [hide](#hide)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.import.MediaImport:hide() -> cp.apple.finalcutpro.import.MediaImport`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Hides the Media Import window.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `cp.apple.finalcutpro.import.MediaImport` object for method chaining.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/import/MediaImport.lua line 110](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/import/MediaImport.lua#L110) |

---


### [show](#show)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.import.MediaImport:show() -> cp.apple.finalcutpro.import.MediaImport`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Shows the Media Import window.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `cp.apple.finalcutpro.import.MediaImport` object for method chaining.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/import/MediaImport.lua line 90](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/import/MediaImport.lua#L90) |

---

