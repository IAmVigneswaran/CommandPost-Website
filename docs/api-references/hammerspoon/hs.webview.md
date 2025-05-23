# hs.webview

Display web content in a window from Hammerspoon

This module uses Apple's WebKit WKWebView class to provide web content display with JavaScript injection support.  The objective is to provide a functional interface to the WKWebView and WKUserContentController classes.

This module is not intended to replace a full web browser and does have some limitations to keep in mind:
  * Self-signed SSL certificates are not accepted unless they have first been approved and included in the users Keychain by another method, for example, opening the page first in Safari.
  * The context-menu (right clicking or ctrl-clicking in the webview) provides some menu items which are currently unsupported -- a known example of this is any "Download..." menu item in the context menu for links and images.
  * It is uncertain at present exactly how or where cookies and cached page data is stored or how it can be invalidated.
    * This can be mitigated to an extent for web requests by using `hs.webview:reload(true)` and by crafting the url for `hs.webview:url({...})` as a table -- see the appropriate help entries for more information.

Any suggestions or updates to the code to address any of these or other limitations as they may become apparent are welcome at the Hammerspoon github site: https://www.github.com/Hammerspoon/hammerspoon


---

## Submodules
 * [hs.webview.datastore](hs.webview.datastore.md)
 * [hs.webview.toolbar](hs.webview.toolbar.md)
 * [hs.webview.usercontent](hs.webview.usercontent.md)

---

