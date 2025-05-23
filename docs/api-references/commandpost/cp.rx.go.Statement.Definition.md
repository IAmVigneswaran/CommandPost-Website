# cp.rx.go.Statement.Definition

A [Statement](cp.rx.go.Statement.md) is defined before being executable.
A definition is initiated with the [Statement:modifier(...)](cp.rx.go.Statement.md#modifer) method.

---

## API Overview
**Functions** - _API calls offered directly by the extension_
 * [is](#is)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [define](#define)
 * [onInit](#oninit)
 * [onObservable](#onobservable)


---

## API Documentation

#### Functions


### [is](#is)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.Statement.Definition.is(thing) -> boolean`                                                                    |
| **Type**                                    | Function                                                                     |
| **Description**                             | Checks if the `thing` is an instance of `Statement.Definition`.                                                                     |
| **Parameters**                              | <ul><li>thing    - The thing to check.</li></ul> |
| **Returns**                                 | <ul><li>`true` if the thing is a `Statement.Definition`.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/Statement.lua line 225](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/Statement.lua#L225) |

---

#### Methods


### [define](#define)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.Statement.Definition:define() -> Statement`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Completes the definition of the [Statement](cp.rx.go.Statement.md).                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The new [Statement](cp.rx.go.Statement.md).</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/Statement.lua line 292](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/Statement.lua#L292) |

---


### [onInit](#oninit)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.Statement.Definition:onInit(initFn) -> Statement.Definition`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Defines the function which will be called to initialise the context.                                                                     |
| **Parameters**                              | <ul><li>initFn       - The init function.</li></ul> |
| **Returns**                                 | <ul><li>The Statement Definition</li></ul>          |
| **Notes**                                   | <ul><li>* The function will be passed the `context` table as the first parameter,</li><li>  and any other parameters passed to the statement follow.</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/Statement.lua line 243](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/Statement.lua#L243) |

---


### [onObservable](#onobservable)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.Statement.Definition:onObservable(observableFn) -> Statement.Definition`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Defines the function which will be called to create the [Observable](cp.rx.Observable.md) for the [Statement](cp.rx.go.Statement.md). The function will be passed the `context` table and must return an `Observable`.                                                                     |
| **Parameters**                              | <ul><li>observableFn     - The observable creator function.</li></ul> |
| **Returns**                                 | <ul><li>The `Statement.Definition`</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/Statement.lua line 262](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/Statement.lua#L262) |

---

