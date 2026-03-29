---
title: HTML
attrs:
  un-cloak: true
  class:
    - w-full
icon: twemoji:page-facing-up
---

## Inline HTML Elements

You can use HTML tags directly in Markdown:

**Markup**

```Markdown

This is a paragraph with <strong>bold text</strong> and <em>italic text</em>.

You can use <code>inline code</code> or <mark>highlighted text</mark>.

Here is an <a href="https://skaldapp.github.io/skaldapp/" target="_blank">external link</a>.

```

::elCard{header="Result" header-class="font-bold"}

This is a paragraph with <strong>bold text</strong> and <em>italic text</em>.

You can use <code>inline code</code> or <mark>highlighted text</mark>.

Here is an <a href="https://skaldapp.github.io/skaldapp/" target="_blank">external link</a>.

::

## Block HTML Elements

**Markup**

```HTML

<div>
  <h4>Information</h4>
  <p>This is an information box created using HTML.</p>
</div>

<blockquote style="border-left: 4px solid #007bff; padding-left: 1rem; color: #657d;">
  <p>This is a quote with custom styling.</p>
  <footer>—— Source</footer>
</blockquote>

```

::elCard{header="Result" header-class="font-bold"}

<div>
  <h4>Information</h4>
  <p>This is an information box created using HTML.</p>
</div>

<blockquote style="border-left: 4px solid #007bff; padding-left: 1rem; color: #657d;">
  <p>This is a quote with custom styling.</p>
  <footer>—— Source</footer>
</blockquote>

::

## Mixed HTML Elements

**Markup**

```Markdown

<div style="text-align: center;">

#### Centered Heading

This is a paragraph inside a <strong>centered</strong> container.

</div>

```

<elCard header="Result" header-class="font-bold">

<div style="text-align: center;">

#### Centered Heading

This is a paragraph inside a <strong>centered</strong> container.

</div>

</elCard>