## API Overview
**Deprecateds** - _API features which will be removed in an future release_
 * [asHSDrawing](#ashsdrawing)
 * [asHSWindow](#ashswindow)
 * [setLevel](#setlevel)

**Constants** - _Useful values which cannot be changed_
 * [certificateOIDs](#certificateoids)
 * [windowMasks](#windowmasks)

**Functions** - _API calls offered directly by the extension_
 * [titleVisibility](#titlevisibility)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [new](#new)
 * [newBrowser](#newbrowser)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [allowGestures](#allowgestures)
 * [allowMagnificationGestures](#allowmagnificationgestures)
 * [allowNavigationGestures](#allownavigationgestures)
 * [allowNewWindows](#allownewwindows)
 * [allowTextEntry](#allowtextentry)
 * [alpha](#alpha)
 * [attachedToolbar](#attachedtoolbar)
 * [behavior](#behavior)
 * [behaviorAsLabels](#behavioraslabels)
 * [bringToFront](#bringtofront)
 * [certificateChain](#certificatechain)
 * [children](#children)
 * [closeOnEscape](#closeonescape)
 * [darkMode](#darkmode)
 * [delete](#delete)
 * [deleteOnClose](#deleteonclose)
 * [estimatedProgress](#estimatedprogress)
 * [evaluateJavaScript](#evaluatejavascript)
 * [examineInvalidCertificates](#examineinvalidcertificates)
 * [frame](#frame)
 * [goBack](#goback)
 * [goForward](#goforward)
 * [hide](#hide)
 * [historyList](#historylist)
 * [hswindow](#hswindow)
 * [html](#html)
 * [isOnlySecureContent](#isonlysecurecontent)
 * [isVisible](#isvisible)
 * [level](#level)
 * [loading](#loading)
 * [magnification](#magnification)
 * [navigationCallback](#navigationcallback)
 * [navigationID](#navigationid)
 * [orderAbove](#orderabove)
 * [orderBelow](#orderbelow)
 * [parent](#parent)
 * [policyCallback](#policycallback)
 * [privateBrowsing](#privatebrowsing)
 * [reload](#reload)
 * [sendToBack](#sendtoback)
 * [shadow](#shadow)
 * [show](#show)
 * [size](#size)
 * [sslCallback](#sslcallback)
 * [stopLoading](#stoploading)
 * [title](#title)
 * [topLeft](#topleft)
 * [transparent](#transparent)
 * [url](#url)
 * [urlParts](#urlparts)
 * [userAgent](#useragent)
 * [windowCallback](#windowcallback)
 * [windowStyle](#windowstyle)
 * [windowTitle](#windowtitle)


---

## API Documentation

#### Deprecateds


### [asHSDrawing](#ashsdrawing)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:asHSDrawing() -> hs.drawing object`                                                                    |
| **Type**                                    | Deprecated                                                                     |
| **Description**                             | Because use of this method can easily lead to a crash, useful methods from `hs.drawing` have been added to the `hs.webview` module itself.  If you believe that a useful method has been overlooked, please submit an issue.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a placeholder object</li></ul>          |
| **Notes**                                   | None |
| **Source**                                  | [extensions/webview/webview.lua line 346](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L346) |

---


### [asHSWindow](#ashswindow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:asHSWindow() -> hs.window object`                                                                    |
| **Type**                                    | Deprecated                                                                     |
| **Description**                             | Returns an hs.window object for the webview so that you can use hs.window methods on it.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/webview/webview.lua line 269](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L269) |

---


### [setLevel](#setlevel)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:setLevel(theLevel) -> drawingObject`                                                                    |
| **Type**                                    | Deprecated                                                                     |
| **Description**                             | Deprecated; you should use [hs.webview:level](#level) instead.                                                                     |
| **Parameters**                              | <ul><li>`theLevel` - the level specified as a number, which can be obtained from `hs.drawing.windowLevels`.</li></ul> |
| **Returns**                                 | <ul><li>the webview object</li></ul>          |
| **Notes**                                   | <ul><li>see the notes for `hs.drawing.windowLevels`</li></ul> |
| **Source**                                  | [extensions/webview/webview.lua line 282](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L282) |

---

#### Constants


### [certificateOIDs](#certificateoids)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview.certificateOIDs[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of common OID values found in SSL certificates.  SSL certificates provided to the callback function for [hs.webview:sslCallback](#sslCallback) or in the results of [hs.webview:certificateChain](#certificateChain) use OID strings as the keys which describe the properties of the certificate and this table can be used to get a more common name for the keys you are most likely to see.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2572](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2572) |

---


### [windowMasks](#windowmasks)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview.windowMasks[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table containing valid masks for the webview window.                                                                     |
| **Notes**                                   | <ul><li>The Maximize button in the window title is enabled when Resizable is set.</li><li>The Close, Minimize, and Maximize buttons are only visible when the Window is also Titled.</li></ul> |
| **Source**                                  | [extensions/webview/libwebview.m line 2530](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2530) |

---

#### Functions


### [titleVisibility](#titlevisibility)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:titleVisibility([state]) -> webviewObject | string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Get or set whether or not the title text appears in the webview window.                                                                     |
| **Parameters**                              | <ul><li>`state` - an optional string containing the text "visible" or "hidden", specifying whether or not the webview's title text appears when webview's window style includes "titled".</li></ul> |
| **Returns**                                 | <ul><li>if a value is provided, returns the webview object; otherwise returns the current value.</li></ul>          |
| **Notes**                                   | <ul><li>See also [hs.webview:windowStyle](#windowStyle) and [hs.webview.windowMasks](#windowMasks).</li><li></li><li>When a toolbar is attached to the webview, this function can be used to specify whether the Toolbar appears underneath the webview window's title ("visible") or in the window's title bar itself, as seen in applications like Safari ("hidden"). When the title is hidden, the toolbar will only display the toolbar items as icons without labels, and ignores changes made with `hs.webview.toolbar:displayMode`.</li><li></li><li>If a toolbar is attached to the webview, you can achieve the same effect as this method with `hs.webview:attachedToolbar():inTitleBar(boolean)`</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2181](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2181) |

---

#### Constructors


### [new](#new)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview.new(rect, [preferencesTable], [userContentController]) -> webviewObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Create a webviewObject and optionally modify its preferences.                                                                     |
| **Parameters**                              | <ul><li>`rect` - a rectangle specifying where the webviewObject should be displayed.</li><li>`preferencesTable` - an optional table which can include one of more of the following keys:
  `javaScriptEnabled`                     - JavaScript is enabled (default true)
  `javaScriptCanOpenWindowsAutomatically` - can JavaScript open windows without user intervention (default true)
  `minimumFontSize`                       - minimum font size (default 0.0)
  `developerExtrasEnabled`                - include "Inspect Element" in the context menu
  `suppressesIncrementalRendering`        - suppresses content rendering until fully loaded into memory (default false)
  The following additional preferences may also be set under OS X 10.11 or later (they will be ignored with a warning printed if used under OS X 10.10):`applicationName`                       - a string specifying an application name to be listed at the end of the browser's USER-AGENT header.  Note that this is only appended to the default user agent string; if you set a custom one with [hs.webview:userAgent](#userAgent), this value is ignored.`allowsAirPlay`                         - a boolean specifying whether media playback within the webview can play through AirPlay devices.`datastore`                             - an `hs.webview.datastore` object specifying where website data such as cookies, cacheable content, etc. is to be stored.`privateBrowsing`                       - a boolean (default false) specifying that the datastore should be set to a new, empty and non-persistent datastore.  Note that this will override the `datastore` key if both are specified and this is set to true.</li><li>`userContentController` - an optional `hs.webview.usercontent` object to provide script injection and JavaScript messaging with Hammerspoon from the webview.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>To set the initial URL, use the `hs.webview:url` method before showing the webview object.</li><li>Preferences can only be set when the webview object is created.  To change the preferences of an open webview, you will need to close it and recreate it with this method.</li><li></li><li>developerExtrasEnabled is not listed in Apple's documentation, but is included in the WebKit2 documentation.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1800](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1800) |

---


### [newBrowser](#newbrowser)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview.newBrowser(rect, [preferencesTable], [userContentController]) -> webviewObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Create a webviewObject with some presets common to an interactive web browser.                                                                     |
| **Parameters**                              | <ul><li>`rect`                  - a rectangle specifying where the webviewObject should be displayed.</li><li>`preferencesTable`      - an optional table which specifies special settings for the webview object.</li><li>`userContentController` - an optional `hs.webview.usercontent` object to provide script injection and JavaScript messaging with Hammerspoon from the webview.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>The parameters are the same as for [hs.webview.new](#new) -- check there for more details</li><li>This constructor is just a short-hand for `hs.webview.new(...):allowTextEntry(true):allowGestures(true):windowStyle(15)`, which specifies a webview with a title bar, title bar buttons (zoom, close, minimize), and allows form entry and gesture support for previous and next pages.</li><li></li><li>* See [hs.webview.new](#new) and the following for more details:</li><li> [hs.webview:allowGestures](#allowGestures)</li><li> [hs.webview:allowTextEntry](#allowTextEntry)</li><li> [hs.webview:windowStyle](#windowStyle)</li><li> [hs.webview.windowMasks](#windowMasks)</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/webview.lua line 80](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L80) |

---

#### Methods


### [allowGestures](#allowgestures)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:allowGestures([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview will respond to gestures from a trackpad or magic mouse.  Default is false.                                                                     |
| **Parameters**                              | <ul><li>value - an optional boolean value indicating whether or not the webview should respond gestures.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>This is a shorthand method for getting or setting both `hs.webview:allowMagnificationGestures` and `hs.webview:allowNavigationGestures`.</li><li>This method will set both types of gestures to true or false, if given an argument, but will only return true if *both* gesture types are currently true; if either or both gesture methods are false, then this method will return false.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/webview.lua line 166](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L166) |

---


### [allowMagnificationGestures](#allowmagnificationgestures)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:allowMagnificationGestures([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview will respond to magnification gestures from a trackpad or magic mouse.  Default is false.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value indicating whether or not the webview should respond to magnification gestures.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1275](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1275) |

---


### [allowNavigationGestures](#allownavigationgestures)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:allowNavigationGestures([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview will respond to the navigation gestures from a trackpad or magic mouse.  Default is false.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value indicating whether or not the webview should respond to navigation gestures.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1365](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1365) |

---


### [allowNewWindows](#allownewwindows)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:allowNewWindows([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview allows new windows to be opened from it by any method.  Defaults to true.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value indicating whether or not the webview should allow new windows to be opened from it.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>This method allows you to prevent a webview from being able to open a new window by any method.   This includes right-clicking on a link and selecting "Open in a New Window", JavaScript pop-ups, links with the target of "__blank", etc.</li><li>If you just want to prevent automatic JavaScript windows, set the preference value javaScriptCanOpenWindowsAutomatically to false when creating the web view - this method blocks *all* methods.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1299](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1299) |

---


### [allowTextEntry](#allowtextentry)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:allowTextEntry([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview can accept keyboard for web form entry. Defaults to false.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value which sets whether or not the webview will accept keyboard input.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1994](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1994) |

---


### [alpha](#alpha)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:alpha([alpha]) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the alpha level of the window containing the hs.webview object.                                                                     |
| **Parameters**                              | <ul><li>`alpha` - an optional number between 0.0 and 1.0 specifying the new alpha level for the webview.</li></ul> |
| **Returns**                                 | <ul><li>If a parameter is provided, returns the webview object; otherwise returns the current value.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2322](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2322) |

---


### [attachedToolbar](#attachedtoolbar)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:attachedToolbar([toolbar]) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or attach/detach a toolbar to/from the webview.                                                                     |
| **Parameters**                              | <ul><li>`toolbar` - if an `hs.webview.toolbar` object is specified, it will be attached to the webview.  If an explicit nil is specified, the current toolbar will be removed from the webview.</li></ul> |
| **Returns**                                 | <ul><li>if a toolbarObject or explicit nil is specified, returns the webviewObject; otherwise returns the current toolbarObject or nil, if no toolbar is attached to the webview.</li></ul>          |
| **Notes**                                   | <ul><li>this method is a convenience wrapper for the `hs.webview.toolbar.attachToolbar` function.</li><li></li><li>If the toolbarObject is currently attached to another window when this method is called, it will be detached from the original window and attached to the webview.  If you wish to attach the same toolbar to multiple webviews, see `hs.webview.toolbar:copy`.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/webview.lua line 107](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L107) |

---


### [behavior](#behavior)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:behavior([behavior]) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the window behavior settings for the webview object.                                                                     |
| **Parameters**                              | <ul><li>`behavior` - an optional number representing the desired window behaviors for the webview object.</li></ul> |
| **Returns**                                 | <ul><li>If an argument is provided, the webview object; otherwise the current value.</li></ul>          |
| **Notes**                                   | <ul><li>Window behaviors determine how the webview object is handled by Spaces and Exposé. See `hs.drawing.windowBehaviors` for more information.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2447](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2447) |

---


### [behaviorAsLabels](#behavioraslabels)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:behaviorAsLabels(behaviorTable) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the window behavior settings for the webview object using labels defined in `hs.drawing.windowBehaviors`.                                                                     |
| **Parameters**                              | <ul><li>behaviorTable - an optional table of strings and/or numbers specifying the desired window behavior for the webview object.</li></ul> |
| **Returns**                                 | <ul><li>If an argument is provided, the webview object; otherwise the current value.</li></ul>          |
| **Notes**                                   | <ul><li>Window behaviors determine how the webview object is handled by Spaces and Exposé. See `hs.drawing.windowBehaviors` for more information.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/webview.lua line 299](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L299) |

---


### [bringToFront](#bringtofront)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:bringToFront([aboveEverything]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Places the drawing object on top of normal windows                                                                     |
| **Parameters**                              | <ul><li>`aboveEverything` - An optional boolean value that controls how far to the front the webview should be placed. True to place the webview on top of all windows (including the dock and menubar and fullscreen windows), false to place the webview above normal windows, but below the dock, menubar and fullscreen windows. Defaults to false.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2286](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2286) |

---


### [certificateChain](#certificatechain)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:certificateChain() -> table | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the certificate chain for the most recently committed navigation of the webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a table containing the certificates that make up the SSL certificate chain securing the most recent committed navigation.  Each certificate is described in a table with the following keys:</li><li>  `commonName` - the common name for the certificate; most commonly this will be a string matching the server portion of the URL request or other descriptor of the certificate's purpose.</li><li>  `values`     - a table containing key-value pairs describing the certificate.  The keys will be certificate OIDs.  Common OIDs and their meaning can be found in [hs.webview.certificateOIDs](#certificateOIDs). The value for each key will be a table with the following keys:</li><li>    `label`           - a description or label for the entry</li><li>    `localized label` - a localized version of `label`</li><li>    `type`            - a description of the data type for this value</li><li>    `value`           - the value</li></ul>          |
| **Notes**                                   | <ul><li>This method is only supported by OS X 10.11 and newer</li><li>A navigation which was performed via HTTP instead of HTTPS will return an empty array.</li><li></li><li>For OIDs which specify a type of "date" -- e.g. "2.5.29.24" (invalidityDate) -- the number provided represents the number of seconds since 12:00:00 AM, January 1, 1970 and can be used directly with the Lua `os.date` command.</li><li>For OIDs which are known to represent a date, but specify its type as a "number" -- e.g. "2.16.840.1.113741.2.1.1.1.7" (X509V1ValidityNotAfter) or "2.16.840.1.113741.2.1.1.1.6" (X509V1ValidityNotBefore) -- the epoch is 12:00:00 AM, Jan 1, 2001.  To convert these dates into a format usable by Lua, you will need to do something similar to the following:  `os.date("%c", value + os.time({year=2001,month=1,day=1,hour=0,min=0,sec=0})`</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1008](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1008) |

---


### [children](#children)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:children() -> array`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns an array of webview objects which have been opened as children of this webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>an array containing the webview objects of all child windows opened from this webview.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 856](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L856) |

---


### [closeOnEscape](#closeonescape)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:closeOnEscape([flag]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | If the webview is closable, this will get or set whether or not the Escape key is allowed to close the webview window.                                                                     |
| **Parameters**                              | <ul><li>`flag` - an optional boolean value which indicates whether a webview, when it's style includes Closable (see `hs.webview:windowStyle`), should allow the Escape key to be a shortcut for closing the webview window.  Defaults to false.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>If this is set to true, Escape will only close the window if no other element responds to the Escape key first (e.g. if you are editing a text input field, the Escape will be captured by the text field, not by the webview Window.)</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2073](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2073) |

---


### [darkMode](#darkmode)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:darkMode([state]) -> bool`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Set or display whether or not the `hs.webview` window should display in dark mode.                                                                     |
| **Parameters**                              | <ul><li>`state` - an optional boolean which will set whether or not the `hs.webview` window should display in dark mode.</li></ul> |
| **Returns**                                 | <ul><li>A boolean, `true` if dark mode is enabled otherwise `false`.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2042](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2042) |

---


### [delete](#delete)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:delete([propagate], [fadeOutTime]) -> none`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Destroys the webview object, optionally fading it out first (if currently visible).                                                                     |
| **Parameters**                              | <ul><li>`propagate`   - an optional boolean, default false, which indicates whether or not the child windows of this webview should also be deleted.</li><li>`fadeOutTime` - an optional number of seconds over which to fade out the webview object. Defaults to zero.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul><li>This method is automatically called during garbage collection, notably during a Hammerspoon termination or reload, with a fade time of 0.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/webview.lua line 189](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L189) |

---


### [deleteOnClose](#deleteonclose)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:deleteOnClose([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview should delete itself when its window is closed.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value which sets whether or not the webview will delete itself when its window is closed by any method.  Defaults to false for a window created with `hs.webview.new` and true for any webview windows created by the main webview (user selects "Open Link in New Window", etc.)</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>If set to true, a webview object will be deleted when the user clicks on the close button of a titled and closable webview (see `hs.webview.windowStyle`).</li><li>Children of an explicitly created webview automatically have this attribute set to true.  To cause closed children to remain after the user closes the parent, you can set this to false with a policy callback function when it receives the "newWindow" action.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2016](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2016) |

---


### [estimatedProgress](#estimatedprogress)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:estimatedProgress() -> number`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the estimated percentage of expected content that has been loaded.  Will equal 1.0 when all content has been loaded.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a numerical value between 0.0 and 1.0 indicating the percentage of expected content which has been loaded.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1137](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1137) |

---


### [evaluateJavaScript](#evaluatejavascript)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:evaluateJavaScript(script, [callback]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Execute JavaScript within the context of the current webview and optionally receive its result or error in a callback function.                                                                     |
| **Parameters**                              | <ul><li>`script` - the JavaScript to execute within the context of the current webview's display</li><li>`callback` - an optional function which should accept two parameters as the result of the executed JavaScript.  The function parameters are as follows:
  `result` - the result of the executed JavaScript code or nil if there was no result or an error occurred.
  `error`  - an NSError table describing any error that occurred during the JavaScript execution or nil if no error occurred.</li></ul> |
| **Returns**                                 | <ul><li>the webview object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1678](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1678) |

---


### [examineInvalidCertificates](#examineinvalidcertificates)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:examineInvalidCertificates([flag]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not invalid SSL server certificates that are approved by the ssl callback function are accepted as valid for browsing with the webview.                                                                     |
| **Parameters**                              | <ul><li>`flag` - an optional boolean, default false, specifying whether or not an invalid SSL server certificate should be  accepted if it is approved by the ssl callback function.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>In order for this setting to have any effect, you must also register an ssl callback function with [hs.webview:sslCallback](#sslCallback) which should return true if the certificate should be granted an exception or false if it should not.  For a certificate to be granted an exception, both this method and the result of the callback *must* be true.</li><li></li><li>A server certificate may be invalid for a variety of reasons:</li><li>  it is not signed by a recognized certificate authority - most commonly this means the certificate is self-signed.</li><li>  the certificate has expired</li><li>  the certificate has a common name (web site server name) other than the one requested (e.g. the certificate's common name is www.site.com, but it is being used for something else, possibly just https://site.com, possibly something else entirely</li><li>  some corporate proxy servers don't handle SSL properly and can cause a certificate to appear invalid even when they are valid (this is less common then it used to be, but does still occur occasionally)</li><li>  potentially nefarious reasons including man-in-the-middle attacks or phishing scams.</li><li></li><li>The Hammerspoon server provided by `hs.httpserver` uses a self-signed certificate when set to use SSL, so it will be considered invalid for reason 1 above.</li><li></li><li>* If the certificate has been granted an exception in another application which registers the exception in the user's keychain (e.g. Safari), then the certificate is no longer considered invalid and this setting has no effect for that certificate.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1327](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1327) |

---


### [frame](#frame)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:frame([rect]) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the frame of the webview window.                                                                     |
| **Parameters**                              | <ul><li>rect - An optional rect-table containing the co-ordinates and size the webview window should be moved and set to</li></ul> |
| **Returns**                                 | <ul><li>If an argument is provided, the webview object; otherwise the current value.</li></ul>          |
| **Notes**                                   | <ul><li>a rect-table is a table with key-value pairs specifying the new top-left coordinate on the screen of the webview window (keys `x`  and `y`) and the new size (keys `h` and `w`).  The table may be crafted by any method which includes these keys, including the use of an `hs.geometry` object.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/webview.lua line 216](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L216) |

---


### [goBack](#goback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:goBack() -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Move to the previous page in the webview's history, if possible.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The webview Object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1197](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1197) |

---


### [goForward](#goforward)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:goForward() -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Move to the next page in the webview's history, if possible.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The webview Object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1177](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1177) |

---


### [hide](#hide)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:hide([fadeOutTime]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Hides the webview object                                                                     |
| **Parameters**                              | <ul><li>`fadeOutTime` - An optional number of seconds over which to fade out the webview. Defaults to zero</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1968](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1968) |

---


### [historyList](#historylist)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:historyList() -> historyTable`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the URL history for the current webview as an array.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table which is an array of the URLs viewed within this webview and a key named `current` which is equal to the index corresponding to the currently visible entry.  Each array element will be a table with the following keys:</li><li>  `URL`        - the URL of the web page</li><li>  `initialURL` - the URL of the initial request that led to this item</li><li>  `title`      - the web page title</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1655](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1655) |

---


### [hswindow](#hswindow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:hswindow() -> hs.window object`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns an hs.window object for the webview so that you can use hs.window methods on it.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>an hs.window object</li></ul>          |
| **Notes**                                   | <ul><li>hs.window:minimize only works if the webview is minimizable (see `hs.webview.windowStyle`)</li><li>hs.window:setSize only works if the webview is resizable (see `hs.webview.windowStyle`)</li><li>hs.window:close only works if the webview is closable (see `hs.webview.windowStyle`)</li><li>hs.window:maximize will reposition the webview to the upper left corner of your screen, but will only resize the webview if the webview is resizable (see `hs.webview.windowStyle`)</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2100](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2100) |

---


### [html](#html)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:html(html,[baseURL]) -> webviewObject, navigationIdentifier`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Render the given HTML in the webview with an optional base URL for relative links.                                                                     |
| **Parameters**                              | <ul><li>`html`    - the html to be rendered in the webview</li><li>`baseURL` - an optional Base URL to use as the starting point for any relative links within the provided html.</li></ul> |
| **Returns**                                 | <ul><li>The webview Object</li></ul>          |
| **Notes**                                   | <ul><li>Web Pages generated in this manner are not added to the webview history list</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1423](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1423) |

---


### [isOnlySecureContent](#isonlysecurecontent)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:isOnlySecureContent() -> bool`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a boolean value indicating if all content current displayed in the webview was loaded over securely encrypted connections.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>true if all content current displayed in the web view was loaded over securely encrypted connections; otherwise false.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1157](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1157) |

---


### [isVisible](#isvisible)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:isVisible() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Checks to see if a webview window is visible or not.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>`true` if the webview window is visible, otherwise `false`</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2128](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2128) |

---


### [level](#level)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:level([theLevel]) -> drawingObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the window level                                                                     |
| **Parameters**                              | <ul><li>`theLevel` - an optional parameter specifying the desired level as an integer, which can be obtained from `hs.drawing.windowLevels`.</li></ul> |
| **Returns**                                 | <ul><li>if a parameter is specified, returns the webview object, otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>see the notes for `hs.drawing.windowLevels`</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2252](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2252) |

---


### [loading](#loading)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:loading() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a boolean value indicating whether or not the webview is still loading content.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>true if the content is still being loaded, or false if it has completed.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1091](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1091) |

---


### [magnification](#magnification)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:magnification([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the webviews current magnification level. Default is 1.0.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional number specifying the webviews magnification level.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1389](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1389) |

---


### [navigationCallback](#navigationcallback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:navigationCallback(fn) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets a callback for tracking a webview's navigation process.                                                                     |
| **Parameters**                              | <ul><li>`fn` - the function to be called when the navigation status of a webview changes.  To disable the callback function, explicitly specify nil.  The function should expect 3 or 4 arguments and may optionally return 1.  The function arguments are defined as follows:
  `action`  - a string indicating the webview's current status.  It will be one of the following:`didStartProvisionalNavigation`                    - a request or action to change the contents of the main frame has occurred`didReceiveServerRedirectForProvisionalNavigation` - a server redirect was received for the main frame`didCommitNavigation`                              - content has started arriving for the main frame`didFinishNavigation`                              - the webview's main frame has completed loading.`didFailNavigation`                                - an error has occurred after content started arriving`didFailProvisionalNavigation`                     - an error has occurred as or before content has started arriving
  `webView` - the webview object the navigation is occurring for.
  `navID`   - a navigation identifier which can be used to link this event back to a specific request made by a `hs.webview:url`, `hs.webview:html`, or `hs.webview:reload` method.
  `error`   - a table which will only be provided when `action` is equal to `didFailNavigation` or `didFailProvisionalNavigation`.  If provided, it will contain at leas some of the following keys, possibly others as well:`code`        - a numerical value indicating the type of error code.  This will mostly be of use to developers or in debugging and may be removed in the future.`domain`      - a string indicating the error domain of the error.  This will mostly be of use to developers or in debugging and may be removed in the future.`description` - a string describing the condition or problem that has occurred.`reason`      - if available, more information about what may have caused the problem to occur.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>The return value of the callback function is ignored except when the `action` argument is equal to `didFailNavigation` or `didFailProvisionalNavigation`.  If the return value when the action argument is one of these values is a string, it will be treated as html and displayed in the webview as the error message.  If the return value is the boolean value true, then no change will be made to the webview (it will continue to display the previous web page).  All other return values or no return value at all, if these navigation actions occur, will cause a default error page to be displayed in the webview.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1458](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1458) |

---


### [navigationID](#navigationid)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:navigationID() -> navigationID`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get the most recent navigation identifier for the specified webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the navigation identifier</li></ul>          |
| **Notes**                                   | <ul><li>This navigation identifier can be used to track the progress of a webview with the navigation callback function - see `hs.webview.navigationCallback`.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1069](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1069) |

---


### [orderAbove](#orderabove)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:orderAbove([webview2]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Moves webview object above webview2, or all webview objects in the same presentation level, if webview2 is not given.                                                                     |
| **Parameters**                              | <ul><li>`webview2` -An optional webview object to place the webview object above.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>If the webview object and webview2 are not at the same presentation level, this method will move the webview object as close to the desired relationship without changing the webview object's presentation level. See [hs.webview.level](#level).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2390](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2390) |

---


### [orderBelow](#orderbelow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:orderBelow([webview2]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Moves webview object below webview2, or all webview objects in the same presentation level, if webview2 is not given.                                                                     |
| **Parameters**                              | <ul><li>`webview2` -An optional webview object to place the webview object below.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>If the webview object and webview2 are not at the same presentation level, this method will move the webview object as close to the desired relationship without changing the webview object's presentation level. See [hs.webview.level](#level).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2406](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2406) |

---


### [parent](#parent)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:parent() -> webviewObject | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get the parent webview object for the calling webview object, or nil if the webview has no parent.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the parent webview object for the calling webview object, or nil if the webview has no parent</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 879](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L879) |

---


### [policyCallback](#policycallback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:policyCallback(fn) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets a callback to approve or deny web navigation activity.                                                                     |
| **Parameters**                              | <ul><li>`fn` - the function to be called to approve or deny web navigation activity.  To disable the callback function, explicitly specify nil.  The callback function will accept three or four arguments and must return 1 argument which will determine if the action is approved or denied.  The first argument will specify the type of policy request and will determine the second and third arguments as follows:
  `navigationAction`: This applies to any connection to a server or service which supplies content for the webview and occurs before any connection has actually been made.the second argument will be the webview this request originates from.the third argument will be a table about the navigation action requested and may contain any of the following keys:`request`        - a table containing the request for that generated this policy action request.  See `hs.webview.url` for details on what keys may be present in this table.`sourceFrame`    - a table describing the frame in which the request occurred containing the following keys:`mainFrame`      - a boolean value indicating if this is the main view frame of the webview or not`request`        - a table containing the request for this frame.  See `hs.webview.url` for details on what keys may be present in this table.`targetFrame`    - a table with the same keys as `sourceFrame`, but describing the target of the request, if it differs.`buttonNumber`   - a number indicating the mouse button pressed that initiated this action or 0 if no mouse button was involved (for example, a url specified via `hs.webview.url` or a request for an image, etc. as part of rendering an earlier request).`modifierFlags`  - a table containing keys for the keyboard modifiers which were pressed when the navigation generating this policy request was generated.`navigationType` - a string indicating how the navigation was requested: `linkActivated`, `formSubmitted`, `backForward`, `reload`, `formResubmitted`, or `other`
  The callback function should return `true` if the navigation should proceed or false if it should be denied.
  `navigationResponse`: This applies to any connection to a server or service which supplies content for the webview and occurs after the connection has been made but before it has been rendered in the webview.the second argument will be the webview this request originates from.the third argument will be a table about the response received and may contain any of the following keys:`canShowMIMEType` - a boolean indicating whether or not the webview can display the content either natively or with a plugin.  If this value is false, it is likely the content either cannot be displayed at all or will appear as gibberish in the webview.`forMainFrame`    - a boolean indicating if the response is for a navigation of the main frames primary content (i.e. not an image or sub-frame, etc.)`response`        - a table describing the response to the URL request and may contain any of the following keys:`expectedContentLength` - the expected length of the response content`suggestedFileName`     - a suggested filename for the response data`MIMEType`              - the MIME type of the response data`textEncodingName`      - if the response is text, then this will contain the encoding type used`URL`                   - the URL of the actual response.  Note that this may differ from the original request due to redirects, etc.`statusCode`            - the HTTP response code for the request`statusCodeDescription` - a localized description of the response code`allHeaderFields`       - a table containing the header fields and values provided in the response
  The callback function should return `true` if the navigation should proceed or false if it should be denied.
  `newWindow`: This applies to any request to create a new window from a webview.  This includes JavaScript, the user selecting "Open in a new window", etc.the second argument will be the new webview this request is generating.the third argument will be a table about the navigation action requested.  See the description above for `navigationAction` for details about this parameter.the fourth argument will be a table containing features requested for the new window (none of these will be addressed by default -- you can choose to honor or disregard the feature requests in the callback yourself) and may contain any of the following keys:`menuBarVisibility`   - Whether the menu bar should be visible. (Not a feature provided for windows under OS X)`statusBarVisibility` - Whether the status bar should be visible. (Not currently supported by this module)`toolbarsVisibility`  - Whether toolbars should be visible.`allowsResizing`      - Whether the new window should be resizable.`x`                   - The x coordinate of the new window.`y`                   - The y coordinate of the new window.`h`                   - The height coordinate of the new window.`w`                   - The width coordinate of the new window.
  The callback function should return `true` if the new window should be created or false if it should not.
  `authenticationChallenge`:  This applies to a web page which requires a log in credential for HTTPBasic or HTTPDigest authentication.the second argument will be the webview this request originates from.the third argument will be a table containing the challenge details and may contain any of the following keys:`previousFailureCount` - an integer indicating the number of previously failed login attempts.  This will be 0 for the first try.`failureResponse`      - the response data as described for `navigationResponse` above for the last authentication failureResponse`proposedCredential`   - a table containing the previously failed credential containing any of the following keys:`hasPassword`          - a boolean value indicating if a password was provided with this credential`persistence`          - a string value identifying the persistence of this credential.  This value will be one of the following:None                 - the credential is for this URL request only and no other`session`              - the credential is for this session and will be forgotten once the webview is deleted`permanent`            - the credential is stored in the user's keychain`synchronized`         - the credential is stored in the user's keychain and may be shared with other devices with the same owning Apple ID.`user`                 - the username of the failed credential`password`             - the password of the failed credential`protectionSpace`      - a table describing the realm for the authentication and may contain any of the following keys:`port`                       - the port of the server with which communication for this request is occurring`receivesCredentialSecurely` - a boolean value indicating whether or not the credential can be sent to the server securely`authenticationMethod`       - a string indicating the authentication type: default, HTTPBasic, or HTTPDigest.  Other types exists but are not currently supported with this module or do not apply to webview activities.`host`                       - the host name of the server with which communication for this request is occurring`protocol`                   - the protocol for which the authentication is occurring`isProxy`                    - a boolean indicating whether or not the authentication is occurring with a proxy server`proxyType`                  - a string representing the type of proxy server: http, https, ftp, or socks.`realm`                      - a string representing the realm name for the authentication.
  The callback function should return true if the user should be prompted for the username and password credentials, a table with the keys `user` and `password` containing the username and password to log in with, or false if the login request should be cancelled.  Note that if your function returns a table and fails to authenticate three times, the user will be prompted anyways to prevent loops.</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>With the `newWindow` action, the navigationCallback and policyCallback are automatically replicated for the new window from its parent.  If you wish to disable these for the new window or assign a different set of callback functions, you can do so before returning true in the callback function with the webview argument provided.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1505](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1505) |

---


### [privateBrowsing](#privatebrowsing)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:privateBrowsing() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns whether or not the webview browser is set up for private browsing (i.e. uses a non-persistent datastore)                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a boolean value indicating whether or not the datastore is non-persistent.</li></ul>          |
| **Notes**                                   | <ul><li>This method is only supported by OS X 10.11 and newer</li><li></li><li>See `hs.webview.datastore` and [hs.webview.new](#new) for more information.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 821](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L821) |

---


### [reload](#reload)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:reload([validate]) -> webviewObject, navigationIdentifier`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Reload the page in the webview, optionally performing end-to-end revalidation using cache-validating conditionals if possible.                                                                     |
| **Parameters**                              | <ul><li>`validate` - an optional boolean indicating whether or not an attempt to perform end-to-end revalidation of cached data should be performed.  Defaults to false.</li></ul> |
| **Returns**                                 | <ul><li>The webview Object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1217](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1217) |

---


### [sendToBack](#sendtoback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:sendToBack() -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Places the webview object behind normal windows, between the desktop wallpaper and desktop icons                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The drawing object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2304](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2304) |

---


### [shadow](#shadow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:shadow([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview window has shadows. Default to false.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value indicating whether or not the webview should have shadows.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2346](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2346) |

---


### [show](#show)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:show([fadeInTime]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Displays the webview object                                                                     |
| **Parameters**                              | <ul><li>`fadeInTime` - An optional number of seconds over which to fade in the webview. Defaults to zero</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1942](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1942) |

---


### [size](#size)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:size([size]) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the size of a webview window                                                                     |
| **Parameters**                              | <ul><li>`size` - An optional size-table specifying the width and height the webview window should be resized to</li></ul> |
| **Returns**                                 | <ul><li>If an argument is provided, the webview object; otherwise the current value.</li></ul>          |
| **Notes**                                   | <ul><li>a size-table is a table with key-value pairs specifying the size (keys `h` and `w`) the webview should be resized to. The table may be crafted by any method which includes these keys, including the use of an `hs.geometry` object.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1767](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1767) |

---


### [sslCallback](#sslcallback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:sslCallback(fn) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets a callback to examine an invalid SSL certificate and determine if an exception should be granted.                                                                     |
| **Parameters**                              | <ul><li>`fn` - the function to be called to examine the SSL certificate to determine if an exception should be granted.  To disable the callback function, explicitly specify nil.  The callback function will accept two arguments and must return 1 argument which will determine if the action is approved or denied.  The first argument will be the webview this request originates from.  The second argument will be a table containing the protection space details and may include the following keys:
  `port`                       - the port of the server with which communication for this request is occurring
  `receivesCredentialSecurely` - a boolean value indicating whether or not the credential can be sent to the server securely
  `authenticationMethod`       - a string indicating the authentication type, in this case "serverTrust".
  `host`                       - the host name of the server with which communication for this request is occurring
  `protocol`                   - the protocol for which the authentication is occurring
  `isProxy`                    - a boolean indicating whether or not the authentication is occurring with a proxy server
  `proxyType`                  - a string representing the type of proxy server: http, https, ftp, or socks.
  `realm`                      - a string representing the realm name for the authentication.
  `certificates` - an array of tables, each table describing a certificate in the SSL certificate chain provided by the server responding to the webview's request.  Each table will contain the following keys:`commonName` - the common name for the certificate; most commonly this will be a string matching the server portion of the URL request or other descriptor of the certificate's purpose.`values`     - a table containing key-value pairs describing the certificate.  The keys will be certificate OIDs.  Common OIDs and their meaning can be found in [hs.webview.certificateOIDs](#certificateOIDs). The value for each key will be a table with the following keys:`label`           - a description or label for the entry`localized label` - a localized version of `label``type`            - a description of the data type for this value`value`           - the value</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>The callback function should return true if an exception should be granted for this certificate or false if it should be rejected.</li><li>even if this callback returns `true`, the certificate will only be granted an exception if [hs.webview:examineInvalidCertificates](#examineInvalidCertificates) has also been set to `true`.</li><li>once an invalid certificate has been granted an exception, the exception will remain in effect until the webview object is deleted.</li><li>the callback is only invoked for invalid certificates -- if a certificate is valid, or once an exception has been granted, the callback will not (no longer) be called for that certificate.</li><li></li><li>* If the certificate has been granted an exception in another application which registers the exception in the user's keychain (e.g. Safari), then the certificate is no longer considered invalid and this callback will not be invoked.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1602](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1602) |

---


### [stopLoading](#stoploading)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:stopLoading() -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Stop loading additional content for the webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | <ul><li>this method does not stop the loading of the primary content for the page at the specified URL</li><li>if [hs.webview:loading](#loading) would return true, this method does nothing -- see notes:</li><li>  The documentation from Apple is unclear and experimentation has shown that if this method is applied before the content of the specified URL has loaded, it can cause the webview to lock up; however it appears to stop the loading of additional resources specified for the content (external script files, external style files, AJAX queries, etc.) and should be used in this context.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1111](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1111) |

---


### [title](#title)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:title() -> title`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get the title of the page displayed in the webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the title</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1050](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1050) |

---


### [topLeft](#topleft)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:topLeft([point]) -> webviewObject | currentValue`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the top-left coordinate of the webview window                                                                     |
| **Parameters**                              | <ul><li>`point` - An optional point-table specifying the new coordinate the top-left of the webview window should be moved to</li></ul> |
| **Returns**                                 | <ul><li>If an argument is provided, the webview object; otherwise the current value.</li></ul>          |
| **Notes**                                   | <ul><li>a point-table is a table with key-value pairs specifying the new top-left coordinate on the screen of the webview (keys `x`  and `y`). The table may be crafted by any method which includes these keys, including the use of an `hs.geometry` object.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1735](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1735) |

---


### [transparent](#transparent)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:transparent([value]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set whether or not the webview background is transparent.  Default is false.                                                                     |
| **Parameters**                              | <ul><li>`value` - an optional boolean value indicating whether or not the webview should be transparent.</li></ul> |
| **Returns**                                 | <ul><li>If a value is provided, then this method returns the webview object; otherwise the current value</li></ul>          |
| **Notes**                                   | <ul><li>When enabled, the webview's background color is equal to the body's `background-color` (transparent by default)</li><li>Setting `background-color:rgba(0, 225, 0, 0.3)` on `<body>` will give a translucent green webview background</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 1247](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L1247) |

---


### [url](#url)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:url([URL]) -> webviewObject, navigationIdentifier | url`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the URL to render for the webview.                                                                     |
| **Parameters**                              | <ul><li>`URL` - an optional string or table representing the URL to display.  If you provide a table, it should contain one or more of the following keys (note that URL is the only required key):
  `URL`                     - the URL of the desired content
  `mainDocumentURL`         - the URL of the main document, if it differs.  This usually only matters for cookie negotiation and currently has no effect in this module.
  `HTTPBody`                - the message body of the request, as in an HTTP POST request
  `HTTPMethod`              - the HTTP Method of the request, default GET.
  `timeoutInterval`         - the timeout interval for the request in seconds, default 60.0.
  `HTTPShouldHandleCookies` - whether or not cookies should be managed automatically, default true.  Currently there is no support for the manual handling of cookies, though this may change in the future.
  `HTTPShouldUsePipelining` - whether or not the request can continue to transmit data before receiving a response from the remote server.  Default false.
  `cachePolicy`             - a string value representing the cache policy for the request.  It should match one of the following:`protocolCachePolicy`     - (default) the cache policy defined as the default for the protocol of the URL request`ignoreLocalCache`        - ignore any locally cached content and request all content from the remote server`returnCacheOrLoad`       - return cached data, regardless of its age or expiration date. If there is no existing data in the cache corresponding to the request, load data from the originating source.`returnCacheDontLoad`     - treat the request as if offline - return cached data, regardless of its age or expiration date. If there is no existing data in the cache corresponding to the request, the load is considered to have failed.
  `networkServiceType`      - a string value representing the network service type of the request.  It should match one of the following:`default`                 - (default) standard network traffic.  You should rarely use a value other than this as it can affect the responsiveness of your computer and other applications.`VoIP`                    - with the VoIP service type, the kernel continues to listen for incoming traffic while your app is in the background, then wakes up your app whenever new data arrives. This should be used only for connections that are used to communicate with a VoIP service.`video`                   - specifies that this is video traffic`background`              - use this for data if your are performing a download that was not requested by the user — for example, prefetching content so that it will be available when the user chooses to view it.`voice`                   - specifies that this is voice traffic
  `HTTPHeaderFields`        - a table containing key-value pairs corresponding to additional headers you wish to include in your request.  Because the HTTP specification requires that both keys and values are strings, any key which is not a string is ignored, and any value which is not a string or number is also ignored.  In addition, the following keys are handled automatically behind the scenes and will be ignored if you specify them:`Authorization``Connection``Host``WWW-Authenticate``Content-Length`</li></ul> |
| **Returns**                                 | <ul><li>If a URL is specified, then this method returns the webview Object; otherwise it returns the current url being displayed.</li></ul>          |
| **Notes**                                   | <ul><li>The networkServiceType field of the URL request table is a hint to the operating system about what the underlying traffic is used for. This hint enhances the system's ability to prioritize traffic, determine how quickly it needs to wake up the Wi-Fi radio, and so on. By providing accurate information, you improve the ability of the system to optimally balance battery life, performance, and other considerations.  Likewise, inaccurate information can have a deleterious effect on your system performance and battery life.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 902](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L902) |

---


### [urlParts](#urlparts)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:urlParts() -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a table of keys containing the individual components of the URL for the webview.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a table containing the keys for the webview's URL.  See the function `hs.http.urlParts` for a description of the possible keys returned in the table.</li></ul>          |
| **Notes**                                   | <ul><li>This method is a wrapper to the `hs.http.urlParts` function wich uses the OS X APIs, based on RFC 1808.</li><li>You may also want to consider the `hs.httpserver.hsminweb.urlParts` function for a version more consistent with RFC 3986.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/webview.lua line 252](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L252) |

---


### [userAgent](#useragent)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:userAgent([agent]) -> webviewObject | current value`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the webview's user agent string                                                                     |
| **Parameters**                              | <ul><li>`agent` - an options string specifying the user agent string to include in all URL requests made by the webview object.</li></ul> |
| **Returns**                                 | <ul><li>if a parameter is specified, returns the webviewObject, otherwise returns the current value</li></ul>          |
| **Notes**                                   | <ul><li>This method is only supported by OS X 10.11 and newer</li><li></li><li>The default user string used by webview objects will be something like this (the exact version numbers will differ, depending upon your OS X version):</li><li> "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_5) AppleWebKit/601.6.17 (KHTML, like Gecko)"</li><li>By default, this method will return the empty string ("") when queried -- this indicates that the default, shown above, is used.  You can also return to this default by setting the user agent to "" with this method (e.g. `hs.webview:userAgent("")`).</li><li></li><li>Some web sites tailor content based on the user string or use it for other internal purposes (tracking, statistics, page availability, layout, etc.).  Common user-agent strings can be found at http://www.useragentstring.com/pages/useragentstring.php.</li><li></li><li>If you have set the user agent application name with the `applicationName` parameter to the [hs.webview.new](#new) constructor, it will be ignored unless this value is "", i.e. the default user agent string.  If you wish to specify an application name after the user agent string and use a custom string, include the application name in your custom string.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 964](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L964) |

---


### [windowCallback](#windowcallback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:windowCallback(fn) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Set or clear a callback for updates to the webview window                                                                     |
| **Parameters**                              | <ul><li>`fn` - the function to be called when the webview window is moved or closed. Specify an explicit nil to clear the current callback.  The function should expect 2 or 3 arguments and return none.  The arguments will be one of the following:
  "closing", webview - specifies that the webview window is being closed, either by the user or with the [hs.webview:delete](#delete) method.`action`  - in this case "closing", specifying that the webview window is being closed`webview` - the webview that is being closed
  "focusChange", webview, state - indicates that the webview window has either become or stopped being the focused window`action`  - in this case "focusChange", specifying that the webview window is being closed`webview` - the webview that is being closed`state`   - a boolean, true if the webview has become the focused window, or false if it has lost focus
  "frameChange", webview, frame - indicates that the webview window has been moved or resized`action`  - in this case "focusChange", specifying that the webview window is being closed`webview` - the webview that is being closed`frame`   - a rect-table containing the new co-ordinates and size of the webview window</li></ul> |
| **Returns**                                 | <ul><li>The webview object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2488](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2488) |

---


### [windowStyle](#windowstyle)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:windowStyle(mask) -> webviewObject | currentMask`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Get or set the window display style                                                                     |
| **Parameters**                              | <ul><li>mask - if present, this mask should be a combination of values found in `hs.webview.windowMasks` describing the window style.  The mask should be provided as one of the following:
  integer - a number representing the style which can be created by combining values found in `hs.webview.windowMasks` with the logical or operator.
  string  - a single key from `hs.webview.windowMasks` which will be toggled in the current window style.
  table   - a list of keys from `hs.webview.windowMasks` which will be combined to make the final style by combining their values with the logical or operator.</li></ul> |
| **Returns**                                 | <ul><li>if a mask is provided, then the webviewObject is returned; otherwise the current mask value is returned.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/webview.lua line 123](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/webview.lua#L123) |

---


### [windowTitle](#windowtitle)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.webview:windowTitle([title]) -> webviewObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the title for the webview window.                                                                     |
| **Parameters**                              | <ul><li>`title` - if specified and not nil, the title to set for the webview window.  If this parameter is not present or is nil, the title will follow the title of the webview's content.</li></ul> |
| **Returns**                                 | <ul><li>The webview Object</li></ul>          |
| **Notes**                                   | <ul><li>The title will be hidden unless the window style includes the "titled" style (see `hs.webview.windowStyle` and `hs.webview.windowMasks`)</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/webview/libwebview.m line 2149](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/webview/libwebview.m#L2149) |

---

