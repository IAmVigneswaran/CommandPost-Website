# hs.watchable

A minimalistic Key-Value-Observer framework for Lua.

This module allows you to generate a table with a defined label or path that can be used to share data with other modules or code.  Other modules can register as watchers to a specific key-value pair within the watchable object table and will be automatically notified when the key-value pair changes.

The goal is to provide a mechanism for sharing state information between separate and (mostly) unrelated code easily and in an independent fashion.

---

## API Overview
**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [new](#new)
 * [watch](#watch)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [callback](#callback)
 * [change](#change)
 * [pause](#pause)
 * [release](#release)
 * [resume](#resume)
 * [value](#value)


---

## API Documentation

#### Constructors


### [new](#new)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.watchable.new(path, [externalChanges]) -> table`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a table that can be watched by other modules for key changes                                                                     |
| **Parameters**                              | <ul><li>`path`            - the global name for this internal table that external code can refer to the table as.</li><li>`externalChanges` - an optional boolean, default false, specifying whether external code can make changes to keys within this table (bi-directional communication).</li></ul> |
| **Returns**                                 | <ul><li>a table with metamethods which will notify external code which is registered to watch this table for key-value changes.</li></ul>          |
| **Notes**                                   | <ul><li>This constructor is used by code which wishes to share state information which other code may register to watch.</li><li></li><li>You may specify any string name as a path, but it must be unique -- an error will occur if the path name has already been registered.</li><li>All key-value pairs stored within this table are potentially watchable by external code -- if you wish to keep some data private, do not store it in this table.</li><li>`externalChanges` will apply to *all* keys within this table -- if you wish to only allow some keys to be externally modifiable, you will need to register separate paths.</li><li>If external changes are enabled, you will need to register your own watcher with [hs.watchable.watch](#watch) if action is required when external changes occur.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/watchable/watchable.lua line 188](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/watchable/watchable.lua#L188) |

---


### [watch](#watch)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.watchable.watch(path, [key], callback) -> watchableObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a watcher that will be invoked when the specified key in the specified path is modified.                                                                     |
| **Parameters**                              | <ul><li>`path`     - a string specifying the path to watch.  If `key` is not provided, then this should be a string of the form "path.key" where the key will be identified as the string after the last "."</li><li>`key`      - if provided, a string specifying the specific key within the path to watch.</li><li>`callback` - an optional function which will be invoked when changes occur to the key specified within the path.  The function should expect the following arguments:
  `watcher` - the watcher object itself
  `path`    - the path being watched
  `key`     - the specific key within the path which invoked this callback
  `old`     - the old value for this key, may be nil
  `new`     - the new value for this key, may be nil</li></ul> |
| **Returns**                                 | <ul><li>a watchableObject</li></ul>          |
| **Notes**                                   | <ul><li>This constructor is used by code which wishes to watch state information which is being shared by other code.</li><li></li><li>The callback function is invoked after the new value has already been set -- the callback is a "didChange" notification, not a "willChange" notification.</li><li></li><li>If the key (specified as a separate argument or as the final component of path) is "*", then all key-value pair changes that occur for the table specified by the path will invoke a callback.  This is a shortcut for watching an entire table, rather than just a specific key-value pair of the table.</li><li>It is possible to register a watcher for a path that has not been registered with [hs.watchable.new](#new) yet. Retrieving the current value with [hs.watchable:value](#value) in such a case will return nil.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/watchable/watchable.lua line 220](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/watchable/watchable.lua#L220) |

---

#### Methods


### [callback](#callback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.watchable:callback(fn) -> watchableObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Change or remove the callback function for the watchableObject.                                                                     |
| **Parameters**                              | <ul><li>`fn` - a function, or an explicit nil to remove, specifying the new callback function to receive notifications for this watchableObject</li></ul> |
| **Returns**                                 | <ul><li>the watchableObject</li></ul>          |
| **Notes**                                   | <ul><li>see [hs.watchable.watch](#watch) for a description of the arguments the callback function should expect.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/watchable/watchable.lua line 100](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/watchable/watchable.lua#L100) |

---


### [change](#change)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.watchable:change([key], value) -> watchableObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Externally change the value of the key-value pair being watched by the watchableObject                                                                     |
| **Parameters**                              | <ul><li>`key`   - if the watchableObject was defined with a key of "*", this argument is required and specifies the specific key of the watched table to change the value of.  If a specific key was specified when the watchableObject was defined, this argument must not be provided.</li><li>`value` - the new value for the key.</li></ul> |
| **Returns**                                 | <ul><li>the watchableObject</li></ul>          |
| **Notes**                                   | <ul><li>if external changes are not allowed for the specified path, this method generates an error</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/watchable/watchable.lua line 144](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/watchable/watchable.lua#L144) |

---


### [pause](#pause)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.watchable:pause() -> watchableObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Temporarily stop notifications about the key-value pair(s) watched by this watchableObject.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the watchableObject</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/watchable/watchable.lua line 61](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/watchable/watchable.lua#L61) |

---


### [release](#release)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.watchable:release() -> nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Removes the watchableObject so that key-value pairs watched by this object no longer generate notifications.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>nil</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/watchable/watchable.lua line 81](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/watchable/watchable.lua#L81) |

---


### [resume](#resume)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.watchable:resume() -> watchableObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Resume notifications about the key-value pair(s) watched by this watchableObject which were previously paused.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the watchableObject</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/watchable/watchable.lua line 71](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/watchable/watchable.lua#L71) |

---


### [value](#value)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.watchable:value([key]) -> currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get the current value for the key-value pair being watched by the watchableObject                                                                     |
| **Parameters**                              | <ul><li>`key` - if the watchableObject was defined with a key of "*", this argument is required and specifies the specific key of the watched table to retrieve the value for.  If a specific key was specified when the watchableObject was defined, this argument is ignored.</li></ul> |
| **Returns**                                 | <ul><li>The current value for the key-value pair being watched by the watchableObject. May be nil.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/watchable/watchable.lua line 125](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/watchable/watchable.lua#L125) |

---

