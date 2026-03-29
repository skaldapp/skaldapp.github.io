---
title: Attributes
description: Add custom classes, IDs, styles, and data attributes to standard Markdown elements using curly brace syntax.
attrs:
  un-cloak: true
  class:
    - w-full
icon: twemoji:page-facing-up
---

## Attributes

Add custom classes, IDs, styles, and data attributes to standard Markdown elements using curly brace syntax.

Skald allows you to add custom attributes to standard Markdown elements using the `{...}` syntax immediately after an element.

### Element Attributes

#### Strong/Bold

```Markdown

**bold text**{.highlight #important}
**bold text**{data-value="custom"}
**bold text**{bool}

```

#### Italic/Emphasis

```Markdown

*italic text*{.emphasized}
*italic text*{#custom-id}

```

#### Links

```Markdown

[Link text](url){target="_blank" rel="noopener"}
[Link text](url){.button .primary}
[External](https://example.com){target="_blank" .external-link}

```

#### Images

```Markdown

![Alt text](image.png){.responsive width="800" height="600"}
![Logo](logo.svg){.logo #site-logo}

```

#### Inline Code

```Markdown

`code snippet`{.language-js}
`variable`{data-type="string"}

```

### Attribute Types

| Syntax                       | Output                | Description                |
| :--------------------------- | :-------------------- | :------------------------- |
| `{bool}`                     | `:bool="true"`        | Boolean attribute          |
| `{#my-id}`                   | `id="my-id"`          | ID attribute               |
| `{.my-class}`                | `class="my-class"`    | Class attribute            |
| `{key="value"}`              | `key="value"`         | Key-value attribute        |
| `{:data='{"key": "val"}'}`   | `data={"key": "val"}` | JSON object attribute      |

### Span Attributes

Add custom attributes to any text fragment by wrapping it in `<span>`. This allows you to style individual parts of text or add metadata without creating custom components.

### Syntax

```Markdown
[text content]{attributes}
```

Text is specified in square brackets `[...]`, followed by attributes in curly braces `{...}`.

### Examples

#### Class:

```Markdown
This is [highlighted text]{.highlight} in a paragraph.
```

```html
<p>This is <span class="highlight">highlighted text</span> in a paragraph.</p>
```

#### Multiple classes:

```Markdown
[Important]{.badge .primary} information here.
```

```html
<p><span class="badge primary">Important</span> information here.</p>
```

#### ID:

```Markdown
Reference this [specific text]{#ref-1} later.
```

```html
<p>Reference this <span id="ref-1">specific text</span> later.</p>
```

#### Inline styles:

```Markdown
[Blue text]{style="color: blue; font-weight: bold"}
```

```html
<p><span style="color: blue; font-weight: bold">Blue text</span></p>
```

#### Data attributes:

```Markdown
[Earth]{data-planet="earth" data-type="terrestrial"}
```

```html
<p><span data-planet="earth" data-type="terrestrial">Earth</span></p>
```

#### Combined attributes:

```Markdown
[Status: Active]{#status .badge .success data-state="active"}
```

```html
<p><span id="status" class="badge success" data-state="active">Status: Active</span></p>
```

### Nested Markdown

You can use nested formatting inside span elements.

```Markdown
[**Bold** and *italic* text]{.highlight}
```

```html
<p><span class="highlight"><strong>Bold</strong> and <em>italic</em> text</span></p>
```

