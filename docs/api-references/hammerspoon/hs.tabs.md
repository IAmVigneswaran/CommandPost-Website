# hs.tabs

Place the windows of an application into tabs drawn on its titlebar

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [enableForApp](#enableforapp)
 * [focusTab](#focustab)
 * [tabWindows](#tabwindows)


---

## API Documentation

#### Functions


### [enableForApp](#enableforapp)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.tabs.enableForApp(app)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Places all the windows of an app into one place and tab them                                                                     |
| **Parameters**                              | <ul><li>app - An `hs.application` object or the app title</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/tabs/tabs.lua line 145](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/tabs/tabs.lua#L145) |

---


### [focusTab](#focustab)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.tabs.focusTab(app, num)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Focuses a specific tab of an app                                                                     |
| **Parameters**                              | <ul><li>app - An `hs.application` object previously enabled for tabbing</li><li>num - A tab number to switch to</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>If num is higher than the number of tabs, the last tab will be focussed</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/tabs/tabs.lua line 180](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/tabs/tabs.lua#L180) |

---


### [tabWindows](#tabwindows)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.tabs.tabWindows(app)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets a list of the tabs of a window                                                                     |
| **Parameters**                              | <ul><li>app - An `hs.application` object</li></ul> |
| **Returns**                                 | <ul><li>An array of the tabbed windows of an app in the same order as they would be tabbed</li></ul>          |
| **Notes**                                   | <ul><li>This function can be used when writing tab switchers</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/tabs/tabs.lua line 33](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/tabs/tabs.lua#L33) |

---

