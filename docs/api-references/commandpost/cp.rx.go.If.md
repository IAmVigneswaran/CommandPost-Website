# cp.rx.go.If

A `Statement` that will check if a `resolvable` matches a predicate, then executes other `resolvables`.

---

## Submodules
 * [cp.rx.go.If.Are](cp.rx.go.If.Are.md)
 * [cp.rx.go.If.AreNot](cp.rx.go.If.AreNot.md)
 * [cp.rx.go.If.Is](cp.rx.go.If.Is.md)
 * [cp.rx.go.If.IsNot](cp.rx.go.If.IsNot.md)
 * [cp.rx.go.If.Matches](cp.rx.go.If.Matches.md)
 * [cp.rx.go.If.Then](cp.rx.go.If.Then.md)

---

## API Overview
**Constructors** - _API calls which return an object, typically one that offers API methods_
 * [If](#if)

**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [Are](#are)
 * [AreNot](#arenot)
 * [Is](#is)
 * [IsNot](#isnot)
 * [Matches](#matches)
 * [Then](#then)


---

## API Documentation

#### Constructors


### [If](#if)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.If(value) -> If`                                                                    |
| **Type**                                    | Constructor                                                                     |
| **Description**                             | Creates a new `If` `Statement` which will check the first result of `value`.                                                                     |
| **Parameters**                              | <ul><li>value  - a `resolvable` value that will be checked.</li></ul> |
| **Returns**                                 | <ul><li>The `Statement` instance which will check if the `resolvable` matches the requirement.</li></ul>          |
| **Notes**                                   | <ul><li>By default, it will check if the value is `truthy` - not `nil` and not `false`.</li><li>Other checks can be specified via the `If:Is/IsNot/Matches` methods.</li><li>If the check passes, the `If:Then(...)` method is processed. If not, the `Otherwise` method</li><li>can specify other `resolvables` to execute instead.</li><li></li><li>Example:</li><li></li><li>```lua</li><li>If(someObservable):Is(true):Then(</li><li>    function() ... end</li><li>):Otherwise(</li><li>    function() ... end</li><li>)</li><li>```</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/If.lua line 46](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/If.lua#L46) |

---

#### Methods


### [Are](#are)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.If:Are(value) -> If.Are`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Specifies the value to check.                                                                     |
| **Parameters**                              | <ul><li>value  - The value to wait for.</li></ul> |
| **Returns**                                 | <ul><li>The [Are](cp.rx.go.If.Are.md) [Statement.Modifier](cp.rx.go.Statement.Modifier.md).</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/If.lua line 233](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/If.lua#L233) |

---


### [AreNot](#arenot)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.If:AreNot(value) -> If.AreNot`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Specifies the value to check.                                                                     |
| **Parameters**                              | <ul><li>value  - The value to not match.</li></ul> |
| **Returns**                                 | <ul><li>The [AreNot](cp.rx.go.If.AreNot.md) [Statement.Modifier](cp.rx.go.Statement.Modifier.md).</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/If.lua line 288](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/If.lua#L288) |

---


### [Is](#is)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.If:Is(value) -> If.Is`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Specifies the value to check.                                                                     |
| **Parameters**                              | <ul><li>value  - The value to check for.</li></ul> |
| **Returns**                                 | <ul><li>The [Is](cp.rx.go.If.Is.md) [Statement.Modifier](cp.rx.go.Statement.Modifier.md).</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/If.lua line 218](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/If.lua#L218) |

---


### [IsNot](#isnot)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.If:IsNot(value) -> If.IsNot`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Specifies the value to not match.                                                                     |
| **Parameters**                              | <ul><li>value  - The value to check for.</li></ul> |
| **Returns**                                 | <ul><li>The [IsNot](cp.rx.go.If.IsNot.md) [Statement.Modifier](cp.rx.go.Statement.Modifier.md).</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/If.lua line 274](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/If.lua#L274) |

---


### [Matches](#matches)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.If:Matches(predicate) -> If.Matches`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Specifies the predicate function that will check the `value` results.                                                                     |
| **Parameters**                              | <ul><li>predicate  - The function that will get called to determine if it has been found.</li></ul> |
| **Returns**                                 | <ul><li>The [Matches](cp.rx.go.If.Matches.md) [Statement.Modifier](cp.rx.go.Statement.Modifier.md).</li></ul>          |
| **Notes**                                   | <ul><li>Example:</li><li>```lua</li><li>If(someObservable):Matches(function(value) return value % 2 == 0 end):Then(doSomething())</li><li>```</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/If.lua line 329](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/If.lua#L329) |

---


### [Then](#then)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.go.If:Then(...) -> If.Then`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Call this to define what will happen if value resolves successfully.                                                                     |
| **Parameters**                              | <ul><li>...  - The list of `resolveable` values to process for the successful `If` result.</li></ul> |
| **Returns**                                 | <ul><li>The `Then` `Statement.Modifier`.</li></ul>          |
| **Notes**                                   | <ul><li>The parameters can be any `resolvable` type.</li><li></li><li>For example:</li><li>```lua</li><li>If(anObservable)</li><li>:Then(function(aResult)</li><li>    doSomethingWith(aResult, anotherResult)</li><li>    return true</li><li>end)</li><li>```</li></ul> |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/rx/go/If.lua line 123](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/rx/go/If.lua#L123) |

---

