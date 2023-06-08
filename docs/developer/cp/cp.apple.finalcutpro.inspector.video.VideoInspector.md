# [docs](index.md) » cp.apple.finalcutpro.inspector.video.VideoInspector
---

Video Inspector Module.

Section Rows (`compositing`, `transform`, etc.) have the following properties:
 * enabled   - (cp.ui.CheckBox) Indicates if the section is enabled.
 * toggle    - (cp.ui.Button) Will toggle the Hide/Show button.
 * reset     - (cp.ui.Button) Will reset the contents of the section.
 * expanded  - (cp.prop <boolean>) Get/sets whether the section is expanded.

Property Rows depend on the type of property:

Menu Property:
 * value     - (cp.ui.PopUpButton) The current value of the property.

Slider Property:
 * value     - (cp.ui.Slider) The current value of the property.

XY Property:
 * x         - (cp.ui.TextField) The current 'X' value.
 * y         - (cp.ui.TextField) The current 'Y' value.

CheckBox Property:
 * value     - (cp.ui.CheckBox) The currently value.

For example:
```lua
local video = fcp.inspector.video
-- Menu Property:
video:compositing():blendMode():value("Subtract")
-- Slider Property:
video:compositing():opacity():value(50.0)
-- XY Property:
video:transform():position():x(-10.0)
-- CheckBox property:
video:stabilization():tripodMode():value(true)
```

You should also be able to show a specific property and it will be revealed:
```lua
video:stabilization():smoothing():show():value(1.5)
```

## API Overview
* Constants - Useful values which cannot be changed
 * [BLEND_MODES](#BLEND_MODES)
 * [CROP_TYPES](#CROP_TYPES)
 * [ROLLING_SHUTTER_AMOUNTS](#ROLLING_SHUTTER_AMOUNTS)
 * [SPATIAL_CONFORM_TYPES](#SPATIAL_CONFORM_TYPES)
 * [STABILIZATION_METHODS](#STABILIZATION_METHODS)
* Functions - API calls offered directly by the extension
 * [matches](#matches)
 * [selectedEffectCheckBox](#selectedEffectCheckBox)
* Constructors - API calls which return an object, typically one that offers API methods
 * [VideoInspector](#VideoInspector)
* Fields - Variables which can only be accessed from an object returned by a constructor
 * [contentUI](#contentUI)
* Methods - API calls which can only be made on an object returned by a constructor
 * [effectCheckBoxes](#effectCheckBoxes)

## API Documentation

### Constants

| [BLEND_MODES](#BLEND_MODES)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.video.VideoInspector.BLEND_MODES -> table`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Blend Modes                                                                     |

| [CROP_TYPES](#CROP_TYPES)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.video.VideoInspector.CROP_TYPES -> table`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Crop Types                                                                     |

| [ROLLING_SHUTTER_AMOUNTS](#ROLLING_SHUTTER_AMOUNTS)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.video.VideoInspector.ROLLING_SHUTTER_AMOUNTS -> table`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Rolling Shutter Amounts                                                                     |

| [SPATIAL_CONFORM_TYPES](#SPATIAL_CONFORM_TYPES)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.video.VideoInspector.SPATIAL_CONFORM_TYPES -> table`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Spatial Conform Types                                                                     |

| [STABILIZATION_METHODS](#STABILIZATION_METHODS)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.video.VideoInspector.STABILIZATION_METHODS -> table`                                                                    |
| **Type**                                    | Constant                                                                     |
| **Description**                             | Stabilisation Methods                                                                     |

### Functions

| [matches](#matches)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.video.VideoInspector.matches(element)`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks if the provided element could be a VideoInspector.                                                                     |
| **Parameters**                              | <ul><li>element   - The element to check</li></ul> |
| **Returns**                                 | <ul><li>`true` if it matches, `false` if not.</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [selectedEffectCheckBox](#selectedEffectCheckBox)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.video.VideoInspector:selectedEffectCheckBox() -> axuielement`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Gets the selected effect checkbox object.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A axuielement object.</li></ul>          |
| **Notes**                                   | <ul></ul>                |

### Constructors

| [VideoInspector](#VideoInspector)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.video.VideoInspector(parent) -> cp.apple.finalcutpro.inspector.video.VideoInspector`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new `VideoInspector` object                                                                     |
| **Parameters**                              | <ul><li>`parent`		- The parent</li></ul> |
| **Returns**                                 | <ul><li>A `VideoInspector` object</li></ul>          |
| **Notes**                                   | <ul></ul>                |

### Fields

| [contentUI](#contentUI)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.video.VideoInspector.contentUI <cp.prop: hs.axuielement; read-only>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | The `axuielement` containing the properties rows, if available.                                                                     |

### Methods

| [effectCheckBoxes](#effectCheckBoxes)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.inspector.video.VideoInspector:effectCheckBoxes() -> table`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Gets a table containing all of the effect checkboxes.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A table.</li></ul>          |
| **Notes**                                   | <ul></ul>                |
