# hs.window.switcher

Window-based cmd-tab replacement

Usage:
```
-- set up your windowfilter
switcher = hs.window.switcher.new() -- default windowfilter: only visible windows, all Spaces
switcher_space = hs.window.switcher.new(hs.window.filter.new():setCurrentSpace(true):setDefaultFilter{}) -- include minimized/hidden windows, current Space only
switcher_browsers = hs.window.switcher.new{'Safari','Google Chrome'} -- specialized switcher for your dozens of browser windows :)

-- bind to hotkeys; WARNING: at least one modifier key is required!
hs.hotkey.bind('alt','tab','Next window',function()switcher:next()end)
hs.hotkey.bind('alt-shift','tab','Prev window',function()switcher:previous()end)

-- alternatively, call .nextWindow() or .previousWindow() directly (same as hs.window.switcher.new():next())
hs.hotkey.bind('alt','tab','Next window',hs.window.switcher.nextWindow)
-- you can also bind to `repeatFn` for faster traversing
hs.hotkey.bind('alt-shift','tab','Prev window',hs.window.switcher.previousWindow,nil,hs.window.switcher.previousWindow)
```

---

## API Overview
**Variables** - _Configurable values_
 * [ui](#ui)

**Functions** - _API calls offered directly by the extension_
 * [nextWindow](#nextwindow)
 * [previousWindow](#previouswindow)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [new](#new)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [next](#next)
 * [previous](#previous)


---

## API Documentation

#### Variables


### [ui](#ui)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.window.switcher.ui`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Allows customization of the switcher behaviour and user interface                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/window/window_switcher.lua line 53](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/window/window_switcher.lua#L53) |

---

#### Functions


### [nextWindow](#nextwindow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.window.switcher.nextWindow()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Shows the switcher (if not yet visible) and selects the next window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>the switcher will be dismissed (and the selected window focused) when all modifier keys are released</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/window/window_switcher.lua line 318](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/window/window_switcher.lua#L318) |

---


### [previousWindow](#previouswindow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.window.switcher.previousWindow()`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Shows the switcher (if not yet visible) and selects the previous window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>the switcher will be dismissed (and the selected window focused) when all modifier keys are released</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/window/window_switcher.lua line 331](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/window/window_switcher.lua#L331) |

---

#### Constructors


### [new](#new)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.window.switcher.new([windowfilter[, uiPrefs][, logname, [loglevel]]]) -> hs.window.switcher object`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new switcher instance; it can use a windowfilter to determine which windows to show                                                                     |
| **Parameters**                              | <ul><li>windowfilter - (optional) if omitted or nil, use the default windowfilter; otherwise it must be a windowfilter instance or constructor table</li><li>uiPrefs - (optional) a table to override UI preferences for this instance; its keys and values must follow the conventions described in `hs.window.switcher.ui`; this parameter allows you to have multiple switcher instances with different behaviour (for example, with and without thumbnails and/or titles) using different hotkeys</li><li>logname - (optional) name of the `hs.logger` instance for the new switcher; if omitted, the class logger will be used</li><li>loglevel - (optional) log level for the `hs.logger` instance for the new switcher</li></ul> |
| **Returns**                                 | <ul><li>the new instance</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/window/window_switcher.lua line 393](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/window/window_switcher.lua#L393) |

---

#### Methods


### [next](#next)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.window.switcher:next()`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Shows the switcher instance (if not yet visible) and selects the next window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>the switcher will be dismissed (and the selected window focused) when all modifier keys are released</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/window/window_switcher.lua line 285](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/window/window_switcher.lua#L285) |

---


### [previous](#previous)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.window.switcher:previous()`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Shows the switcher instance (if not yet visible) and selects the previous window                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>the switcher will be dismissed (and the selected window focused) when all modifier keys are released</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/window/window_switcher.lua line 298](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/window/window_switcher.lua#L298) |

---

