# hs.axuielement.observer

This submodule allows you to create observers for accessibility elements and be notified when they trigger notifications. Not all notifications are supported by all elements and not all elements support notifications, so some trial and error will be necessary, but for compliant applications, this can allow your code to be notified when an application's user interface changes in some way.

---

## API Overview
**Constants** - _Useful values which cannot be changed_
 * [notifications](#notifications)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [new](#new)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [addWatcher](#addwatcher)
 * [callback](#callback)
 * [isRunning](#isrunning)
 * [removeWatcher](#removewatcher)
 * [start](#start)
 * [stop](#stop)
 * [watching](#watching)


---

## API Documentation

#### Constants


### [notifications](#notifications)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.observer.notifications[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of common accessibility object notification names, provided for reference.                                                                     |
| **Notes**                                   | <ul><li>Notifications are application dependent and can be any string that the application developers choose; this list provides the suggested notification names found within the macOS Framework headers, but the list is not exhaustive nor is an application or element required to provide them.</li></ul> |
| **Source**                                  | [extensions/axuielement/observer.m line 402](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/observer.m#L402) |

---

#### Constructors


### [new](#new)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.observer.new(pid) -> observerObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new observer object for the application with the specified process ID.                                                                     |
| **Parameters**                              | <ul><li>`pid` - the process ID of the application.</li></ul> |
| **Returns**                                 | <ul><li>a new observerObject; generates an error if the pid does not exist or if the object cannot be created.</li></ul>          |
| **Notes**                                   | <ul><li>If you already have the `hs.application` object for an application, you can get its process ID with `hs.application:pid()`</li><li>If you already have an `hs.axuielement` from the application you wish to observe (it doesn't have to be the application axuielement object, just one belonging to the application), you can get the process ID with `hs.axuielement:pid()`.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/observer.m line 117](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/observer.m#L117) |

---

#### Methods


### [addWatcher](#addwatcher)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.observer:addWatcher(element, notification) -> observerObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Registers the specified notification for the specified accessibility element with the observer.                                                                     |
| **Parameters**                              | <ul><li>`element`      - the `hs.axuielement` representing an accessibility element of the application the observer was created for.</li><li>`notification` - a string specifying the notification.</li></ul> |
| **Returns**                                 | <ul><li>the observerObject; generates an error if watcher cannot be registered</li></ul>          |
| **Notes**                                   | <ul><li>multiple notifications for the same accessibility element can be registered by invoking this method multiple times with the same element but different notification strings.</li><li>if the specified element and notification string are already registered, this method does nothing.</li><li>the notification string is application dependent and can be any string that the application developers choose; some common ones are found in `hs.axuielement.observer.notifications`, but the list is not exhaustive nor is an application or element required to provide them.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/observer.m line 263](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/observer.m#L263) |

---


### [callback](#callback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.observer:callback([fn]) -> observerObject | fn | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the callback for the observer.                                                                     |
| **Parameters**                              | <ul><li>`fn` - a function, or an explicit nil to remove, specifying the callback function the observer will invoke when the assigned elements generate notifications.</li></ul> |
| **Returns**                                 | <ul><li>If an argument is provided, the observerObject; otherwise the current value.</li></ul>          |
| **Notes**                                   | <ul><li>the callback should expect 4 arguments and return none. The arguments passed to the callback will be as follows:</li><li>  the observerObject itself</li><li>  the `hs.axuielement` object for the accessibility element which generated the notification</li><li>  a string specifying the specific notification which was received</li><li>  a table containing key-value pairs with more information about the notification, if the element and notification type provide it. Commonly this will be an empty table indicating that no additional detail was provided.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/observer.m line 221](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/observer.m#L221) |

---


### [isRunning](#isrunning)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.observer:isRunning() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns true or false indicating whether the observer is currently watching for notifications and generating callbacks.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a boolean value indicating whether or not the observer is currently active.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/observer.m line 202](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/observer.m#L202) |

---


### [removeWatcher](#removewatcher)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.observer:removeWatcher(element, notification) -> observerObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Unregisters the specified notification for the specified accessibility element from the observer.                                                                     |
| **Parameters**                              | <ul><li>`element`      - the `hs.axuielement` representing an accessibility element of the application the observer was created for.</li><li>`notification` - a string specifying the notification.</li></ul> |
| **Returns**                                 | <ul><li>the observerObject; generates an error if watcher cannot be unregistered</li></ul>          |
| **Notes**                                   | <ul><li>if the specified element and notification string are not currently registered with the observer, this method does nothing.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/observer.m line 308](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/observer.m#L308) |

---


### [start](#start)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.observer:start() -> observerObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Start observing the application and trigger callbacks for the elements and notifications assigned.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the observerObject</li></ul>          |
| **Notes**                                   | <ul><li>This method does nothing if the observer is already running</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/observer.m line 148](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/observer.m#L148) |

---


### [stop](#stop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.observer:stop() -> observerObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Stop observing the application; no further callbacks will be generated.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the observerObject</li></ul>          |
| **Notes**                                   | <ul><li>This method does nothing if the observer is not currently running</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/observer.m line 175](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/observer.m#L175) |

---


### [watching](#watching)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.observer:watching([element]) -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a table of the notifications currently registered with the observer.                                                                     |
| **Parameters**                              | <ul><li>`element` - an optional `hs.axuielement` to return a list of registered notifications for.</li></ul> |
| **Returns**                                 | <ul><li>a table containing the currently registered notifications</li></ul>          |
| **Notes**                                   | <ul><li>If an element is specified, then the table returned will contain a list of strings specifying the specific notifications that the observer is watching that element for.</li><li>If no argument is specified, then the table will contain key-value pairs in which each key will be an `hs.axuielement` that is being observed and the corresponding value will be a table containing a list of strings specifying the specific notifications that the observer is watching for from that element.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/observer.m line 348](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/observer.m#L348) |

---

