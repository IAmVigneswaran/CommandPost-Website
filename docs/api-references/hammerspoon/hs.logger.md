# hs.logger

Simple logger for debugging purposes

Note: "methods" in this module are actually "static" functions - see `hs.logger.new()`

---

## API Overview
**Variables** - _Configurable values_
 * [defaultLogLevel](#defaultloglevel)

**Functions** - _API calls offered directly by the extension_
 * [history](#history)
 * [historySize](#historysize)
 * [new](#new)
 * [printHistory](#printhistory)
 * [setGlobalLogLevel](#setgloballoglevel)
 * [setModulesLogLevel](#setmodulesloglevel)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [level](#level)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [d](#d)
 * [df](#df)
 * [e](#e)
 * [ef](#ef)
 * [f](#f)
 * [getLogLevel](#getloglevel)
 * [i](#i)
 * [setLogLevel](#setloglevel)
 * [v](#v)
 * [vf](#vf)
 * [w](#w)
 * [wf](#wf)


---

## API Documentation

#### Variables


### [defaultLogLevel](#defaultloglevel)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.defaultLogLevel`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Default log level for new logger instances.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/logger/logger.lua line 203](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L203) |

---

#### Functions


### [history](#history)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.history() -> list of log entries`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns the global log history                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a list of (at most `hs.logger.historySize()`) log entries produced by all the logger instances, in chronological order;</li><li>   each entry is a table with the following fields:</li><li>  time - timestamp in seconds since the epoch</li><li>  level - a number between 1 (error) and 5 (verbose)</li><li>  id - a string containing the id of the logger instance that produced this entry</li><li>  message - a string containing the logged message</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 94](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L94) |

---


### [historySize](#historysize)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.historySize([size]) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets or gets the global log history size                                                                     |
| **Parameters**                              | <ul><li>size - (optional) the desired number of log entries to keep in the history; if omitted, will return the current size; the starting value is 0 (disabled)</li></ul> |
| **Returns**                                 | <ul><li>the current or new history size</li></ul>          |
| **Notes**                                   | <ul><li>if you change history size (other than from 0) after creating any logger instances, things will likely break</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 69](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L69) |

---


### [new](#new)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.new(id, loglevel) -> logger`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Creates a new logger instance                                                                     |
| **Parameters**                              | <ul><li>id - a string identifier for the instance (usually the module name)</li><li>loglevel - (optional) can be 'nothing', 'error', 'warning', 'info', 'debug', or 'verbose', or a corresponding number between 0 and 5; uses `hs.logger.defaultLogLevel` if omitted</li></ul> |
| **Returns**                                 | <ul><li>the new logger instance</li></ul>          |
| **Notes**                                   | <ul><li>the logger instance created by this method is not a regular object, but a plain table with "static" functions;</li><li>   therefore, do not use the colon syntax for so-called "methods" in this module (as in `mylogger.setLogLevel(3)`);</li><li>   you must instead use the regular dot syntax: `mylogger.setLogLevel(3)`</li><li></li><li>Example:</li><li>```lua</li><li>local log = hs.logger.new('mymodule','debug')</li><li>log.i('Initializing') -- will print "[mymodule] Initializing" to the console```</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 211](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L211) |

---


### [printHistory](#printhistory)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.printHistory([entries[, level[, filter[, caseSensitive]]]])`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Prints the global log history to the console                                                                     |
| **Parameters**                              | <ul><li>entries - (optional) the maximum number of entries to print; if omitted, all entries in the history will be printed</li><li>level - (optional) the desired log level (see `hs.logger.setLogLevel()`); if omitted, defaults to `verbose`</li><li>filter - (optional) a string to filter the entries (by logger id or message) via `string.find` plain matching</li><li>caseSensitive - (optional) if true, filtering is case sensitive</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 139](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L139) |

---


### [setGlobalLogLevel](#setgloballoglevel)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.setGlobalLogLevel(lvl)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets the log level for all logger instances (including objects' loggers)                                                                     |
| **Parameters**                              | <ul><li>lvl</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 30](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L30) |

---


### [setModulesLogLevel](#setmodulesloglevel)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.setModulesLogLevel(lvl)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets the log level for all currently loaded modules                                                                     |
| **Parameters**                              | <ul><li>lvl</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>This function only affects *module*-level loggers, object instances with their own loggers (e.g. windowfilters) won't be affected;</li><li>   you can use `hs.logger.setGlobalLogLevel()` for those</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 46](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L46) |

---

#### Fields


### [level](#level)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.level`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The log level of the logger instance, as a number between 0 and 5                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/logger/logger.lua line 285](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L285) |

---

#### Methods


### [d](#d)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.d(...)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Logs debug info to the console                                                                     |
| **Parameters**                              | <ul><li>... - one or more message strings</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 352](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L352) |

---


### [df](#df)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.df(fmt,...)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Logs formatted debug info to the console                                                                     |
| **Parameters**                              | <ul><li>fmt - formatting string as per string.format</li><li>... - arguments to fmt</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 362](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L362) |

---


### [e](#e)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.e(...)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Logs an error to the console                                                                     |
| **Parameters**                              | <ul><li>... - one or more message strings</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 289](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L289) |

---


### [ef](#ef)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.ef(fmt,...)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Logs a formatted error to the console                                                                     |
| **Parameters**                              | <ul><li>fmt - formatting string as per string.format</li><li>... - arguments to fmt</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 299](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L299) |

---


### [f](#f)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.f(fmt,...)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Logs formatted info to the console                                                                     |
| **Parameters**                              | <ul><li>fmt - formatting string as per string.format</li><li>... - arguments to fmt</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 341](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L341) |

---


### [getLogLevel](#getloglevel)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.getLogLevel() -> number`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets the log level of the logger instance                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The log level of this logger as a number between 0 and 5</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 275](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L275) |

---


### [i](#i)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.i(...)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Logs info to the console                                                                     |
| **Parameters**                              | <ul><li>... - one or more message strings</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 331](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L331) |

---


### [setLogLevel](#setloglevel)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.setLogLevel(loglevel)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the log level of the logger instance                                                                     |
| **Parameters**                              | <ul><li>loglevel - can be 'nothing', 'error', 'warning', 'info', 'debug', or 'verbose'; or a corresponding number between 0 and 5</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 265](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L265) |

---


### [v](#v)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.v(...)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Logs verbose info to the console                                                                     |
| **Parameters**                              | <ul><li>... - one or more message strings</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 373](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L373) |

---


### [vf](#vf)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.vf(fmt,...)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Logs formatted verbose info to the console                                                                     |
| **Parameters**                              | <ul><li>fmt - formatting string as per string.format</li><li>... - arguments to fmt</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 383](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L383) |

---


### [w](#w)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.w(...)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Logs a warning to the console                                                                     |
| **Parameters**                              | <ul><li>... - one or more message strings</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 310](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L310) |

---


### [wf](#wf)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.logger.wf(fmt,...)`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Logs a formatted warning to the console                                                                     |
| **Parameters**                              | <ul><li>fmt - formatting string as per string.format</li><li>... - arguments to fmt</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/logger/logger.lua line 320](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/logger/logger.lua#L320) |

---

