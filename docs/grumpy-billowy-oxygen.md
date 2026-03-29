---
title: Vue
attrs:
  un-cloak: true
  class:
    - w-full
icon: twemoji:page-facing-up
---

## Templating

### Interpolation

Every Markdown file is first compiled to HTML and then passed as a Vue component through the processing pipeline. This means you can use Vue-style interpolation in text:

**Markup**

::pre

[{{ 1 + 1 }}]{v-pre}

::

::elCard{header="Result" header-class="font-bold"}

#default
{{ 1 + 1 }}

::

### Directives

Directives also work (note that raw HTML is also valid in Markdown by design):

**Markup**

::div{v-pre}

```html

<span v-for="i in 3">{{ i }}</span>

```

::

::elCard{header="Result" header-class="font-bold"}

<span v-for="i in 3">{{ i }}</span>

::

## `<script>` and `<style>`

Root-level `<script>` and `<style>` tags in Markdown files work the same as in Vue SFC, including `<script setup>`, `<style module>`, etc. The main difference is the absence of a `<template>` tag: all other root-level content is Markdown. Also note that all tags must be placed **after** the frontmatter:

::div{v-pre}

```Markdown

---
title: hello world
---

<script setup>
import { ref } from "vue";

const count = ref(0);
</script>

## Markdown Content. Counter: {{ count }}

<button class="button" @click="count++">Increment</button>

<style scoped>
.button {
  color: red;
  font-weight: bold;
}
</style>
```

::

## Using Components

You can import and use Vue components directly in Markdown files.

:elAlert{.not-prose title="Default Libraries" type="warning" description="The vue and vue-router libraries are included in the build by default, so they don't need to be specified in `importmap`." show-icon :closable="false"}

<br />

:elAlert{.not-prose title="Modules" type="primary" description="Modern packages usually already include an ESM module file for import. If for some reason a package doesn't have an ESM module, you can use services that will build the module from the package sources for you: <https://esm.sh>, <https://esm.run>" show-icon :closable="false"}

### Import in Markdown

If a component is only used on a few pages, it's recommended to explicitly import it where it's used. This allows proper code splitting and loading only when showing the corresponding pages. Don't forget to use `importmap` when importing components from CDN.

```Markdown
---
title: Using Components
script:
  - type: importmap
    innerHTML: |
      {
        "imports": {
          "element-plus": "https://cdn.jsdelivr.net/npm/element-plus@2/dist/index.full.min.mjs"
        }
      }
---

<script setup>
import { ref } from "vue";
import { elRate } from "element-plus";

const value = ref(3.7);
</script>

<style scoped src="https://cdn.jsdelivr.net/npm/element-plus@2/theme-chalk/index.css"></style>
<style scoped src="https://cdn.jsdelivr.net/npm/element-plus@2/theme-chalk/dark/css-vars.css"></style>

# Documentation

This is a .md file using a custom component

<elRate v-model="value" disabled show-score text-color="#ff9900" score-template="{value} points" />

## Other Documentation

...
```

<elCard header="Result" header-class="font-bold">

# Documentation

This is a .md file using a custom component

<elRate v-model="value" disabled show-score text-color="#ff9900" score-template="{value} points" />

## Other Documentation

...

</elCard>

If you need to define components globally, you can use the app instance `window.__vue_app__` and register components on it.

```Markdown

---
title: Using Components
script:
  - type: importmap
    innerHTML: |
      {
        "imports": {
          "element-plus": "https://cdn.jsdelivr.net/npm/element-plus@2/dist/index.full.min.mjs"
        }
      }
---

<script setup>
import { ref } from "vue";
import ElementPlus from "element-plus";

const app = window.__vue_app__;
app.use(ElementPlus);

const value = ref(3.7);
</script>

<style>
@import url("https://cdn.jsdelivr.net/npm/element-plus@2/theme-chalk/index.css");
@import url("https://cdn.jsdelivr.net/npm/element-plus@2/theme-chalk/dark/css-vars.css");
</style>

# Documentation

This is a .md file using a custom component

<elRate v-model="value" disabled show-score text-color="#ff9900" score-template="{value} points" />

## Other Documentation

...

```

## Routing

To use routing, you need to enable the `template: true` parameter in the page configuration and add a `<RouterView />` tag to the page template. This will allow rendering child pages within the parent page.

:elAlert{.not-prose title="Frontmatter Inheritance" type="primary" description="Child pages inherit frontmatter from parent template pages. For example, if an importmap is specified in a parent template page, it will be available in child pages as well." show-icon :closable="false"}

```Markdown
---
title: Parent Page
template: true
---

# Parent Page

<RouterView />

```

Although any number of pages in the project can contain a `<RouterView />` tag, a good practice is to use it in the root page by setting the `template: true` parameter. This will allow rendering child pages within the parent page, using a common template for all pages, and using parent page frontmatter in child pages.

<script setup>
import { ref } from "vue";

const value = ref(3.7);
</script>
