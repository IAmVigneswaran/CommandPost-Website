# cp.apple.finalcutpro.inspector.color.ColorWheels

Color Wheels Module.

Extends [Element](cp.ui.Element.md)

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [matches](#matches)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [ColorWheels](#colorwheels)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [blackPoint](#blackpoint)
 * [brightness](#brightness)
 * [contentUI](#contentui)
 * [contrast](#contrast)
 * [exposure](#exposure)
 * [highlights](#highlights)
 * [highlightsTint](#highlightstint)
 * [highlightsWarmth](#highlightswarmth)
 * [hue](#hue)
 * [hueRow](#huerow)
 * [hueSlider](#hueslider)
 * [hueTextField](#huetextfield)
 * [master](#master)
 * [maxValue](#maxvalue)
 * [midtones](#midtones)
 * [midtonesTint](#midtonestint)
 * [midtonesWarmth](#midtoneswarmth)
 * [minValue](#minvalue)
 * [mix](#mix)
 * [mixRow](#mixrow)
 * [mixSlider](#mixslider)
 * [mixTextField](#mixtextfield)
 * [saturation](#saturation)
 * [shadows](#shadows)
 * [shadowsTint](#shadowstint)
 * [shadowsWarmth](#shadowswarmth)
 * [temperature](#temperature)
 * [temperatureRow](#temperaturerow)
 * [temperatureSlider](#temperatureslider)
 * [temperatureTextField](#temperaturetextfield)
 * [tint](#tint)
 * [tintRow](#tintrow)
 * [tintSlider](#tintslider)
 * [tintTextField](#tinttextfield)
 * [value](#value)
 * [viewingAllWheels](#viewingallwheels)
 * [viewMode](#viewmode)
 * [wheelType](#wheeltype)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [doShow](#doshow)
 * [show](#show)


---

## API Documentation

#### Functions


### [matches](#matches)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.matches(element)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks if the specified element is the Color Wheels element.                                                                     |
| **Parameters**                              | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                 | <ul><li>`true` if the element is the Color Wheels.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 36](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L36) |

---

#### Constructors


### [ColorWheels](#colorwheels)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels(parent) -> ColorInspector`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new ColorWheels object                                                                     |
| **Parameters**                              | <ul><li>`parent`     - The parent</li></ul> |
| **Returns**                                 | <ul><li>A new `ColorInspector` object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 54](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L54) |

---

#### Fields


### [blackPoint](#blackpoint)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.blackPoint <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 504](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L504) |

---


### [brightness](#brightness)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.brightness <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 375](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L375) |

---


### [contentUI](#contentui)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.contentUI <cp.prop: hs.axuielement; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `axuielement` representing the content element of the ColorWheels corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 93](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L93) |

---


### [contrast](#contrast)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.contrast <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 332](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L332) |

---


### [exposure](#exposure)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.exposure <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 289](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L289) |

---


### [highlights](#highlights)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.highlights <ColorWheel>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `ColorWheel` that allows control of the 'highlights' color settings.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 249](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L249) |

---


### [highlightsTint](#highlightstint)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.highlightsTint <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 633](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L633) |

---


### [highlightsWarmth](#highlightswarmth)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.highlightsWarmth <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 590](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L590) |

---


### [hue](#hue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.hue <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The hue for the corrector. A number from `0` to `360`.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 154](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L154) |

---


### [hueRow](#huerow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.hueRow <cp.ui.PropertyRow>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `PropertyRow` that provides access to the 'Hue' parameter, and `axuielement`                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 359](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L359) |

---


### [hueSlider](#hueslider)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.hueSlider <cp.ui.Slider>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns a `Slider` that provides access to the 'Hue' slider.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 367](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L367) |

---


### [hueTextField](#huetextfield)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.hueTextField <cp.ui.TextField>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `TextField` that provides access to the 'Hue' slider.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 379](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L379) |

---


### [master](#master)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.master <ColorWheel>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `ColorWheel` that allows control of the 'master' color settings.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 228](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L228) |

---


### [maxValue](#maxvalue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.maxValue <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The maximum value of the indicator as a number.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 119](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L119) |

---


### [midtones](#midtones)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.midtones <ColorWheel>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `ColorWheel` that allows control of the 'midtones' color settings.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 242](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L242) |

---


### [midtonesTint](#midtonestint)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.midtonesTint <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 719](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L719) |

---


### [midtonesWarmth](#midtoneswarmth)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.midtonesWarmth <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 676](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L676) |

---


### [minValue](#minvalue)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.minValue <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The minimum value of the indicator as a number.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 110](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L110) |

---


### [mix](#mix)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.mix <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The mix amount for this corrector. A number ranging from `0` to `1`.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 133](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L133) |

---


### [mixRow](#mixrow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.mixRow <cp.ui.PropertyRow>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `PropertyRow` that provides access to the 'Mix' parameter, and `axuielement`                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 260](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L260) |

---


### [mixSlider](#mixslider)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.mixSlider <cp.ui.Slider>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `Slider` that provides access to the 'Mix' slider.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 268](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L268) |

---


### [mixTextField](#mixtextfield)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.mixTextField <cp.ui.TextField>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `TextField` that provides access to the 'Mix' slider.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 280](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L280) |

---


### [saturation](#saturation)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.saturation <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 418](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L418) |

---


### [shadows](#shadows)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.shadows <ColorWheel>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `ColorWheel` that allows control of the 'shadows' color settings.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 235](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L235) |

---


### [shadowsTint](#shadowstint)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.shadowsTint <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 805](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L805) |

---


### [shadowsWarmth](#shadowswarmth)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.shadowsWarmth <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The amount for this corrector.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua line 762](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorAdjustments.lua#L762) |

---


### [temperature](#temperature)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.temperature <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The color temperature for this corrector. A number from 2500 to 10000.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 140](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L140) |

---


### [temperatureRow](#temperaturerow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.temperatureRow <cp.ui.PropertyRow>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `PropertyRow` that provides access to the 'Temperatures' parameter, and `axuielement`                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 293](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L293) |

---


### [temperatureSlider](#temperatureslider)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.temperatureSlider <cp.ui.Slider>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `Slider` that provides access to the 'Temperatures' slider.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 301](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L301) |

---


### [temperatureTextField](#temperaturetextfield)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.temperatureTextField <cp.ui.TextField>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `TextField` that provides access to the 'Temperature' slider.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 313](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L313) |

---


### [tint](#tint)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.tint <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The tint for the corrector. A number from `-50` to `50`.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 147](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L147) |

---


### [tintRow](#tintrow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.tintRow <cp.ui.PropertyRow>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `PropertyRow` that provides access to the 'Tint' parameter, and `axuielement`                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 326](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L326) |

---


### [tintSlider](#tintslider)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.tintSlider <cp.ui.Slider>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns a `Slider` that provides access to the 'Tint' slider.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 334](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L334) |

---


### [tintTextField](#tinttextfield)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.tintTextField <cp.ui.TextField>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A `TextField` that provides access to the 'Tint' slider.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 346](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L346) |

---


### [value](#value)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.value <cp.prop: number>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The value of the value indicator as a number.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua line 63](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ValueIndicator.lua#L63) |

---


### [viewingAllWheels](#viewingallwheels)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.viewingAllWheels <cp.prop: boolean>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Reports and modifies whether the ColorWheels corrector is showing "All Wheels" (`true`) or "Single Wheels" (`false`).                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 106](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L106) |

---


### [viewMode](#viewmode)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.viewMode <cp.ui.MenuButton>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The [MenuButton](cp.ui.MenuButton.md) for the View Mode.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 198](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L198) |

---


### [wheelType](#wheeltype)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels.wheelType <cp.ui.RadioGroup>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `RadioGroup` that allows selection of the wheel type. Only available when                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 211](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L211) |

---

#### Methods


### [doShow](#doshow)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels:doShow() -> cs.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that shows the Color Board within the Color Inspector.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The `Statement`, resolving to `true` if successfully shown.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 183](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L183) |

---


### [show](#show)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.color.ColorWheels:show() -> boolean`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Show's the Color Board within the Color Inspector.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>ColorWheels object</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua line 167](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/apple/finalcutpro/inspector/color/ColorWheels.lua#L167) |

---

