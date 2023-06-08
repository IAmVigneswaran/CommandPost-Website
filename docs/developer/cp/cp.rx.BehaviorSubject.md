# [docs](index.md) » cp.rx.BehaviorSubject
---

A [Subject](cp.rx.Subject.md) that tracks its current value. Provides an accessor to retrieve the most
recent pushed value, and all subscribers immediately receive the latest value.

## API Overview
* Methods - API calls which can only be made on an object returned by a constructor
 * [create](#create)
 * [getValue](#getValue)
 * [onNext](#onNext)
 * [subscribe](#subscribe)

## API Documentation

### Methods

| [create](#create)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.BehaviorSubject.create(...) -> cp.rx.BehaviorSubject`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Creates a new `BehaviorSubject`.                                                                     |
| **Parameters**                              | <ul><li>...     - The initial values.</li></ul> |
| **Returns**                                 | <ul><li>The new `BehaviorSubject`.</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [getValue](#getValue)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.BehaviorSubject:getValue() -> anything`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Returns the last value emitted by the `BehaviorSubject`, or the initial value passed to the constructor if nothing has been emitted yet.                                                                     |
| **Parameters**                              | <ul><li>None</li></ul> |
| **Returns**                                 | <ul><li>The last value.</li></ul>          |
| **Notes**                                   | <ul><li>You can also call the `BehaviorSubject` as a function to retrieve the value. E.g. `mySubject()`.</li></ul>                |

| [onNext](#onNext)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.BehaviorSubject:onNext(...) -> nil`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Pushes zero or more values to the `BehaviorSubject`. They will be broadcasted to all [Observers](cp.rx.Observer.md).                                                                     |
| **Parameters**                              | <ul><li>...     - The values to send.</li></ul> |
| **Returns**                                 | <ul><li>None</li></ul>          |
| **Notes**                                   | <ul></ul>                |

| [subscribe](#subscribe)         |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.rx.BehaviorSubject:subscribe(observer, onError, onCompleted) -> cp.rx.Reference`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Creates a new [Observer](cp.rx.Observer.md) and attaches it to the `BehaviorSubject`. Immediately broadcasts the most recent value to the [Observer](cp.rx.Observer.md).                                                                     |
| **Parameters**                              | <ul><li>observer - The [Observer](cp.rx.Observer.md) subscribing, or the `function` called when the `BehaviorSubject` produces a value.</li><li>onError - A `function` called when the `BehaviorSubject` terminates due to an error.</li><li>onCompleted - A `function` called when the `BehaviorSubject` completes normally.</li></ul> |
| **Returns**                                 | <ul><li>The [Reference](cp.rx.Reference.md)</li></ul>          |
| **Notes**                                   | <ul></ul>                |
