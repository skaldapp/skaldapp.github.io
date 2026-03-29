---
title: Frontmatter
attrs:
  un-cloak: true
  class:
    - w-full
icon: twemoji:page-facing-up
---

## Frontmatter in Skald

Frontmatter is a special section at the top of a Markdown file used to store document metadata. It uses YAML format and is surrounded by three dashes (`---`). Skald uses Frontmatter to control page behavior, metadata, and other settings using the Unhead library.

You can access metadata through the global [{{ $frontmatter }}]{v-pre} object in Vue expressions, for example, for the current page it would look like:

```

{{ $frontmatter }}

```

For instance, if you want to access the page title, you can use the expression: [{{ $frontmatter.title }}]{v-pre}, which will immediately display the current page title - **{{ $frontmatter.title }}**.

### Basic Syntax

```YAML

---
title: Title
description: Description
attrs:
  un-cloak: true
  class:
    - container
    - mx-auto
    - prose
    - prose-sm
    - sm:prose-base
    - dark:prose-invert
hidden: false
template: false
icon: twemoji:page-facing-up
---

# My Document Heading

Main document content goes here...

```

## Main Fields

### Page Control Attributes

* **attrs** - array of page container attributes, usually includes the un-cloak attribute to prevent FOAC effect and classes for styling

* **hidden** - hides the page from navigation

* **template** - indicates that the page is a template where RouterView can be added

* **icon** - page icon

### Page Metadata

* **title** - page title

* **titleTemplate** - page title template (function or string with %s placeholder)

* **templateParams** - template parameters for dynamic replacements

* **base** - base URL for all relative URLs on the page (normally computed automatically and doesn't need to be specified manually)

* **link** - array of objects for defining links to external resources (e.g., favicon, styles, fonts, etc.)

* **meta** - array of objects for defining page metadata (e.g., description, keywords, Open Graph, etc.)

* **style** - array of objects for defining inline styles on the page

* **script** - array of objects for defining inline scripts on the page

* **noscript** - array of objects for defining content that will be displayed if JavaScript is disabled in the browser

* **htmlAttrs** - object for defining `<html>` element attributes

* **bodyAttrs** - object for defining `<body>` element attributes

### Additional Fields

Any additional fields added to frontmatter will be used to define page metadata. For example, if you add a `description` field, it will be used to define the page's meta description, and the `keywords` field will be used to define meta keywords.

```YAML

---
title: The Complete Guide to Markdown
description: A comprehensive guide to learning Markdown syntax and best practices
keywords: markdown, tutorial, guide, syntax
---

```

