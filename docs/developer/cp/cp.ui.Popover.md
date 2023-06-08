# [docs](index.md) » cp.ui.Popover
---

UI Group.

## API Overview
* Functions - API calls offered directly by the extension
 * [matches](#matches)
* Constructors - API calls which return an object, typically one that offers API methods
 * [Popover](#Popover)
* Methods - API calls which can only be made on an object returned by a constructor
 * [doHide](#doHide)
 * [hide](#hide)

## API Documentation

### Functions

| [matches](#matches)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.Popover.matches(element) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks to see if an element matches what we think it should be.                                                                     |
| **Parameters**                              | <ul><li>element - An `axuielementObject` to check.</li></ul> |
| **Returns**                                 | <ul><li>`true` if matches otherwise `false`</li></ul>          |
| **Notes**                                   | <ul></ul>                |

### Constructors

| [Popover](#Popover)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.Popover(parent, uiFinder) -> Popover`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new `Popover` instance.                                                                     |
| **Parameters**                              | <ul><li>parent - The parent object.</li><li>uiFinder - A function which will return the `hs.axuielement` when available.</li></ul> |
| **Returns**                                 | <ul><li>A new `Popover` object.</li></ul>          |
| **Notes**                                   | <ul></ul>                |

### Methods

| [doHide](#doHide)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.Popover:doHide() -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a `Statement` which will hide the popover.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `Statement`.</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [hide](#hide)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.Popover:hide() -> Popover`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Hides a popover.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>Self</li></ul>          |
| **Notes**                                   | <ul></ul>                |
