---
title: Tailwind CSS
attrs:
  un-cloak: true
  class:
    - w-full
icon: twemoji:page-facing-up
---

## [Tailwind CSS](https://tailwindcss.com/){target="_blank"} is already integrated and ready to use

In the Skald editor, Tailwind CSS classes are available immediately without any additional setup: no need to include libraries, configure builds, or edit configurations. Simply write HTML and apply ready-to-use Tailwind classes — everything works by default.

:elAlert{.not-prose title="FOUC" type="warning" description="To prevent content flickering on load, use the `un-cloak` attribute on the root element of the page." show-icon :closable="false"}

**Markup**

```HTML

<button class="m-2 bg-blue-400 hover:bg-blue-500 text-sm text-white font-mono font-light py-2 px-4 rounded border border-blue-200 dark:bg-blue-500 dark:hover:bg-blue-600">
  Button
</button>

```

::elCard{.not-prose header="Result" header-class="font-bold"}

<button class="m-2 bg-blue-400 hover:bg-blue-500 text-sm text-white font-mono font-light py-2 px-4 rounded border border-blue-200 dark:bg-blue-500 dark:hover:bg-blue-600">
  Button
</button>

::

Or even like this:

**Markup**

```HTML

<button m-2 bg="blue-400 hover:blue-500 dark:blue-500 dark:hover:blue-600" text="sm white" font="mono light" p="y-2 x-4" border="~ rounded blue-200">
  Button
</button>

```

::elCard{.not-prose header="Result" header-class="font-bold"}

<button m-2 bg="blue-400 hover:blue-500 dark:blue-500 dark:hover:blue-600" text="sm white" font="mono light" p="y-2 x-4" border="~ rounded blue-200">
  Button
</button>

::

You can also use abbreviated syntax for components, for example `text-red` instead of `class="text-red"`:

**Markup**

```html

<!-- standard syntax -->

<span class="text-red">red text</span>
<div class="flex">flexbox</div>
I'm feeling <span class="i-line-md-emoji-grin"></span> today!

<!-- abbreviated syntax -->

<text-red>red text</text-red>
<flex>flexbox</flex>
I'm feeling <i-line-md-emoji-grin /> today!

```

::elCard{.not-prose header="Result" header-class="font-bold"}

<text-red>red text</text-red>
<flex>flexbox</flex>
I'm feeling <i-line-md-emoji-grin /> today!

::

## Icons

Any icon from the Iconify project is available on demand. Simply add the class `i-<collection-name>:<icon-name>` to any element, and the icon will appear. For example, `i-carbon:sun` will display a sun icon from the Carbon collection.

**Markup**

```html

<div class="flex items-center gap-x-4 text-4xl p-2 mt-4">
    <div class="i-ph:anchor-simple-thin"></div>
    <div class="i-mdi:alarm text-orange-400 hover:text-teal-400"></div>
    <div class="w-2em h-2em i-logos:vue transform transition-800 hover:rotate-180"></div>
    <div class="i-carbon:sun dark:i-carbon:moon !w-2em !h-2em"></div>
    <div class="i-twemoji:grinning-face-with-smiling-eyes hover:i-twemoji:face-with-tears-of-joy"></div>
    <div class="text-base my-auto flex"><div class="i-carbon:arrow-left my-auto mr-1"></div> Hover it</div>
</div>

```

::elCard{.not-prose header="Result" header-class="font-bold"}

<div class="flex items-center gap-x-4 text-4xl p-2 mt-4">
    <div class="i-ph:anchor-simple-thin"></div>
    <div class="i-mdi:alarm text-orange-400 hover:text-teal-400"></div>
    <div class="w-2em h-2em i-logos:vue transform transition-800 hover:rotate-180"></div>
    <div class="i-carbon:sun dark:i-carbon:moon !w-2em !h-2em"></div>
    <div class="i-twemoji:grinning-face-with-smiling-eyes hover:i-twemoji:face-with-tears-of-joy"></div>
    <div class="text-base my-auto flex"><div class="i-carbon:arrow-left my-auto mr-1"></div> Hover it</div>
</div>

::

## Typography

:elAlert{.not-prose title="Prose" type="primary" description="Typography is enabled by adding the prose class to an element. It can be disabled with the not-prose class." show-icon :closable="false"}

**Markup**

```html

<article class="prose prose-stone prose-xl dark:prose-invert">
  <h1>Cheesy Garlic Bread: What Science Says</h1>
  <p>
    For years, parents have maintained the health benefits of eating cheesy garlic bread
    for their children, and this food has achieved such iconic status in our culture
    that children often dress up as warm, cheesy bread for Halloween.
  </p>
  <p>
    But recent research suggests that the famous snack may be linked
    to a series of rabies cases occurring across the country.
  </p>
</article>

```

::elCard{header="Result" header-class="font-bold"}

<article class="prose-stone prose-xl dark:prose-invert">
  <h1>Cheesy Garlic Bread: What Science Says</h1>
  <p>
    For years, parents have maintained the health benefits of eating cheesy garlic bread
    for their children, and this food has achieved such iconic status in our culture
    that children often dress up as warm, cheesy bread for Halloween.
  </p>
  <p>
    But recent research suggests that the famous snack may be linked
    to a series of rabies cases occurring across the country.
  </p>
</article>

::
