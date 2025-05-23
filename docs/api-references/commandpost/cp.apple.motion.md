# cp.apple.motion

Represents the Motion application, providing functions that allow different tasks to be accomplished.

---

## Submodules
 * [cp.apple.motion.app](cp.apple.motion.app.md)

---

## API Overview
**Constants** - _Useful values which cannot be changed_
 * [BUNDLE_ID](#bundle_id)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [bundleID](#bundleid)
 * [doRestart](#dorestart)
 * [hide](#hide)
 * [launch](#launch)
 * [notifier](#notifier)
 * [path](#path)
 * [quit](#quit)
 * [show](#show)


---

## API Documentation

#### Constants


### [BUNDLE_ID](#bundle_id)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.motion.BUNDLE_ID`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Compressor's Bundle ID                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/motion/init.lua line 14](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/motion/init.lua#L14) |

---

#### Methods


### [bundleID](#bundleid)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.motion:bundleID() -> string`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the Compressor Bundle ID                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string of the Compressor Bundle ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/motion/init.lua line 96](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/motion/init.lua#L96) |

---


### [doRestart](#dorestart)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.motion:doRestart() -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a [Statement](cp.rx.go.Statement.md) that will restart the application.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if the application was running and restarted successfully.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/motion/init.lua line 141](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/motion/init.lua#L141) |

---


### [hide](#hide)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.motion:hide() -> self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Hides Compressor                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The motion instance.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/motion/init.lua line 172](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/motion/init.lua#L172) |

---


### [launch](#launch)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.motion:launch([waitSeconds]) -> self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Launches Compressor, or brings it to the front if it was already running.                                                                     |
| **Parameters**                              | <ul><li>waitSeconds      - if provided, we will wait for up to the specified seconds for the launch to complete.</li></ul> |
| **Returns**                                 | <ul><li>`true` if Compressor was either launched or focused, otherwise false (e.g. if Compressor doesn't exist)</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/motion/init.lua line 122](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/motion/init.lua#L122) |

---


### [notifier](#notifier)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.motion:notifier() -> cp.ui.notifier`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a notifier that is tracking the application UI element. It has already been started.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The notifier.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/motion/init.lua line 109](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/motion/init.lua#L109) |

---


### [path](#path)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.motion:path() -> string or nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Path to Compressor Application                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string containing Compressor's filesystem path, or `nil` if the bundle identifier could not be located</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/motion/init.lua line 208](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/motion/init.lua#L208) |

---


### [quit](#quit)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.motion:quit([waitSeconds]) -> self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Quits Compressor                                                                     |
| **Parameters**                              | <ul><li>waitSeconds  - if provided, we will wait for the specified time for the quit to complete before returning.</li></ul> |
| **Returns**                                 | <ul><li>The `motion` instance.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/motion/init.lua line 190](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/motion/init.lua#L190) |

---


### [show](#show)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.motion:show() -> self`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Activate Compressor                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The motion instance.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/motion/init.lua line 154](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/motion/init.lua#L154) |

---

