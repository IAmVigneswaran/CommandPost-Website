# cp.ui.Builder

A utility class, which provides support for allowing creation of [Element](cp.ui.Element.md) instances in a "builder" style.

This is useful for creating complex UI elements, such as a [Table](cp.ui.Table.md) or [ScrollArea](cp.ui.ScrollArea.md),
which can have custom sub-elements.

A `Builder` instance can be called like a function, expecting a `parent` and `uiFinder`, which are the basic values required
to create a new `Element` instance. Specific subclasses have extra values, which a `Builder` can define to pass in.

For example, a [Table](cp.ui.Table.md) has a `headerType` and `rowType` in its constructor, which are used to create the
header and row elements when required:

```lua
local myTable = cp.ui.Table(parent, uiFinder, Group, Row)
```

However, its quite common for a `ScrollArea` to contain a [Table](cp.ui.Table.md), and in order to use the `ScrollArea:containing(Table)`
method, you would have to provide a wrapper function that hard-codes the `headerType` and `rowType` values:

```lua
local scrollArea = ScrollArea:containing(function(parent, uiFinder)
    return Table(parent, uiFinder, Group, Row)
end)
```

However, `Table` has its own helper method for this to make it easier to use:

```lua
local scrollArea = ScrollArea:containing(Table:withRowsOf(Row):withHeaderOf(Group))
scrollArea.contents.header -- A cp.ui.Group instance
scrollArea.contents.rows[1] -- A cp.ui.Row instance
```

Internally, the `Table:withRowsOf(rowType)` function returns a `Builder` configured to accept `"withRowsOf"` and `"withHeaderOf"`
values, which are then passed to the `Table` constructor.

To create your own `Builder` instances, you can just return a new `Builder`, specifying the type (typically `self`) and the names
of the constructor arguments to accept. For example:

```lua
local MyElement = Element:subclass("foo.MyElement")

function MyElement:initialize(parent, uiFinder, leftType, rightType)
    -- TODO
end

function MyElement.static:withLeftOf(leftType)
    return Builder(self, "withLeftOf", "withRightOf"):withLeftOf(leftType)
end
```

The `Builder` instance can then be used to create new `MyElement` instances:

```lua
local myElementBuilder = MyElement:withLeftOf(Group):withRightOf(Button)
local myElement = myElementBuilder(parent, uiFinder)
```

The order of the arguments is important, because it defines what order the constructor arguments will be passed in.
For example, if we added a `withRightOf` method definition, it would look like this:

```lua
function MyElement.static:withRightOf(rightType)
    return Builder(self, "withLeftOf", "withRightOf"):withRightOf(rightType)
end
local myElementBuilder = MyElement:withRightOf(Group):withLeftOf(Button)
```

The `"withLeftOf"` value will still be passed to the constructor first, because it is listed first in the `Builder` constructor.

---

## API Overview
**Methods** - _API calls which can only be made on an object returned by a constructor_
 * [build](#build)


---

## API Documentation

#### Methods


### [build](#build)

|                                             |                                                                                     |
| --------------------------------------------|-------------------------------------------------------------------------------------|
| **Signature**                               | `cp.ui.Builder:build(parent, uiFinder) -> cp.ui.Element`                                                                    |
| **Type**                                    | Method                                                                     |
| **Description**                             | Builds a new [Element](cp.ui.Element.md) instance, passing in the `parent` and `uiFinder` parameters, followed by any extra arguments that have been set, in the order passed to the constructor.                                                                     |
| **Parameters**                              | <ul><li>parent - The parent `Element`.</li><li>uiFinder - A `cp.prop` or `axuielement` that will be used to find this `Element`'s `axuielement`.</li></ul> |
| **Returns**                                 | <ul><li>A new `Element` instance.</li></ul>          |
| **Notes**                                   | None |
| **Examples**                                | None |
| **Source**                                  | [src/extensions/cp/ui/Builder.lua line 105](https://github.com/CommandPost/CommandPost/blob/develop/src/extensions/cp/ui/Builder.lua#L105) |

---

