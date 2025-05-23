# cp.apple.finalcutpro.prefs.PlaybackPanel

Playback Panel Module.

---

## API Overview
**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [PlaybackPanel](#playbackpanel)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [avOutput](#avoutput)
 * [backgroundRender](#backgroundrender)
 * [backgroundRenderDelay](#backgroundrenderdelay)
 * [createMulticamOptimizedMedia](#createmulticamoptimizedmedia)
 * [playerBackground](#playerbackground)
 * [postRollDuration](#postrollduration)
 * [preRollDuration](#prerollduration)
 * [renderShareGPU](#rendersharegpu)
 * [showHDRAsToneMapped](#showhdrastonemapped)
 * [warnAfterPlaybackOnDiskFrameDrop](#warnafterplaybackondiskframedrop)
 * [warnAfterPlaybackOnVRFrameDrop](#warnafterplaybackonvrframedrop)
 * [warnOnFrameDrop](#warnonframedrop)


---

## API Documentation

#### Constructors


### [PlaybackPanel](#playbackpanel)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel(preferencesDialog) -> PlaybackPanel`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new `PlaybackPanel` instance.                                                                     |
| **Parameters**                              | <ul><li>parent - The parent object.</li></ul> |
| **Returns**                                 | <ul><li>A new `PlaybackPanel` object.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 22](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L22) |

---

#### Fields


### [avOutput](#avoutput)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.avOutput <cp.ui.PopUpButton>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `PopUpButton` for "A/V Output".                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 125](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L125) |

---


### [backgroundRender](#backgroundrender)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.backgroundRender <cp.ui.CheckBox>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `CheckBox` for "Background render".                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 35](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L35) |

---


### [backgroundRenderDelay](#backgroundrenderdelay)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.backgroundRenderDelay <cp.ui.TextField>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `TextField` for "Background render".                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 44](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L44) |

---


### [createMulticamOptimizedMedia](#createmulticamoptimizedmedia)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.createMulticamOptimizedMedia <cp.ui.CheckBox>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `CheckBox` for "Create optimized media for multicam clips".                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 62](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L62) |

---


### [playerBackground](#playerbackground)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.playerBackground <cp.ui.PopUpButton>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `PopUpButton` for "Player Background".                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 116](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L116) |

---


### [postRollDuration](#postrollduration)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.postRollDuration <cp.ui.TextField>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `TextField` for "Post-Roll Duration" in seconds.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 107](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L107) |

---


### [preRollDuration](#prerollduration)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.preRollDuration <cp.ui.TextField>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `TextField` for "Pre-Roll Duration" in seconds.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 98](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L98) |

---


### [renderShareGPU](#rendersharegpu)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.renderShareGPU <cp.ui.PopUpButton>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `PopUpButton` for "Render/Share GPU".                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 53](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L53) |

---


### [showHDRAsToneMapped](#showhdrastonemapped)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.showHDRAsToneMapped <cp.ui.CheckBox>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `CheckBox` for "Show HDR as Tone Mapped".                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 134](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L134) |

---


### [warnAfterPlaybackOnDiskFrameDrop](#warnafterplaybackondiskframedrop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.warnAfterPlaybackOnDiskFrameDrop <cp.ui.CheckBox>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `CheckBox` for "If frames drop due to disk performance, warn after playback".                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 80](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L80) |

---


### [warnAfterPlaybackOnVRFrameDrop](#warnafterplaybackonvrframedrop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.warnAfterPlaybackOnVRFrameDrop <cp.ui.CheckBox>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `CheckBox` for "If frames drop on VR headset, warn after playback".                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 89](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L89) |

---


### [warnOnFrameDrop](#warnonframedrop)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.prefs.PlaybackPanel.warnOnFrameDrop <cp.ui.CheckBox>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `CheckBox` for "If a frame drops, stop playback and warn".                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua line 71](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/prefs/PlaybackPanel.lua#L71) |

---

