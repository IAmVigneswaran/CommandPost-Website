# hs.caffeinate.watcher

Watch for display and system sleep/wake/power events
and for fast user switching session events.

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

---

## API Overview
**Constants** - _Useful values which cannot be changed_
 * [screensaverDidStart](#screensaverdidstart)
 * [screensaverDidStop](#screensaverdidstop)
 * [screensaverWillStop](#screensaverwillstop)
 * [screensDidLock](#screensdidlock)
 * [screensDidSleep](#screensdidsleep)
 * [screensDidUnlock](#screensdidunlock)
 * [screensDidWake](#screensdidwake)
 * [sessionDidBecomeActive](#sessiondidbecomeactive)
 * [sessionDidResignActive](#sessiondidresignactive)
 * [systemDidWake](#systemdidwake)
 * [systemWillPowerOff](#systemwillpoweroff)
 * [systemWillSleep](#systemwillsleep)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [new](#new)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [start](#start)
 * [stop](#stop)


---

## API Documentation

#### Constants


### [screensaverDidStart](#screensaverdidstart)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.screensaverDidStart`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The screensaver started                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 42](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L42) |

---


### [screensaverDidStop](#screensaverdidstop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.screensaverDidStop`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The screensaver stopped                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 50](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L50) |

---


### [screensaverWillStop](#screensaverwillstop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.screensaverWillStop`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The screensaver is about to stop                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 46](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L46) |

---


### [screensDidLock](#screensdidlock)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.screensDidLock`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The screen was locked                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 54](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L54) |

---


### [screensDidSleep](#screensdidsleep)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.screensDidSleep`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The displays have gone to sleep                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 26](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L26) |

---


### [screensDidUnlock](#screensdidunlock)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.screensDidUnlock`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The screen was unlocked                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 58](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L58) |

---


### [screensDidWake](#screensdidwake)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.screensDidWake`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The displays have woken from sleep                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 30](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L30) |

---


### [sessionDidBecomeActive](#sessiondidbecomeactive)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.sessionDidBecomeActive`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The session became active, due to fast user switching                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 38](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L38) |

---


### [sessionDidResignActive](#sessiondidresignactive)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.sessionDidResignActive`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The session is no longer active, due to fast user switching                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 34](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L34) |

---


### [systemDidWake](#systemdidwake)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.systemDidWake`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The system woke from sleep                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 14](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L14) |

---


### [systemWillPowerOff](#systemwillpoweroff)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.systemWillPowerOff`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The user requested a logout or shutdown                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 22](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L22) |

---


### [systemWillSleep](#systemwillsleep)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.systemWillSleep`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | The system is preparing to sleep                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 18](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L18) |

---

#### Constructors


### [new](#new)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher.new(fn) -> watcher`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a watcher object for system and display sleep/wake/power events                                                                     |
| **Parameters**                              | <ul><li>fn - A function that will be called when system/display events happen. It should accept one parameter:
  An event type (see the constants defined above)</li></ul> |
| **Returns**                                 | <ul><li>An `hs.caffeinate.watcher` object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 170](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L170) |

---

#### Methods


### [start](#start)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher:start()`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Starts the sleep/wake watcher                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An `hs.caffeinate.watcher` object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 277](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L277) |

---


### [stop](#stop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.caffeinate.watcher:stop()`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Stops the sleep/wake watcher                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>An `hs.caffeinate.watcher` object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/caffeinate/libcaffeinate_watcher.m line 301](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/caffeinate/libcaffeinate_watcher.m#L301) |

---

