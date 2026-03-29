---
title: Semantics
attrs:
  un-cloak: true
  class:
    - w-full
icon: twemoji:page-facing-up
---

## Semantic Page Object

Each page contains a static constant `$id` with a unique identification number that always matches the filename in the `docs` directory.

You can also inject an associative array of all semantic page objects and get the identification number of the currently selected page from the router object.

```JavaScript

/** Import computed and inject */
import { computed, inject } from "vue";
/** Import the selected route composable */
import { useRoute } from "vue-router";
/** Get the selected route object */
const route = useRoute();
/** Inject the array of semantic page objects of the site */
const docs = inject("docs");
/** Get the semantic object of the current page */
const doc = docs[$id];
/** Compute the semantic object of the selected page */
const current = computed(() => docs[route.name]);

```

## Usage Example

**Markup**

::div{v-pre}

```HTML

<h3>{{ doc.parent.title }}</h3>
<ul>
    <li v-for="{title} in doc.$siblings">{{ title }}</li>
</ul>

```

::

::elCard{header="Result" header-class="font-bold"}

<h3>{{ doc.parent.frontmatter.title }}</h3>
<ul>
    <li v-for="{ frontmatter: { title } } in doc.$siblings">{{ title }}</li>
</ul>

::

## Attributes List

* **id** - Unique identifier of the doc page

* **name** - Short name of the doc page, used to generate the path attribute

* **frontmatter** - Frontmatter object of the doc page

* **parent** - Parent page of doc

* **next** - Next page from doc in the siblings array

* **prev** - Previous page from doc in the siblings array

* **index** - Index of the doc page in the siblings array

* **children** - Child pages of doc

* **siblings** - Array of same-level pages as doc

* **path** - Relative path to the doc page

* **branch** - Array of pages from root to the doc page

* **to** - Page URL for use in `<RouterLink>`

Additionally, there are attributes that start with the `$` character (`$children`, `$index`, `$siblings`, `$next`, `$prev`, `$branch`, `$parent`) and contain the corresponding pages filtered by the `hidden` parameter in frontmatter.

<script setup>
import { inject } from "vue";
const docs = inject("docs");
const doc = docs[$id];
</script>
