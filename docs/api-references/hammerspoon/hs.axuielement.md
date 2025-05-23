# hs.axuielement

This module allows you to access the accessibility objects of running applications, their windows, menus, and other user interface elements that support the OS X accessibility API.

This module works through the use of axuielementObjects, which is the Hammerspoon representation for an accessibility object.  An accessibility object represents any object or component of an OS X application which can be manipulated through the OS X Accessibility API -- it can be an application, a window, a button, selected text, etc.  As such, it can only support those features and objects within an application that the application developers make available through the Accessibility API.

In addition to the formal methods described in this documentation, dynamic methods exist for accessing element attributes and actions. These will differ somewhat between objects as the specific attributes and actions will depend upon the accessibility object's role and purpose, but the following outlines the basics.

Getting and Setting Attribute values:
 * `object.attribute` is a shortcut for `object:attributeValue(attribute)`
 * `object.attribute = value` is a shortcut for `object:setAttributeValue(attribute, value)`
   * If detecting accessibility errors that may occur is necessary, you must use the formal methods [hs.axuielement:attributeValue](#attributeValue) and [hs.axuielement:setAttributeValue](#setAttributeValue)
   * Note that setting an attribute value is not guaranteed to work with either method:
     * internal logic within the receiving application may decline to accept the newly assigned value
     * an accessibility error may occur
     * the element may not be settable (surprisingly this does not return an error, even when [hs.axuielement:isAttributeSettable](#isAttributeSettable) returns false for the attribute specified)
   * If you require confirmation of the change, you will need to check the value of the attribute with one of the methods described above after setting it.

Iteration over Attributes:
 * `for k,v in pairs(object) do ... end` is a shortcut for `for k,_ in ipairs(object:attributeNames()) do local v = object:attributeValue(k) ; ... end` or `for k,v in pairs(object:allAttributeValues()) do ... end` (though see note below)
    * If detecting accessibility errors that may occur is necessary, you must use one of the formal approaches [hs.axuielement:allAttributeValues](#allAttributeValues) or [hs.axuielement:attributeNames](#attributeNames) and [hs.axuielement:attributeValue](#attributeValue)
   * By default, [hs.axuielement:allAttributeValues](#allAttributeValues) will not include key-value pairs for which the attribute (key) exists for the element but has no assigned value (nil) at the present time. This is because the value of `nil` prevents the key from being retained in the table returned. See [hs.axuielement:allAttributeValues](#allAttributeValues) for details and a workaround.

Iteration over Child Elements (AXChildren):
 * `for i,v in ipairs(object) do ... end` is a shortcut for `for i,v in pairs(object:attributeValue("AXChildren") or {}) do ... end`
   * Note that `object:attributeValue("AXChildren")` *may* return nil if the object does not have the `AXChildren` attribute; the shortcut does not have this limitation.
 * `#object` is a shortcut for `#object:attributeValue("AXChildren")`
 * `object[i]` is a shortcut for `object:attributeValue("AXChildren")[i]`
   * If detecting accessibility errors that may occur is necessary, you must use the formal method [hs.axuielement:attributeValue](#attributeValue) to get the "AXChildren" attribute.

Actions ([hs.axuielement:actionNames](#actionNames)):
 * `object:do<action>()` is a shortcut for `object:performAction(action)`
   * See [hs.axuielement:performAction](#performAction) for a description of the return values and [hs.axuielement:actionNames](#actionNames) to get a list of actions that the element supports.

ParameterizedAttributes:
 * `object:<attribute>WithParameter(value)` is a shortcut for `object:parameterizedAttributeValue(attribute, value)
   * See [hs.axuielement:parameterizedAttributeValue](#parameterizedAttributeValue) for a description of the return values and [hs.axuielement:parameterizedAttributeNames](#parameterizedAttributeNames) to get a list of parameterized values that the element supports

   * The specific value required for a each parameterized attribute is different and is often application specific thus requiring some experimentation. Notes regarding identified parameter types and thoughts on some still being investigated will be provided in the Hammerspoon Wiki, hopefully shortly after this module becomes part of a Hammerspoon release.

---

## Submodules
 * [hs.axuielement.axtextmarker](hs.axuielement.axtextmarker.md)
 * [hs.axuielement.observer](hs.axuielement.observer.md)

---

## API Overview
**Constants** - _Useful values which cannot be changed_
 * [actions](#actions)
 * [attributes](#attributes)
 * [orientations](#orientations)
 * [parameterizedAttributes](#parameterizedattributes)
 * [roles](#roles)
 * [rulerMarkers](#rulermarkers)
 * [sortDirections](#sortdirections)
 * [subroles](#subroles)
 * [units](#units)

**Functions** - _API calls offered directly by the extension_
 * [searchCriteriaFunction](#searchcriteriafunction)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [applicationElement](#applicationelement)
 * [applicationElementForPID](#applicationelementforpid)
 * [systemElementAtPosition](#systemelementatposition)
 * [systemWideElement](#systemwideelement)
 * [windowElement](#windowelement)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [actionDescription](#actiondescription)
 * [actionNames](#actionnames)
 * [allAttributeValues](#allattributevalues)
 * [allDescendantElements](#alldescendantelements)
 * [asHSApplication](#ashsapplication)
 * [asHSWindow](#ashswindow)
 * [attributeNames](#attributenames)
 * [attributeValue](#attributevalue)
 * [attributeValueCount](#attributevaluecount)
 * [buildTree](#buildtree)
 * [childrenWithRole](#childrenwithrole)
 * [copy](#copy)
 * [elementAtPosition](#elementatposition)
 * [elementSearch](#elementsearch)
 * [isAttributeSettable](#isattributesettable)
 * [isValid](#isvalid)
 * [matchesCriteria](#matchescriteria)
 * [parameterizedAttributeNames](#parameterizedattributenames)
 * [parameterizedAttributeValue](#parameterizedattributevalue)
 * [path](#path)
 * [performAction](#performaction)
 * [pid](#pid)
 * [setAttributeValue](#setattributevalue)
 * [setTimeout](#settimeout)


---

## API Documentation

#### Constants


### [actions](#actions)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.actions[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of common accessibility object action names, provided for reference.                                                                     |
| **Notes**                                   | <ul><li>this table is provided for reference only and is not intended to be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in `hs.axuielement.actions`</li></ul> |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 966](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L966) |

---


### [attributes](#attributes)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.attributes[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of common accessibility object attribute names which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as keys in the match criteria argument.                                                                     |
| **Notes**                                   | <ul><li>This table is provided for reference only and is not intended to be comprehensive.</li><li>You can view the contents of this table from the Hammerspoon console by typing in `hs.axuielement.attributes`</li></ul> |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 743](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L743) |

---


### [orientations](#orientations)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.orientations[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of orientation types which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for "AXOrientation" in the match criteria argument.                                                                     |
| **Notes**                                   | <ul><li>this table is provided for reference only and may not be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in `hs.axuielement.orientations`</li></ul> |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 1127](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L1127) |

---


### [parameterizedAttributes](#parameterizedattributes)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.parameterizedAttributes[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of common accessibility object parameterized attribute names, provided for reference.                                                                     |
| **Notes**                                   | <ul><li>this table is provided for reference only and is not intended to be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in `hs.axuielement.parameterizedAttributes`</li><li>Parameterized attributes are attributes that take an argument when querying the element. There is very little documentation available for most of these and application developers can implement their own for which we may never be able to get any documentation. This table contains parameterized attribute names that are defined within the Apple documentation and a few others that have been discovered.</li><li>Documentation covering what has been discovered through experimentation about parameterized attributes is planned and should be added to the Hammerspoon wiki shortly after this module becomes part of a formal release.</li></ul> |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 926](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L926) |

---


### [roles](#roles)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.roles[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of common accessibility object roles which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for "AXRole" in the match criteria argument.                                                                     |
| **Notes**                                   | <ul><li>this table is provided for reference only and is not intended to be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in `hs.axuielement.roles`</li></ul> |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 990](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L990) |

---


### [rulerMarkers](#rulermarkers)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.rulerMarkers[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of ruler marker types which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for "AXMarkerType" in the match criteria argument.                                                                     |
| **Notes**                                   | <ul><li>this table is provided for reference only and may not be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in `hs.axuielement.rulerMarkers`</li></ul> |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 1159](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L1159) |

---


### [sortDirections](#sortdirections)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.sortDirections[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of sort direction types which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for "AXSortDirection" in the match criteria argument.                                                                     |
| **Notes**                                   | <ul><li>this table is provided for reference only and may not be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in `hs.axuielement.sortDirections`</li></ul> |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 1143](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L1143) |

---


### [subroles](#subroles)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.subroles[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of common accessibility object subroles which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for "AXSubrole" in the match criteria argument.                                                                     |
| **Notes**                                   | <ul><li>this table is provided for reference only and is not intended to be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in `hs.axuielement.subroles`</li></ul> |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 1067](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L1067) |

---


### [units](#units)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.units[]`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | A table of measurement unit types which may be used with [hs.axuielement:elementSearch](#elementSearch) or [hs.axuielement:matchesCriteria](#matchesCriteria) as attribute values for attributes which specify measurement unit types (e.g. "AXUnits", "AXHorizontalUnits", and "AXVerticalUnits") in the match criteria argument.                                                                     |
| **Notes**                                   | <ul><li>this table is provided for reference only and may not be comprehensive.</li><li>you can view the contents of this table from the Hammerspoon console by typing in `hs.axuielement.units`</li></ul> |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 1180](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L1180) |

---

#### Functions


### [searchCriteriaFunction](#searchcriteriafunction)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.searchCriteriaFunction(criteria) -> function`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a function for use with [hs.axuielement:elementSearch](#elementSearch) that uses [hs.axuielement:matchesCriteria](#matchesCriteria) with the specified criteria.                                                                     |
| **Parameters**                              | <ul><li>`criteria` - a criteria definition as defined for the [hs.axuielement:matchesCriteria](#matchesCriteria) method.</li></ul> |
| **Returns**                                 | <ul><li>a function which can be used as the `criteriaFunction` for [hs.axuielement:elementSearch](#elementSearch).</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/axuielement.lua line 464](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/axuielement.lua#L464) |

---

#### Constructors


### [applicationElement](#applicationelement)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.applicationElement(applicationObject) -> axuielementObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Returns the top-level accessibility object for the application specified by the `hs.application` object.                                                                     |
| **Parameters**                              | <ul><li>`applicationObject` - the `hs.application` object for the Application or a string or number which will be passed to `hs.application.find` to get an `hs.application` object.</li></ul> |
| **Returns**                                 | <ul><li>an axuielementObject for the application specified</li></ul>          |
| **Notes**                                   | <ul><li>if `applicationObject` is a string or number, only the first item found with `hs.application.find` will be used by this function to create an axuielementObject.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 98](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L98) |

---


### [applicationElementForPID](#applicationelementforpid)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.applicationElementForPID(pid) -> axuielementObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Returns the top-level accessibility object for the application with the specified process ID.                                                                     |
| **Parameters**                              | <ul><li>`pid` - the process ID of the application.</li></ul> |
| **Returns**                                 | <ul><li>an axuielementObject for the application specified, or nil if it cannot be determined</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 144](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L144) |

---


### [systemElementAtPosition](#systemelementatposition)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.systemElementAtPosition(x, y | pointTable) -> axuielementObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Returns the accessibility object at the specified position on the screen. The top-left corner of the primary screen is 0, 0.                                                                     |
| **Parameters**                              | <ul><li>`x` - the x coordinate of the screen location to test. If this parameter is provided, then the `y` parameter must also be provided and the `pointTable` parameter must not be provided.</li><li>`y` - the y coordinate of the screen location to test. This parameter is required if the `x` parameter is provided.</li><li>`pointTable` - the x and y coordinates of the screen location to test provided as a point-table, like the one returned by `hs.mouse.getAbsolutePosition` (a point-table is a table with key-value pairs for keys `x` and `y`). If this parameter is provided, then separate `x` and `y` parameters must not also be present.</li></ul> |
| **Returns**                                 | <ul><li>an axuielementObject for the object at the specified coordinates, or nil if no object could be identified.</li></ul>          |
| **Notes**                                   | <ul><li>See also [hs.axuielement:elementAtPosition](#elementAtPosition) -- this function is a shortcut for `hs.axuielement.systemWideElement():elementAtPosition(...)`.</li><li>This function does hit-testing based on window z-order (that is, layering). If one window is on top of another window, the returned accessibility object comes from whichever window is topmost at the specified location.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/axuielement.lua line 86](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/axuielement.lua#L86) |

---


### [systemWideElement](#systemwideelement)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.systemWideElement() -> axuielementObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Returns an accessibility object that provides access to system attributes.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the axuielementObject for the system attributes</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 126](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L126) |

---


### [windowElement](#windowelement)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement.windowElement(windowObject) -> axuielementObject`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Returns the accessibility object for the window specified by the `hs.window` object.                                                                     |
| **Parameters**                              | <ul><li>`windowObject` - the `hs.window` object for the window or a string or number which will be passed to `hs.window.find` to get an `hs.window` object.</li></ul> |
| **Returns**                                 | <ul><li>an axuielementObject for the window specified</li></ul>          |
| **Notes**                                   | <ul><li>if `windowObject` is a string or number, only the first item found with `hs.window.find` will be used by this function to create an axuielementObject.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 70](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L70) |

---

#### Methods


### [actionDescription](#actiondescription)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:actionDescription(action) -> string | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a localized description of the specified accessibility object's action.                                                                     |
| **Parameters**                              | <ul><li>`action` - the name of the action, as specified by [hs.axuielement:actionNames](#actionNames).</li></ul> |
| **Returns**                                 | <ul><li>a string containing a description of the object's action, nil if no description is available, or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | <ul><li>The action descriptions are provided by the target application; as such their accuracy and usefulness rely on the target application's developers.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 254](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L254) |

---


### [actionNames](#actionnames)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:actionNames() -> table | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a list of all the actions the specified accessibility object can perform.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>an array of the names of all actions supported by the axuielementObject or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | <ul><li>Common action names can be found in the [hs.axuielement.actions](#actions) table; however, this method will list only those names which are supported by this object, and is not limited to just those in the referenced table.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 221](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L221) |

---


### [allAttributeValues](#allattributevalues)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:allAttributeValues([includeErrors]) -> table | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a table containing key-value pairs for all attributes of the accessibility object.                                                                     |
| **Parameters**                              | <ul><li>`includeErrors` - an optional boolean, default false, that specifies whether attribute names which generate an error when retrieved are included in the returned results.</li></ul> |
| **Returns**                                 | <ul><li>a table with key-value pairs corresponding to the attributes of the accessibility object or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | <ul><li>if `includeErrors` is not specified or is false, then attributes which exist for the element, but currently have no value assigned, will not appear in the table. This is because Lua treats a nil value for a table's key-value pair as an instruction to remove the key from the table, if it currently exists.</li><li>To include attributes which exist but are currently unset, you need to specify `includeErrors` as true.</li><li>  attributes for which no value is currently assigned will be given a table value with the following key-value pairs:</li><li>    `_code` = -25212</li><li>    `error` = "Requested value does not exist"</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 315](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L315) |

---


### [allDescendantElements](#alldescendantelements)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:allDescendantElements(callback, [withParents]) -> elementSearchObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Query the accessibility object for all child accessibility objects and their descendants                                                                     |
| **Parameters**                              | <ul><li>`callback`    - a required function which should expect two arguments: a `msg` string specifying how the search ended, and a table containing the discovered descendant elements. `msg` will be "completed" when the traversal has completed normally and will contain a string starting with "**" if it terminates early for some reason (see Notes: section for more information)</li><li>`withParents` - an optional boolean, default false, indicating that the parent of objects (and their descendants) should be collected as well.</li></ul> |
| **Returns**                                 | <ul><li>an elementSearchObject as described in [hs.axuielement:elementSearch](#elementSearch)</li></ul>          |
| **Notes**                                   | <ul><li>This method is syntactic sugar for `hs.axuielement:elementSearch(callback, { [includeParents = withParents] })`. Please refer to [hs.axuielement:elementSearch](#elementSearch) for details about the returned object and callback arguments.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/axuielement.lua line 502](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/axuielement.lua#L502) |

---


### [asHSApplication](#ashsapplication)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:asHSApplication() -> hs.application object | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | If the element refers to an application, return an `hs.application` object for the element.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>if the element refers to an application, return an `hs.application` object for the element ; otherwise return nil</li></ul>          |
| **Notes**                                   | <ul><li>An element is considered an application by this method if it has an AXRole of AXApplication and has a process identifier (pid).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 645](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L645) |

---


### [asHSWindow](#ashswindow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:asHSWindow() -> hs.window object | nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | If the element refers to a window, return an `hs.window` object for the element.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>if the element refers to a window, return an `hs.window` object for the element ; otherwise return nil</li></ul>          |
| **Notes**                                   | <ul><li>An element is considered a window by this method if it has an AXRole of AXWindow.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 680](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L680) |

---


### [attributeNames](#attributenames)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:attributeNames() -> table | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a list of all the attributes supported by the specified accessibility object.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>an array of the names of all attributes supported by the axuielementObject or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | <ul><li>Common attribute names can be found in the [hs.axuielement.attributes](#attributes) tables; however, this method will list only those names which are supported by this object, and is not limited to just those in the referenced table.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 188](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L188) |

---


### [attributeValue](#attributevalue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:attributeValue(attribute) -> value | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the value of an accessibility object's attribute.                                                                     |
| **Parameters**                              | <ul><li>`attribute` - the name of the attribute, as specified by [hs.axuielement:attributeNames](#attributeNames).</li></ul> |
| **Returns**                                 | <ul><li>the current value of the attribute, nil if the attribute has no value, or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 286](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L286) |

---


### [attributeValueCount](#attributevaluecount)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:attributeValueCount(attribute) -> integer | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the count of the array of an accessibility object's attribute value.                                                                     |
| **Parameters**                              | <ul><li>`attribute` - the name of the attribute, as specified by [hs.axuielement:attributeNames](#attributeNames).</li></ul> |
| **Returns**                                 | <ul><li>the number of items in the value for the attribute, if it is an array, or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 365](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L365) |

---


### [buildTree](#buildtree)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:buildTree(callback, [depth], [withParents]) -> elementSearchObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Captures all of the available information for the accessibility object and its descendants and returns it in a table for inspection.                                                                     |
| **Parameters**                              | <ul><li>`callback` - a required function which should expect two arguments: a `msg` string specifying how the search ended, and a table containing the recorded information. `msg` will be "completed" when the search has completed normally (or reached the specified depth) and will contain a string starting with "**" if it terminates early for some reason (see Notes: section for more information)</li><li>`depth`    - an optional integer, default `math.huge`, specifying the maximum depth from the initial accessibility object that should be visited to identify descendant elements and their attributes.</li><li>`withParents` - an optional boolean, default false, specifying whether or not an element's (or descendant's) attributes for `AXParent` and `AXTopLevelUIElement` should also be visited when identifying additional elements to include in the results table.</li></ul> |
| **Returns**                                 | <ul><li>an elementSearchObject as described in [hs.axuielement:elementSearch](#elementSearch)</li></ul>          |
| **Notes**                                   | <ul><li>* The format of the `results` table passed to the callback for this method is primarily for debugging and exploratory purposes and may not be arranged for easy programatic evaluation.</li><li>This method is syntactic sugar for `hs.axuielement:elementSearch(callback, { objectOnly = false, asTree = true, [depth = depth], [includeParents = withParents] })`. Please refer to [hs.axuielement:elementSearch](#elementSearch) for details about the returned object and callback arguments.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/axuielement.lua line 478](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/axuielement.lua#L478) |

---


### [childrenWithRole](#childrenwithrole)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:childrenWithRole(role) -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a table containing only those immediate children of the element that perform the specified role.                                                                     |
| **Parameters**                              | <ul><li>`role` - a string specifying the role that the returned children must perform. Example values can be found in [hs.axuielement.roles](#roles).</li></ul> |
| **Returns**                                 | <ul><li>a table containing zero or more axuielementObjects.</li></ul>          |
| **Notes**                                   | <ul><li>only the immediate children of the object are searched.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/axuielement.lua line 972](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/axuielement.lua#L972) |

---


### [copy](#copy)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:copy() -> axuielementObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Return a duplicate userdata reference to the Accessibility object.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a new userdata object representing a new reference to the Accessibility object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 171](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L171) |

---


### [elementAtPosition](#elementatposition)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:elementAtPosition(x, y | pointTable) -> axuielementObject | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the accessibility object at the specified position on the screen. The top-left corner of the primary screen is 0, 0.                                                                     |
| **Parameters**                              | <ul><li>`x` - the x coordinate of the screen location to test. If this parameter is provided, then the `y` parameter must also be provided and the `pointTable` parameter must not be provided.</li><li>`y` - the y coordinate of the screen location to test. This parameter is required if the `x` parameter is provided.</li><li>`pointTable` - the x and y coordinates of the screen location to test provided as a point-table, like the one returned by `hs.mouse.getAbsolutePosition` (a point-table is a table with key-value pairs for keys `x` and `y`). If this parameter is provided, then separate `x` and `y` parameters must not also be present.</li></ul> |
| **Returns**                                 | <ul><li>an axuielementObject for the object at the specified coordinates, or nil and an error string if no object could be identified or an accessibility error occurred</li></ul>          |
| **Notes**                                   | <ul><li>This method can only be called on an axuielementObject that represents an application or the system-wide element (see [hs.axuielement.systemWideElement](#systemWideElement)).</li><li>This function does hit-testing based on window z-order (that is, layering). If one window is on top of another window, the returned accessibility object comes from whichever window is topmost at the specified location.</li><li>If this method is called on an axuielementObject representing an application, the search is restricted to the application.</li><li>If this method is called on an axuielementObject representing the system-wide element, the search is not restricted to any particular application.  See [hs.axuielement.systemElementAtPosition](#systemElementAtPosition).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 533](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L533) |

---


### [elementSearch](#elementsearch)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:elementSearch(callback, [criteria], [namedModifiers]) -> elementSearchObject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Search for and generate a table of the accessibility elements for the attributes and descendants of this object based on the specified criteria.                                                                     |
| **Parameters**                              | <ul><li>`callback`       - a (usually) required function which will receive the results of this search. The callback should expect three arguments and return none. The arguments to the callback function will be `msg`, a string specifying how the search ended and `results`, the elementSearchObject containing the requested results, and the number of items added to the results (see `count` in `namedModifiers`). `msg` will be "completed" if the search completes normally, or a string starting with "**" if it is terminated early (see Returns: and Notes: for more details).</li><li>`criteria`       - an optional function which should accept one argument (the current element being examined) and return true if it should be included in the results or false if it should be rejected. See [hs.axuielement.searchCriteriaFunction](#searchCriteriaFunction) to create a search function that uses [hs.axuielement:matchesCriteria](#matchesCriteria) for evaluation.</li><li>`namedModifiers` - an optional table specifying key-value pairs that further modify or control the search. This table may contain 0 or more of the following keys:
  `count`          - an optional integer, default `math.huge`, specifying the maximum number of matches to collect before ending the search and invoking the callback. You can continue the search to find additional elements by invoking `elementSearchObject:next()` (described below in the `Returns` section) on the return value of this method, or on the results argument passed to the callback.
  `depth`          - an optional integer, default `math.huge`, specifying the maximum number of steps (descendants) from the initial accessibility element the search should visit. If you know that your desired element(s) are relatively close to your starting element, setting this to a lower value can significantly speed up the search.
  The following are also recognized, but may impact the speed of the search, the responsiveness of Hammerspoon, or the format of the results in ways that limit further filtering and are not recommended except when you know that you require them:`asTree`         - an optional boolean, default false, and ignored if `criteria` is specified and non-empty, `objectOnly` is true, or `count` is specified. This modifier specifies whether the search results should return as an array table of tables containing each element's details (false) or as a tree where in which the root node details are the key-value pairs of the returned table and descendant elements are likewise described in subtables attached to the attribute name they belong to (true). This format is primarily for debugging and exploratory purposes and may not be arranged for easy programatic evaluation.`includeParents` - a boolean, default false, specifying whether or not parent attributes (`AXParent` and `AXTopLevelUIElement`) should be examined during the search. Note that in most cases, setting this value to true will end up traversing the entire Accessibility structure for the target application and may significantly slow down the search.`noCallback`     - an optional boolean, default false, and ignored if `callback` is not also nil, allowing you to specify nil as the callback when set to true. This feature requires setting this named argument to true *and* specifying the callback field as nil because starting a query from an element with a lot of descendants **WILL** block Hammerspoon and slow down the responsiveness of your computer (I've seen blocking for over 5 minutes in extreme cases) and should be used *only* when you know you are starting from close to the end of the element hierarchy.`objectOnly`     - an optional boolean, default true, specifying whether each result in the final table will be the accessibility element discovered (true) or a table containing details about the element include the attribute names, actions, etc. for the element (false). This latter format is primarily for debugging and exploratory purposes and may not be arranged for easy programatic evaluation.</li></ul> |
| **Returns**                                 | <ul><li>an elementSearchObject which contains metamethods allowing you to check to see if the process has completed and cancel it early if desired. The methods include:</li><li>  `elementSearchObject:cancel([reason])` - cancels the current search and invokes the callback with the partial results already collected. If you specify `reason`, the `msg` argument for the callback will be `** <reason>`; otherwise it will be "** cancelled".</li><li>  `elementSearchObject:isRunning()`      - returns true if the search is currently ongoing or false if it has completed or been cancelled.</li><li>  `elementSearchObject:matched()`        - returns an integer specifying the number of elements which have already been found that meet the specified criteria function.</li><li>  `elementSearchObject:runTime()`        - returns an integer specifying the number of seconds spent performing this search. Note that this is *not* an accurate measure of how much time a given search will always take because the time will be greatly affected by how much other activity is occurring within Hammerspoon and on the users computer. Resuming a cancelled search or a search which invoked the callback because it reached `count` items with the `next` method (described below) will cause this number to begin increasing again to provide a cumulative total of time spent performing the search; time between when the callback is invoked and the `next` method is invoked is not included.</li><li>  `elementSearchObject:visited()`        - returns an integer specifying the number of elements which have been examined during the search so far.</li><li>  If `asTree` is false or not specified, the following additional methods will be available:</li><li>    `elementSearchObject:filter(criteria, [callback]) -> filterObject`</li><li>      returns a new table containing elements in the search results that match the specified criteria.</li><li>        `criteria`  - a required function which should accept one argument (the current element being examined) and return true if it should be included in the results or false if it should be rejected. See [hs.axuielement.searchCriteriaFunction](#searchCriteriaFunction) to create a search function that uses [hs.axuielement:matchesCriteria](#matchesCriteria) for evaluation.</li><li>        `callback`  - an optional callback which should expect two arguments and return none. If a callback is specified, the callback will receive two arguments, a msg indicating how the callback ended (the message format matches the style defined for this method) and the filterObject which contains the matching elements.</li><li>      The filterObject returned by this method and passed to the callback, if defined, will support the following methods as defined here: `cancel`, `filter`, `isRunning`, `matched`, `runTime`, and `visited`.</li><li>    `elementSearchObject:next()` - if the search was cancelled or reached the count of matches specified, this method will continue the search where it left off. The elementSearchObject returned when the callback is next invoked will have up to `count` items added to the existing results (calls to `next` are cumulative for the total results captured in the elementSearchObject). The third argument to the callback will be the number of items *added* to the search results, not the number of items *in* the search results.</li></ul>          |
| **Notes**                                   | <ul><li>This method utilizes coroutines to keep Hammerspoon responsive, but may be slow to complete if `includeParents` is true, if you do not specify `depth`, or if you start from an element that has a lot of descendants (e.g. the application element for a web browser). This is dependent entirely upon how many active accessibility elements the target application defines and where you begin your search and cannot reliably be determined up front, so you may need to experiment to find the best balance for your specific requirements.</li><li>The search performed is a breadth-first search, so in general earlier elements in the results table will be "closer" in the Accessibility hierarchy to the starting point than later elements.</li><li>The `elementSearchObject` returned by this method and the results passed in as the second argument to the callback function are the same object -- you can use either one in your code depending upon which makes the most sense. Results that match the criteria function are added to the `elementSearchObject` as they are found, so if you examine the object/table returned by this method and determine that you have located the element or elements you require before the callback has been invoked, you can safely invoke the cancel method to end the search early.</li><li>  The exception to this is when `asTree` is true and `objectsOnly` is false and the search criteria is nil -- see [hs.axuielement:buildTree](#buildTree). In this case, the results passed to the callback will be equal to `elementSearchObject[1]`.</li><li>If `objectsOnly` is specified as false, it may take some time after `cancel` is invoked for the mapping of element attribute tables to the descendant elements in the results set -- this is a by product of the need to iterate through the results to match up all of the instances of each element to it's attribute table.</li><li>[hs.axuielement:allDescendantElements](#allDescendantElements) is syntactic sugar for `hs.axuielement:elementSearch(callback, { [includeParents = withParents] })`</li><li>[hs.axuielement:buildTree](#buildTree) is syntactic sugar for `hs.axuielement:elementSearch(callback, { objectOnly = false, asTree = true, [depth = depth], [includeParents = withParents] })`</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/axuielement.lua line 766](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/axuielement.lua#L766) |

---


### [isAttributeSettable](#isattributesettable)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:isAttributeSettable(attribute) -> boolean | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns whether the specified accessibility object's attribute can be modified.                                                                     |
| **Parameters**                              | <ul><li>`attribute` - the name of the attribute, as specified by [hs.axuielement:attributeNames](#attributeNames).</li></ul> |
| **Returns**                                 | <ul><li>a boolean value indicating whether or not the value of the parameter can be modified or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 421](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L421) |

---


### [isValid](#isvalid)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:isValid() -> boolean | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns whether the specified accessibility object is still valid.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a boolean value indicating whether or not the accessibility object is still valid or nil and an error string if any other accessibility error occurred</li></ul>          |
| **Notes**                                   | <ul><li>an accessibilityObject can become invalid for a variety of reasons, including but not limited to the element referred to no longer being available (e.g. an element referring to a window or one of its descendants that has been closed) or the application terminating.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 447](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L447) |

---


### [matchesCriteria](#matchescriteria)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:matchesCriteria(criteria) -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns true if the axuielementObject matches the specified criteria or false if it does not.                                                                     |
| **Parameters**                              | <ul><li>`criteria`  - the criteria to compare against the accessibility object</li></ul> |
| **Returns**                                 | <ul><li>true if the axuielementObject matches the criteria, false if it does not.</li></ul>          |
| **Notes**                                   | <ul><li>the `criteria` argument must be one of the following:</li><li>  a single string, specifying the value the element's AXRole attribute must equal for a positive match</li><li>  an array table of strings specifying a list of possible values the element's AXRole attribute can equal for a positive match</li><li>  a table of key-value pairs specifying a more complex criteria. The table should be defined as follows:</li><li>    one or more of the following must be specified (though all specified must match):</li><li>      `attribute`              -- a string, or table of strings, specifying attributes that the element must support.</li><li>      `action`                 -- a string, or table of strings, specifying actions that the element must be able to perform.</li><li>      `parameterizedAttribute` -- a string, or table of strings, specifying parametrized attributes that the element must support.</li><li>    if the `attribute` key is specified, you can use one of the following to specify a specific value the attribute must equal for a positive match. No more than one of these should be provided. If neither are present, then only the existence of the attributes specified by `attribute` are required.</li><li>      `value`                  -- a value, or table of values, that a specified attribute must equal. If it's a table, then only one of the values has to match the attribute value for a positive match. Note that if you specify more than one attribute with the `attribute` key, you must provide at least one value for each attribute in this table (order does not matter, but the match will fail if any attribute does not match at least one value provided).</li><li>        when specifying a value which is itself a table with keys (e.g. frame, size, url, color, etc.) then you *must* provide the value or values as a table of tables, e.g. `{ { y = 22 } }`.</li><li>          only those keys which are specified within the value are checked for equality (or pattern matching). Values which are present in the attribute's value but are not specified in the comparison value are ignored (i.e. the previous example of `y = 22` would only check the `y` component of an AXFrame attribute -- the `x`, `h`, and `w` values would be ignored).</li><li>          For value components which are numeric, e.g. `22` in the previous example, the default comparison is equality. You may change this with the `comparison` key described below in the optional keys.</li><li>          For possible keys when trying to match a color, see the documentation for `hs.drawing.color`.</li><li>          For possible keys when trying to match a URL, use `url = <string>` and/or `filePath = <string>`. The string for the specified table key will be compared in accordance with the `pattern` optional key described below.</li><li>        when specifying a value which is itself a table of values (e.g. a list of axuielementObjects) you *must* provide the value or values as a table of tables, e.g. `{ { obj1, obj2 } }`.</li><li>          Order of the elements provided in the comparison value does not matter -- this only tests for existence within the attributes value.</li><li>          The test is for inclusion only -- the attribute's value may contain other elements as well, but must contain those specified within the comparison value.</li><li>      `nilValue`               -- a boolean, specifying that the attributes must not have an assigned value (true) or may be assigned any value except nil (false). If the `value` key is specified, this key is ignored. Note that this applies to *all* of the attributes specified with the `attribute` key.</li><li>    the following are optional keys and are not required:</li><li>      `pattern`                -- a boolean, default false, specifying whether string matches for attribute values should be evaluated with `string.match` (true) or as exact matches (false). See the Lua manual, section 6.4.1 (`help.lua._man._6_4_1` in the Hammerspoon console). If the `value` key is not set, than this key is ignored.</li><li>      `invert`                 -- a boolean, default false, specifying inverted logic for the criteria result --- if this is true and the criteria matches, evaluate criteria as false; otherwise evaluate as true.</li><li>      `comparison`             -- a string, default "==", specifying the comparison to be used when comparing numeric values. Possible comparison strings are: "==" for equality, "<" for less than, "<=" for less than or equal to, ">" for greater than, ">=" for greater than or equal to, or "~=" for not equal to.</li><li></li><li>  an array table of one or more key-value tables as described immediately above; the element must be a positive match for all of the individual criteria tables specified (logical AND).</li><li>This method is used by [hs.axuielement.searchCriteriaFunction](#searchCriteriaFunction) to create criteria functions compatible with [hs.axuielement:elementSearch](#elementSearch).</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/axuielement.lua line 265](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/axuielement.lua#L265) |

---


### [parameterizedAttributeNames](#parameterizedattributenames)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:parameterizedAttributeNames() -> table | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a list of all the parameterized attributes supported by the specified accessibility object.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>an array of the names of all parameterized attributes supported by the axuielementObject or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 391](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L391) |

---


### [parameterizedAttributeValue](#parameterizedattributevalue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:parameterizedAttributeValue(attribute, parameter) -> value | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the value of an accessibility object's parameterized attribute.                                                                     |
| **Parameters**                              | <ul><li>`attribute` - the name of the attribute, as specified by [hs.axuielement:parameterizedAttributeNames](#parameterizedAttributeNames).</li><li>`parameter` - the parameter required by the parameterized attribute.</li></ul> |
| **Returns**                                 | <ul><li>the current value of the parameterized attribute, nil if the parameterized attribute has no value, or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | <ul><li>The specific parameter required for a each parameterized attribute is different and is often application specific thus requiring some experimentation. Notes regarding identified parameter types and thoughts on some still being investigated will be provided in the Hammerspoon Wiki, hopefully shortly after this module becomes part of a Hammerspoon release.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 582](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L582) |

---


### [path](#path)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:path() -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns a table of axuielements tracing this object through its parent objects to the root for this element, most likely an application object or the system wide object.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>a table containing this object and 0 or more parent objects representing the path from the root object to this element.</li></ul>          |
| **Notes**                                   | <ul><li>this object will always exist as the last element in the table (e.g. at `table[#table]`) with its most immediate parent at `#table - 1`, etc. until the rootmost object for this element is reached at index position 1.</li><li>an axuielement object representing an application or the system wide object is its own rootmost object and will return a table containing only itself (i.e. `#table` will equal 1)</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/axuielement.lua line 211](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/axuielement.lua#L211) |

---


### [performAction](#performaction)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:performAction(action) -> axuielement | false | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Requests that the specified accessibility object perform the specified action.                                                                     |
| **Parameters**                              | <ul><li>`action` - the name of the action, as specified by [hs.axuielement:actionNames](#actionNames).</li></ul> |
| **Returns**                                 | <ul><li>if the requested action was accepted by the target, returns the axuielementObject; if the requested action was rejected, returns false; otherwise returns nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | <ul><li>The return value only suggests success or failure, but is not a guarantee.  The receiving application may have internal logic which prevents the action from occurring at this time for some reason, even though this method returns success (the axuielementObject).  Contrawise, the requested action may trigger a requirement for a response from the user and thus appear to time out, causing this method to return false or nil.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 503](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L503) |

---


### [pid](#pid)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:pid() -> integer | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the process ID associated with the specified accessibility object.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>the process ID for the application to which the accessibility object ultimately belongs or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 478](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L478) |

---


### [setAttributeValue](#setattributevalue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:setAttributeValue(attribute, value) -> axuielementObject  | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the accessibility object's attribute to the specified value.                                                                     |
| **Parameters**                              | <ul><li>`attribute` - the name of the attribute, as specified by [hs.axuielement:attributeNames](#attributeNames).</li><li>`value`     - the value to assign to the attribute</li></ul> |
| **Returns**                                 | <ul><li>the axuielementObject on success; nil and an error string if the attribute could not be set or an accessibility error occurred.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 617](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L617) |

---


### [setTimeout](#settimeout)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `hs.axuielement:setTimeout(value) -> axuielementObject | nil, errString`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Sets the timeout value used accessibility queries performed from this element.                                                                     |
| **Parameters**                              | <ul><li>`value` - the number of seconds for the new timeout value. Must be 0 or positive.</li></ul> |
| **Returns**                                 | <ul><li>the axuielementObject or nil and an error string if an accessibility error occurred</li></ul>          |
| **Notes**                                   | <ul><li>To change the global timeout affecting all queries on elements which do not have a specific timeout set, use this method on the systemwide element (see [hs.axuielement.systemWideElement](#systemWideElement).</li><li>Changing the timeout value for an axuielement object only changes the value for that specific element -- other axuieleement objects that may refer to the identical accessibility item are not affected.</li><li>Setting the value to 0.0 resets the timeout -- if applied to the `systemWideElement`, the global default will be reset to its default value; if applied to another axuielement object, the timeout will be reset to the current global value as applied to the systemWideElement.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [extensions/axuielement/libaxuielement.m line 710](https://github.com/CommandPost/CommandPost-App/blob/master/extensions/axuielement/libaxuielement.m#L710) |

---

