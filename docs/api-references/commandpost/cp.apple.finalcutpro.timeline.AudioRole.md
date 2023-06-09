# cp.apple.finalcutpro.timeline.AudioRole

 *Extends [Role](cp.apple.finalcutpro.timeline.Role.md)*

A [Role](cp.apple.finalcutpro.timeline.Role.md) representing Audio.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [matches](#matches)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [AudioRole](#audiorole)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [focusedInTimeline](#focusedintimeline)
 * [subroleLanes](#subrolelanes)
 * [subrolesExpanded](#subrolesexpanded)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [doFocusInTimeline](#dofocusintimeline)
 * [doHideSubroleLanes](#dohidesubrolelanes)
 * [doShowSubroleLanes](#doshowsubrolelanes)
 * [doUnfocusInTimeline](#dounfocusintimeline)


---

## API Documentation

### Functions


### [matches](#matches)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.timeline.AudioRole.matches(element) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks if the element is a "Audio" Role.                                                                     |
| **Parameters**                              | <ul><li>element - An element to check</li></ul> |
| **Returns**                                 | <ul><li>A boolean</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---
### Constructors


### [AudioRole](#audiorole)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.timeline.AudioRole(parent, uiFinder)`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new instance with the specified `parent` and `uiFinder`.                                                                     |
| **Parameters**                              | <ul><li>parent - the parent `Element`.</li><li>uiFinder - a `function` or `cp.prop` containing the `axuielement`</li></ul> |
| **Returns**                                 | <ul><li>The new `Row`.</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---
### Fields


### [focusedInTimeline](#focusedintimeline)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.timeline.AudioRole.focusedInTimeline <cp.ui.CheckBox>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A [CheckBox](cp.ui.CheckBox.md) that toggles this role is larger than the other audio roles on the timeline.                                                                     |

---

### [subroleLanes](#subrolelanes)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.timeline.AudioRole.subroleLanes <cp.ui.CheckButton>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A [CheckButton](cp.ui.CheckButton.md) that toggles whether the subroles are visible in the [Timeline](cp.apple.finalcutpro.timeline.Timeline.md).                                                                     |

---

### [subrolesExpanded](#subrolesexpanded)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.timeline.AudioRole.subrolesExpanded <cp.ui.CheckButton>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | A [CheckButton](cp.ui.CheckButton.md) that toggles whether the roles are visible in the Index.                                                                     |
| **Notes**                                   | <ul><li>Unlike the [VideoRole](cp.finalcutpro.apple.timeline.VideoRole.md) and [CaptionsRole](cp.apple.finalcutpro.timeline.CaptionsRole.md), this is a [CheckBox](cp.ui.CheckBox.md) and is always visible.</li></ul>                |

---
### Methods


### [doFocusInTimeline](#dofocusintimeline)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.timeline.AudioRole:doFocusInTimeline() -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that will attempt to focus on this audio role in the timeline.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A Statement</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [doHideSubroleLanes](#dohidesubrolelanes)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.timeline.AudioRole:doHideSubroleLanes() -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that will attempt to hide the subrole lanes on this audio role in the timeline.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A Statement</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [doShowSubroleLanes](#doshowsubrolelanes)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.timeline.AudioRole:doShowSubroleLanes() -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that will attempt to show the subrole lanes on this audio role in the timeline.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A Statement</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---

### [doUnfocusInTimeline](#dounfocusintimeline)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.apple.finalcutpro.timeline.AudioRole:doUnfocusInTimeline() -> cp.rx.go.Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | A [Statement](cp.rx.go.Statement.md) that will attempt to unfocus on this audio role in the timeline.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>A Statement</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---