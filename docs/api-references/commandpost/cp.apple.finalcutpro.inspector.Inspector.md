# cp.apple.finalcutpro.inspector.Inspector

Inspector

---

## API Overview
**Constants** - _Useful values which cannot be changed_
 * [INSPECTOR_TABS](#inspector_tabs)

**Functions** - _API calls offered directly by the extension_
 * [matches](#matches)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [Inspector](#inspector)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [audio](#audio)
 * [bottomBarUI](#bottombarui)
 * [color](#color)
 * [generator](#generator)
 * [info](#info)
 * [isFullHeight](#isfullheight)
 * [isShowing](#isshowing)
 * [labelUI](#labelui)
 * [panelUI](#panelui)
 * [projectInfo](#projectinfo)
 * [propertiesUI](#propertiesui)
 * [share](#share)
 * [text](#text)
 * [title](#title)
 * [topBarUI](#topbarui)
 * [transition](#transition)
 * [video](#video)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [doFindTabButton](#dofindtabbutton)
 * [doHide](#dohide)
 * [doSelectTab](#doselecttab)
 * [doShow](#doshow)
 * [hide](#hide)
 * [selectedTab](#selectedtab)
 * [selectTab](#selecttab)
 * [show](#show)
 * [tabAvailable](#tabavailable)


---

## API Documentation

#### Constants


### [INSPECTOR_TABS](#inspector_tabs)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS -> table`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Table of supported Inspector Tabs                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 38](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L38) |

---

#### Functions


### [matches](#matches)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.matches(element) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks to see if an element matches what we think it should be.                                                                     |
| **Parameters**                              | <ul><li>element - axuielementObject</li></ul> |
| **Returns**                                 | <ul><li>`true` if matches otherwise `false`</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 54](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L54) |

---

#### Constructors


### [Inspector](#inspector)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector(parent) -> Inspector`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new Inspector.                                                                     |
| **Parameters**                              | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                 | <ul><li>The Inspector object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 70](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L70) |

---

#### Fields


### [audio](#audio)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.audio <cp.apple.finalcutpro.inspector.AudioInspector>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The [AudioInspector](cp.apple.finalcutpro.inspector.AudioInspector.md).                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 609](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L609) |

---


### [bottomBarUI](#bottombarui)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.bottomBarUI <cp.prop: hs.axuielement; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns the bottom bar `axuielement` for the Inspector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 169](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L169) |

---


### [color](#color)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.color <cp.apple.finalcutpro.inspector.ColorInspector>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The [ColorInspector](cp.apple.finalcutpro.inspector.ColorInspector.md).                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 635](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L635) |

---


### [generator](#generator)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.generator <cp.apple.finalcutpro.inspector.GeneratorInspector>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The [GeneratorInspector](package.GeneratorInspector.md)                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 537](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L537) |

---


### [info](#info)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.info <cp.apple.finalcutpro.inspector.InfoInspector>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The  [InfoInspector](cp.apple.finalcutpro.inspector.InfoInspector.md).                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 550](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L550) |

---


### [isFullHeight](#isfullheight)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.isFullHeight <cp.prop: boolean>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns `true` if the Inspector is full height.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 201](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L201) |

---


### [isShowing](#isshowing)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.isShowing <cp.prop: boolean; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns `true` if the Inspector is showing otherwise `false`                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 191](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L191) |

---


### [labelUI](#labelui)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.labelUI <cp.prop: hs.axuielement; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns the `axuielement` for text label at the top of the Inspector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 181](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L181) |

---


### [panelUI](#panelui)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.panelUI <cp.prop: hs.axuielement; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns the central panel `axuielement` for the Inspector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 130](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L130) |

---


### [projectInfo](#projectinfo)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.projectInfo <cp.apple.finalcutpro.inspector.InfoProjectInspector>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The  [InfoProjectInspector](cp.apple.finalcutpro.inspector.InfoProjectInspector.md).                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 557](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L557) |

---


### [propertiesUI](#propertiesui)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.propertiesUI <cp.prop: hs.axuielement; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns the properties `axuielement` for the Inspector. This contains the rows of property values.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 151](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L151) |

---


### [share](#share)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.share <cp.apple.finalcutpro.inspector.ShareInspector>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The [ShareInspector](cp.apple.finalcutpro.inspector.ShareInspector.md).                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 622](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L622) |

---


### [text](#text)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.text <cp.apple.finalcutpro.inspector.TextInspector`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The [TextzInspector](cp.apple.finalcutpro.inspector.TextzInspector.md).                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 570](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L570) |

---


### [title](#title)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.title <cp.apple.finalcutpro.inspector.TitleInspector>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The [TitleInspector](cp.apple.finalcutpro.inspector.TitleInspector.md).                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 583](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L583) |

---


### [topBarUI](#topbarui)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.topBarUI <cp.prop: hs.axuielement; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns the "top bar" `axuielement` for the Inspector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 118](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L118) |

---


### [transition](#transition)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.transition <cp.apple.finalcutpro.inspector.TransitionInspector>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The [TransitionInspector](cp.apple.finalcutpro.inspector.TransitionInspector.md).                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 596](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L596) |

---


### [video](#video)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector.video <cp.apple.finalcutpro.inspector.VideoInspector>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The [VideoInspector](cp.apple.finalcutpro.inspector.VideoInspector.md).                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 524](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L524) |

---

#### Methods


### [doFindTabButton](#dofindtabbutton)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector:doFindTabButton(type) -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Finds the named Inspector tab button, or sends an error if the type is unsupported.                                                                     |
| **Parameters**                              | <ul><li>type - the type of the button to return. (e.g. "Video")</li></ul> |
| **Returns**                                 | <ul><li>A [Statement](cp.rx.go.Statement.md) to execute.</li></ul>          |
| **Notes**                                   | <ul><li>Valid strings for `type` are as follows:</li><li>  Audio</li><li>  Color</li><li>  Effect</li><li>  Generator</li><li>  Info</li><li>  Share</li><li>  Text</li><li>  Title</li><li>  Transition</li><li>  Video</li><li>Not all button types are available in all contexts.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 368](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L368) |

---


### [doHide](#dohide)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector:doHide() -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that attempts to hide the `Inspector`.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `Statement`, resolving to `true` if the Inspector was hidden successfully, or an error if not.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 303](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L303) |

---


### [doSelectTab](#doselecttab)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector:doSelectTab(title) -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A Statement that selects the specified tab title.                                                                     |
| **Parameters**                              | <ul><li>title     - The title of the tab to select.</li></ul> |
| **Returns**                                 | <ul><li>The [Statement](cp.rx.go.Statement.md)</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 408](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L408) |

---


### [doShow](#doshow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector:doShow() -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that attempts to show the `Inspector`.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `Statement`, resolving to `true` if the Inspector was shown successfully, or an error if not.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 268](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L268) |

---


### [hide](#hide)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector:hide() -> Inspector`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Hides the inspector.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `Inspector` instance.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 285](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L285) |

---


### [selectedTab](#selectedtab)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector:selectedTab() -> string or nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the name of the selected inspector tab otherwise `nil`.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A string of the selected tab, otherwise `nil` if the Inspector is closed or an error occurred.</li></ul>          |
| **Notes**                                   | <ul><li>The tab strings can be:</li><li>  Audio</li><li>  Color</li><li>  Effect</li><li>  Generator</li><li>  Info</li><li>  Share</li><li>  Text</li><li>  Title</li><li>  Transition</li><li>  Video</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 475](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L475) |

---


### [selectTab](#selecttab)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector:selectTab(tab) -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Selects a tab in the inspector.                                                                     |
| **Parameters**                              | <ul><li>tab - A string from the `cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS` table</li></ul> |
| **Returns**                                 | <ul><li>A string of the selected tab, otherwise `nil` if an error occurred.</li></ul>          |
| **Notes**                                   | <ul><li>This method will open the Inspector if it's closed, and leave it open.</li><li>Valid strings for `value` are as follows:</li><li>  Audio</li><li>  Color</li><li>  Effect</li><li>  Generator</li><li>  Info</li><li>  Share</li><li>  Text</li><li>  Title</li><li>  Transition</li><li>  Video</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 319](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L319) |

---


### [show](#show)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector:show([tab]) -> Inspector`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Shows the inspector.                                                                     |
| **Parameters**                              | <ul><li>[tab] - A string from the `cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS` table</li></ul> |
| **Returns**                                 | <ul><li>The `Inspector` instance.</li></ul>          |
| **Notes**                                   | <ul><li>Valid strings for `value` are as follows:</li><li>  Audio</li><li>  Color</li><li>  Effect</li><li>  Generator</li><li>  Info</li><li>  Share</li><li>  Text</li><li>  Title</li><li>  Transition</li><li>  Video</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 225](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L225) |

---


### [tabAvailable](#tabavailable)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.Inspector:tabAvailable(tab) -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Checks to see if a tab is currently available in the Inspector.                                                                     |
| **Parameters**                              | <ul><li>tab - A string from the `cp.apple.finalcutpro.inspector.Inspector.INSPECTOR_TABS` table</li></ul> |
| **Returns**                                 | <ul><li>`true` if available otherwise `false`.</li></ul>          |
| **Notes**                                   | <ul><li>Valid strings for `value` are as follows:</li><li>  Audio</li><li>  Color</li><li>  Effect</li><li>  Generator</li><li>  Info</li><li>  Share</li><li>  Text</li><li>  Title</li><li>  Transition</li><li>  Video</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua line 430](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/Inspector.lua#L430) |

---

