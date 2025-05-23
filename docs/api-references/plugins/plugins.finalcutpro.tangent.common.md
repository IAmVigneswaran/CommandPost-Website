# plugins.finalcutpro.tangent.common

Common Final Cut Pro functions for Tangent

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [buttonParameter](#buttonparameter)
 * [checkboxParameter](#checkboxparameter)
 * [checkboxParameterByIndex](#checkboxparameterbyindex)
 * [checkboxSliderParameter](#checkboxsliderparameter)
 * [commandParameter](#commandparameter)
 * [doShowParameter](#doshowparameter)
 * [dynamicPopupSliderParameter](#dynamicpopupsliderparameter)
 * [functionParameter](#functionparameter)
 * [menuParameter](#menuparameter)
 * [popupParameter](#popupparameter)
 * [popupParameters](#popupparameters)
 * [popupSliderParameter](#popupsliderparameter)
 * [radioButtonParameter](#radiobuttonparameter)
 * [shortcutParameter](#shortcutparameter)
 * [sliderParameter](#sliderparameter)
 * [volumeSliderParameter](#volumesliderparameter)
 * [xyParameter](#xyparameter)


---

## API Documentation

#### Functions


### [buttonParameter](#buttonparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.buttonParameter(group, param, id, label) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Button Parameter for the Tangent                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 591](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L591) |

---


### [checkboxParameter](#checkboxparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.checkboxParameter(group, param, id, label) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Checkbox Parameter for the Tangent                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 313](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L313) |

---


### [checkboxParameterByIndex](#checkboxparameterbyindex)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.checkboxParameterByIndex(group, section, nextSection, id, label, index) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new AXCheckBox object for the Tangent.                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>section - The section as it appears in the FCPX Inspector.</li><li>nextSection - The next section as it appears in the FCPX Inspector.</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li><li>index - The index of the checkbox in the section.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 622](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L622) |

---


### [checkboxSliderParameter](#checkboxsliderparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.checkboxSliderParameter(group, id, label, options, resetIndex) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Popup Slider parameter for the Tangent                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li><li>options - A table of options. The key for each option should be a number ID (in the order it appears in the UI), and the value should be another table with keys for `flexoID` and `i18n` values.</li><li>resetIndex - An index of which item to use when "reset" is triggered.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 341](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L341) |

---


### [commandParameter](#commandparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.commandParameter(group, id, commandID) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Command Parameter for the Tangent                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>id - The Tangent ID.</li><li>commandID - The command ID.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 506](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L506) |

---


### [doShowParameter](#doshowparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.doShowParameter(group, param, id, label) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new `DoShow` Parameter for the Tangent                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 482](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L482) |

---


### [dynamicPopupSliderParameter](#dynamicpopupsliderparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.dynamicPopupSliderParameter(group, param, id, label, defaultValue) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Popup Slider parameter for the Tangent                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li><li>defaultValue - The default value to use when the reset button is pressed.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 67](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L67) |

---


### [functionParameter](#functionparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.functionParameter(group, id, label, fn) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Function Parameter for the Tangent.                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li><li>path - The list of menu items you'd like to activate as a table.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 571](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L571) |

---


### [menuParameter](#menuparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.menuParameter(group, id, label, path) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Final Cut Pro Menu Parameter for the Tangent.                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li><li>path - The list of menu items you'd like to activate as a table.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 549](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L549) |

---


### [popupParameter](#popupparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.popupParameter(group, param, id, value, label) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Popup Parameter for the Tangent                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>param - The Parameter.</li><li>id - The Tangent ID.</li><li>value - The value to select as a string.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 41](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L41) |

---


### [popupParameters](#popupparameters)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.popupParameters(group, param, id, options) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Popup Parameter for the Tangent                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>options - A table of options. The key for each option should be a number ID (in the order it appears in the UI), and the value should be another table with keys for `flexoID` and `i18n` values.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 289](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L289) |

---


### [popupSliderParameter](#popupsliderparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.popupSliderParameter(group, param, id, label, options, resetIndex) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Popup Slider parameter for the Tangent                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li><li>options - A table of options. The key for each option should be a number ID (in the order it appears in the UI), and the value should be another table with keys for `flexoID` and `i18n` values.</li><li>resetIndex - An index of which item to use when "reset" is triggered.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 164](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L164) |

---


### [radioButtonParameter](#radiobuttonparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.radioButtonParameter(group, param, id, label) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Checkbox Parameter for the Tangent                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>param - The Parameter</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 430](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L430) |

---


### [shortcutParameter](#shortcutparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.shortcutParameter(group, id, label, shortcutID) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Final Cut Pro Shortcut Parameter for the Tangent.                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group.</li><li>id - The Tangent ID.</li><li>label - The label to be used by the Tangent. This can either be an i18n ID or a plain string.</li><li>shortcutID - The shortcut ID.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 527](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L527) |

---


### [sliderParameter](#sliderparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.sliderParameter(group, param, id, minValue, maxValue, stepSize, default, label, optionalParamA, optionalParamB) -> number, parameter`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Slider Parameter                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group</li><li>param - The Parameter</li><li>id - The Tangent ID</li><li>minValue - The minimum value</li><li>maxValue - The maximum value</li><li>stepSize - The step size</li><li>default - The default value</li><li>label - An optional label as an i18n ID or plain string. If no label is supplied the `param` label will be used.</li><li>optionalParamA - An optional parameter. Useful if you need to link parameters.</li><li>optionalParamB - An optional parameter. Useful if you need to link parameters.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li><li>The parameters value</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 752](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L752) |

---


### [volumeSliderParameter](#volumesliderparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.volumeSliderParameter(group, param, id, minValue, maxValue, stepSize, default, label) -> number, parameter`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new Volume Slider Parameter                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group</li><li>param - The Parameter</li><li>id - The Tangent ID</li><li>minValue - The minimum value</li><li>maxValue - The maximum value</li><li>stepSize - The step size</li><li>default - The default value</li><li>label - An optional label as an i18n ID or plain string. If no label is supplied the `param` label will be used.</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li><li>The parameters value</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 825](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L825) |

---


### [xyParameter](#xyparameter)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.tangent.common.xyParameter(group, param, id, minValue, maxValue, stepSize) -> number`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sets up a new XY Parameter                                                                     |
| **Parameters**                              | <ul><li>group - The Tangent Group</li><li>param - The Parameter</li><li>id - The Tangent ID</li><li>minValue - The minimum value</li><li>maxValue - The maximum value</li><li>stepSize - The step size</li></ul> |
| **Returns**                                 | <ul><li>An updated ID</li><li>The `x` parameter value</li><li>The `y` parameter value</li><li>The xy binding</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/tangent/common.lua line 668](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/tangent/common.lua#L668) |

---

