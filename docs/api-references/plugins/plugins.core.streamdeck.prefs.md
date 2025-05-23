# plugins.core.streamdeck.prefs

Stream Deck Preferences Panel

---

## API Overview
**Variables** - _Configurable values_
 * [defaultIconPath](#defaulticonpath)
 * [supportedExtensions](#supportedextensions)

**Functions** - _API calls offered directly by the extension_
 * [buildIconFromLabel](#buildiconfromlabel)
 * [processEncodedIcon](#processencodedicon)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [automaticallyApplyIconFromAction](#automaticallyapplyiconfromaction)
 * [backgroundColour](#backgroundcolour)
 * [iconHistory](#iconhistory)
 * [lastDevice](#lastdevice)
 * [lastExportPath](#lastexportpath)
 * [lastIconPath](#lasticonpath)
 * [lastImportPath](#lastimportpath)
 * [lastUnit](#lastunit)
 * [pasteboard](#pasteboard)
 * [previewSelectedApplicationAndBankOnHardware](#previewselectedapplicationandbankonhardware)
 * [resizeImagesOnImport](#resizeimagesonimport)
 * [snippetsRefreshFrequency](#snippetsrefreshfrequency)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [setItem](#setitem)


---

## API Documentation

#### Variables


### [defaultIconPath](#defaulticonpath)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.defaultIconPath -> string`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Default Path where built-in icons are stored                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 98](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L98) |

---


### [supportedExtensions](#supportedextensions)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.supportedExtensions -> string`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Table of supported extensions for Stream Deck Icons.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 91](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L91) |

---

#### Functions


### [buildIconFromLabel](#buildiconfromlabel)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.buildIconFromLabel(params) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Creates a new icon image from a string.                                                                     |
| **Parameters**                              | <ul><li>params - A table of parameters.</li></ul> |
| **Returns**                                 | <ul><li>A new encoded icon as URL string.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 614](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L614) |

---


### [processEncodedIcon](#processencodedicon)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.processEncodedIcon(icon, controlType) -> string`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Processes an encoded icon.                                                                     |
| **Parameters**                              | <ul><li>icon - The encoded icon as URL string or a hs.image object.</li><li>button - The button ID.</li></ul> |
| **Returns**                                 | <ul><li>A new encoded icon as URL string.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 680](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L680) |

---

#### Fields


### [automaticallyApplyIconFromAction](#automaticallyapplyiconfromaction)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.automaticallyApplyIconFromAction <cp.prop: boolean>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Automatically Apply Icon from Action                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 103](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L103) |

---


### [backgroundColour](#backgroundcolour)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.backgroundColour <cp.prop: string>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Background Colour.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 108](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L108) |

---


### [iconHistory](#iconhistory)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.iconHistory <cp.prop: table>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Icon History                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 123](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L123) |

---


### [lastDevice](#lastdevice)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.lastDevice <cp.prop: string>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Last Device used in the Preferences Panel.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 143](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L143) |

---


### [lastExportPath](#lastexportpath)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.lastExportPath <cp.prop: string>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Last Export path.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 133](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L133) |

---


### [lastIconPath](#lasticonpath)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.lastIconPath <cp.prop: string>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Last icon path.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 118](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L118) |

---


### [lastImportPath](#lastimportpath)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.lastImportPath <cp.prop: string>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Last Import path.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 138](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L138) |

---


### [lastUnit](#lastunit)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.lastUnit <cp.prop: string>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Last Unit used in the Preferences Panel.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 153](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L153) |

---


### [pasteboard](#pasteboard)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.pasteboard <cp.prop: table>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Pasteboard                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 128](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L128) |

---


### [previewSelectedApplicationAndBankOnHardware](#previewselectedapplicationandbankonhardware)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.previewSelectedApplicationAndBankOnHardware <cp.prop: boolean>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Should we preview the selected application and bank on hardware?                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/manager/init.lua line 51](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/manager/init.lua#L51) |

---


### [resizeImagesOnImport](#resizeimagesonimport)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.resizeImagesOnImport <cp.prop: string>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Resize Icons on Import Preference.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 113](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L113) |

---


### [snippetsRefreshFrequency](#snippetsrefreshfrequency)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.snippetsRefreshFrequency <cp.prop: string>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | How often snippets are refreshed.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/core/streamdeck/manager/init.lua line 56](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/manager/init.lua#L56) |

---

#### Methods


### [setItem](#setitem)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.core.streamdeck.prefs.setItem(app, bank, button, key, [value]) -> none`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Update the Stream Deck layout file.                                                                     |
| **Parameters**                              | <ul><li>app - The application bundle ID as a string</li><li>bank - The bank ID as a string</li><li>button - The button ID as a string</li><li>key - The key as a string or a table if replacing the entire button contents</li><li>value - The optional value</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/core/streamdeck/prefs/init.lua line 563](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/core/streamdeck/prefs/init.lua#L563) |

---

