---
title: CSS Styles
attrs:
  un-cloak: true
  class:
    - w-full
icon: twemoji:page-facing-up
---

## Styling Markdown with CSS

Markdown provides a concise syntax for formatting text, but CSS styles can make your documents more beautiful and professional.

:elAlert{.not-prose title="scoped" type="warning" description="Styles apply only to the current page if the scoped attribute is used." show-icon :closable="false"}

**Markup**

```html

<style scoped>
.highlight {
  background-color: #fff3cd;
  color: black;
  padding: 10px;
  border-left: 4px solid #ffc107;
}
</style>

<div class="highlight">
This is an important highlighted paragraph.
</div>

```

::elCard{header="Result" header-class="font-bold"}


<style scoped>
.highlight {
  background-color: #fff3cd;
  color: black;
  padding: 10px;
  border-left: 4px solid #ffc107;
}
</style>

<div class="highlight">
This is an important highlighted paragraph.
</div>

::

For the same purposes, you can use classes from Tailwind CSS.

**Markup**

```html

<style lang="postcss" scoped>
.highlight-tw {
  @apply bg-amber-100 text-black p-3 border-l-4 border-yellow-400;
}
</style>

<div class="highlight-tw">
This is an important highlighted paragraph using Tailwind CSS classes.
</div>

```

::elCard{header="Result" header-class="font-bold"}

<style lang="postcss" scoped>
.highlight-tw {
  @apply bg-amber-100 text-black p-3 border-l-4 border-yellow-400;
}
</style>

<div class="highlight-tw">
This is an important highlighted paragraph using Tailwind CSS classes.
</div>

::

Styles can also be imported from external files, for example, from a CDN:

**Markup**

```html

<style scoped src="https://cdn.jsdelivr.net/npm/hover.css/css/hover-min.css"></style>

<div class="hvr-buzz">Hover over me!!!</div>

```

::elCard{header="Result" header-class="font-bold"}

<style scoped src="https://cdn.jsdelivr.net/npm/hover.css/css/hover-min.css"></style>

<div class="hvr-buzz">Hover over me!!!</div>

::