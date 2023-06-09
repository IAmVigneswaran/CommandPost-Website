# cp.spec.Message

Provides an Message message, which can be thrown via the `error` function.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [is](#is)

**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [Message](#message)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [traceback](#traceback)


---

## API Documentation

### Functions


### [is](#is)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.spec.Message.is(other) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks if the `other` is an instance of the `Message` class.                                                                     |
| **Parameters**                              | <ul><li>other - The object to compare</li></ul> |
| **Returns**                                 | <ul><li>A boolean</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---
### Constructors


### [Message](#message)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.spec.Message(message)`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new Message message.                                                                     |
| **Parameters**                              | <ul><li>message   - the message to send.</li></ul> |
| **Returns**                                 | <ul><li>A new message.</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---
### Methods


### [traceback](#traceback)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.spec.Message:traceback()`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Stores the `debug.traceback` result at the present time. Can be retrieved via `stacktrace`                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

---