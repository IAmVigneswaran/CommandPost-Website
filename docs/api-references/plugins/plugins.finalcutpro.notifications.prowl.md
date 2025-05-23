# plugins.finalcutpro.notifications.prowl

Prowl Notifications Plugin.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [init](#init)
 * [sendNotification](#sendnotification)
 * [update](#update)
 * [validateAPIKey](#validateapikey)

**Fields** - _Variables which can only be accessed from an object returned by a constructor_
 * [apiKey](#apikey)
 * [apiValidated](#apivalidated)
 * [enabled](#enabled)


---

## API Documentation

#### Functions


### [init](#init)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.notifications.prowl.init() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Initialises the plugin.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/notifications/prowl.lua line 89](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/notifications/prowl.lua#L89) |

---


### [sendNotification](#sendnotification)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.notifications.prowl.sendNotification(message, [title]) -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Sends a notification.                                                                     |
| **Parameters**                              | <ul><li>message - The message you want to send as a string.</li><li>[title] - An optional Title for the message as a string.</li></ul> |
| **Returns**                                 | <ul><li>success - `true` if successful otherwise `false`</li><li>errorMessage - a string containing any error messages</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/notifications/prowl.lua line 103](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/notifications/prowl.lua#L103) |

---


### [update](#update)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.notifications.prowl.update() -> none`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Enables or disables Prowl Notifications depending on the user's preferences.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/notifications/prowl.lua line 64](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/notifications/prowl.lua#L64) |

---


### [validateAPIKey](#validateapikey)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.notifications.prowl.validateAPIKey(key) -> success, errorMessage`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Validates a Growl API Key                                                                     |
| **Parameters**                              | <ul><li>key - The API key as string</li></ul> |
| **Returns**                                 | <ul><li>success - `true` if successful otherwise `false`</li><li>errorMessage - a string containing any error messages</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/plugins/finalcutpro/notifications/prowl.lua line 25](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/notifications/prowl.lua#L25) |

---

#### Fields


### [apiKey](#apikey)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.notifications.prowl.apiKey <cp.prop: string>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Prowl API Key                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/finalcutpro/notifications/prowl.lua line 59](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/notifications/prowl.lua#L59) |

---


### [apiValidated](#apivalidated)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.notifications.prowl.apiValidated <cp.prop: boolean>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Whether or not the API key has been validated.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/finalcutpro/notifications/prowl.lua line 20](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/notifications/prowl.lua#L20) |

---


### [enabled](#enabled)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `plugins.finalcutpro.notifications.prowl.enabled <cp.prop: boolean>`                                                                    |
| **Type**                                    | Field                                                                     |
| **Description**                             | Whether or not the plugin has been enabled.                                                                     |
| **Notes**                                   | None |
| **Source**                                  | [src/plugins/finalcutpro/notifications/prowl.lua line 54](https://github.com/CommandPost/CommandPost/blob/develop/src/plugins/finalcutpro/notifications/prowl.lua#L54) |

---

