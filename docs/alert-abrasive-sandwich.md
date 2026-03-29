---
title: Components
description: Add custom components directly into Markdown — supports both block and inline syntax, props, slots, and nested elements.
attrs:
  un-cloak: true
  class:
    - w-full
icon: twemoji:page-facing-up
---

## Components

Add custom components directly into Markdown — supports both block and inline syntax, props, slots, and nested elements.

Skald adds component support to Markdown — now you can insert your own UI elements directly into text without sacrificing readability.

### Block Components

For block components, use the `::component-name` syntax, and they are always placed on a separate line.

```Markdown

::component-name{prop1="value1" prop2="value2"}
Content inside the component

Can have **markdown** and other elements
::

```

#### Examples

```Markdown
::alert{type="info"}
This is an important message!
::

::card{title="My Card"}
Card content with **markdown** support
::

::divider
::
```

### Inline Components

Inline components use the `:component-name` syntax and can be placed directly within text:

```Markdown
Check out this :icon-star component in the middle of text.

Click the :button[Submit]{type="primary"} to continue.

The status is :badge[Active]{color="green"} right now.
```

<br />

| Syntax                        | Description                             |
| :---------------------------- | :-------------------------------------- |
| `:icon-check`                 | Simple inline component                 |
| `:badge[New]`                 | Inline component with content           |
| `:badge[New]{color="blue"}`   | Inline component with content and props |
| `:tooltip{text="Hover text"}` | Inline component with props only        |

### Component Props

Use the `{...}` syntax for simple props:

```Markdown
::component{prop="value"}
<!-- Standard key-value pair -->
::

::component{bool}
<!-- Boolean property (becomes :bool="true" in AST) -->
::

::component{#custom-id}
<!-- ID attribute -->
::

::component{.class-name}
<!-- CSS class -->
::

::component{.class-one .class-two}
<!-- Multiple CSS classes -->
::

::component{obj='{"key": "value"}'}
<!-- Object/JSON value -->
::

::component{multiple="props" bool #id .class}
<!-- Multiple properties combined -->
::
```

### Component Slots

Block components support named slots using the `#slot-name` syntax:


```Markdown
::card
#header
# Card Title

#content
This is the main content of the card

#footer
Footer text here
::
```

## Nested Components

Components can be nested within each other using additional colons:

```Markdown
::outer-component
Content in outer

:::inner-component{variant="compact"}
Content in inner
:::

More content in outer
::
```
