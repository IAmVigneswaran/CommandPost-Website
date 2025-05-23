# plugins.finalcutpro.workflowextension

Workflow Extension Helper

Commands that can be SENT to the Workflow Extension:

 PING           - Send a ping
 INCR f         - Increment by Frame        (where f is number of frames)
 DECR f         - Decrement by Frame        (where f is number of frames)
 GOTO s         - Goto Timeline Position    (where s is number of seconds)


 Commands that can be RECEIVED from the Workflow Extension:

 DONE           - Connection successful
 DEAD           - Server is shutting down
 PONG           - Recieve a pong
 PLHD s         - The playhead time has changed                (where s is playhead position in seconds)

 SEQC sequenceName || startTime || duration || frameDuration || container || timecodeFormat || objectType
    - The active sequence has changed
      (sequenceName is a string)
      (startTime in seconds)
      (duration in seconds)
      (frameDuration in seconds)
      (container as a string)
      (timecodeFormat as a string: DropFrame, NonDropFrame, Unspecified or Unknown)
      (objectType as a string: Event, Library, Project, Sequence or Unknown)

 RNGC startTime || duration
    - The active sequence time range has changed
      (startTime in seconds)
      (duration in seconds)

---

## API Overview
**Variables** - _Configurable values_
 * [connected](#connected)
 * [lastPlayheadPosition](#lastplayheadposition)
 * [skimmingRestoreTimer](#skimmingrestoretimer)
 * [wasSkimmingEnabled](#wasskimmingenabled)

**Functions** - _API calls offered directly by the extension_
 * [callback](#callback)
 * [connect](#connect)
 * [connectionCallback](#connectioncallback)
 * [decrementPlayhead](#decrementplayhead)
 * [disconnect](#disconnect)
 * [forcefullyInstall](#forcefullyinstall)
 * [incrementPlayhead](#incrementplayhead)
 * [movePlayheadToSeconds](#moveplayheadtoseconds)
 * [ping](#ping)
 * [repositionWorkflowExtension](#repositionworkflowextension)
 * [sendCommand](#sendcommand)
 * [setupActions](#setupactions)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [hasWorkflowExtensionBeenAddedVersion](#hasworkflowextensionbeenaddedversion)
 * [hasWorkflowExtensionBeenMovedVersion](#hasworkflowextensionbeenmovedversion)


---

## API Documentation

#### Variables


### [connected](#connected)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.connected -> boolean`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Is CommandPost connecting to the Workflow Extension?                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 97](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L97) |

---


### [lastPlayheadPosition](#lastplayheadposition)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.lastPlayheadPosition -> string`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | The last playhead position.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 107](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L107) |

---


### [skimmingRestoreTimer](#skimmingrestoretimer)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.skimmingRestoreTimer -> hs.timer.delayed`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Delayed Timer to Restore the Skimming Feature (if required)                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 371](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L371) |

---


### [wasSkimmingEnabled](#wasskimmingenabled)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.wasSkimmingEnabled -> boolean`                                                                    |
| **Type**                                    | Variable                                                                     |
| **Description**                             | Was the Skimming Feature enabled?                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 366](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L366) |

---

#### Functions


### [callback](#callback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.callback() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Triggers when the Socket receives data.                                                                     |
| **Parameters**                              | <ul><li>data - The incoming data.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 229](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L229) |

---


### [connect](#connect)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.connect() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Connect to the Workflow Extension Socket Server.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 257](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L257) |

---


### [connectionCallback](#connectioncallback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.connectionCallback() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Triggers when the Socket makes a connection.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 158](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L158) |

---


### [decrementPlayhead](#decrementplayhead)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.decrementPlayhead(frames) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Decrements the Final Cut Pro playhead via the Workflow Extension                                                                     |
| **Parameters**                              | <ul><li>frames - The amount of frames to increment by</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 424](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L424) |

---


### [disconnect](#disconnect)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.disconnect() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Disconnects from the Workflow Extension Socket Server.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 295](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L295) |

---


### [forcefullyInstall](#forcefullyinstall)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.forcefullyInstall() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Forcefully installs the Workflow Extension.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 615](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L615) |

---


### [incrementPlayhead](#incrementplayhead)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.incrementPlayhead(frames) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Increments the Final Cut Pro playhead via the Workflow Extension                                                                     |
| **Parameters**                              | <ul><li>frames - The amount of frames to increment by</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 409](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L409) |

---


### [movePlayheadToSeconds](#moveplayheadtoseconds)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.movePlayheadToSeconds(seconds) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Moves the Final Cut Pro playhead via the Workflow Extension                                                                     |
| **Parameters**                              | <ul><li>seconds - The value you want the timeline playhead to move to in seconds</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 439](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L439) |

---


### [ping](#ping)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.ping() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sends a ping to the Workflow Extension                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 452](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L452) |

---


### [repositionWorkflowExtension](#repositionworkflowextension)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.repositionWorkflowExtension() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Repositions the Workflow Extension.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 527](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L527) |

---


### [sendCommand](#sendcommand)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.sendCommand(command) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sends a command to the Workflow                                                                     |
| **Parameters**                              | <ul><li>command - The command as a string</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 331](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L331) |

---


### [setupActions](#setupactions)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.setupActions() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Setup the Workflow Extension Actions                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 466](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L466) |

---

#### Fields


### [hasWorkflowExtensionBeenAddedVersion](#hasworkflowextensionbeenaddedversion)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.hasWorkflowExtensionBeenAddedVersion -> cp.prop`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns the CommandPost Version String for the last time the Workflow Extension was added.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 82](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L82) |

---


### [hasWorkflowExtensionBeenMovedVersion](#hasworkflowextensionbeenmovedversion)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.workflowextension.hasWorkflowExtensionBeenMovedVersion -> cp.prop`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Returns the CommandPost Version String for the last time the Workflow Extension was moved.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/finalcutpro/workflowextension/init.lua line 87](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/workflowextension/init.lua#L87) |

---

