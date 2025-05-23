# cp.apple.fcpxml

A collection of tools for handling FCPXML Documents.

---

## Submodules
 * [cp.apple.fcpxml.time](cp.apple.fcpxml.time.md)
 * [cp.apple.fcpxml.timecode](cp.apple.fcpxml.timecode.md)

---

## API Overview
**Constants** - _Useful values which cannot be changed_
 * [HAS_OFFSET_ATTRIBUTE](#has_offset_attribute)

**Functions** - _API calls offered directly by the extension_
 * [latestDTDVersion](#latestdtdversion)
 * [supportedDTDs](#supporteddtds)
 * [valid](#valid)


---

## API Documentation

#### Constants


### [HAS_OFFSET_ATTRIBUTE](#has_offset_attribute)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.fcpxml.HAS_OFFSET_ATTRIBUTE <table: string:boolean>`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Table of elements that have an `offset` attribute.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/fcpxml/init.lua line 20](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/fcpxml/init.lua#L20) |

---

#### Functions


### [latestDTDVersion](#latestdtdversion)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.fcpxml.latestDTDVersion() -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the latest supported FCPXML DTD version.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The latest DTD version as a string, for example: "1.8".</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/fcpxml/init.lua line 61](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/fcpxml/init.lua#L61) |

---


### [supportedDTDs](#supporteddtds)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.fcpxml.supportedDTDs() -> table`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Returns a table containing the version numbers of all the DTD documents included in this extension.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table of supported DTD versions as strings.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/fcpxml/init.lua line 38](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/fcpxml/init.lua#L38) |

---


### [valid](#valid)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.fcpxml:valid(path[, version]) -> string|boolean, string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Validates an FCPXML document against a document type definition (DTD).                                                                     |
| **Parameters**                              | <ul><li>path - The path and path of the FCPXML document you want to validate.</li><li>version - The optional FCPXML version you want to validate against.</li></ul> |
| **Returns**                                 | <ul><li>The FCPXML path or `false` if not valid.</li><li>The output from xmllint as a string.</li></ul>          |
| **Notes**                                   | <ul><li>If a version is not supplied, we will try and read the version</li><li>   from the file itself, and if that's not possible, we'll default</li><li>   to the latest FCPXML version.</li><li>If a `fcpxmld` bundle path is supplied, this function will return</li><li>   the path to the `Info.fcpxml` document if valid.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/fcpxml/init.lua line 76](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/fcpxml/init.lua#L76) |

---

