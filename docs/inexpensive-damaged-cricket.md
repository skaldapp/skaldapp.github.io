---
title: Skald
description: Skald is a modern tool for working with text and web development.
attrs:
  un-cloak: true
  class:
    - max-w-none
    - prose
    - prose-slate
    - prose-sm
    - sm:prose-base
    - dark:prose-invert
    - min-h-dvh
template: true
icon: twemoji:page-facing-up
script:
  - type: importmap
    innerHTML: |
      {
        "imports": {
          "@vueuse/core": "https://cdn.jsdelivr.net/npm/@vueuse/core@14/dist/index.js",
          "@vueuse/shared": "https://cdn.jsdelivr.net/npm/@vueuse/shared@14/dist/index.js",
          "element-plus": "https://cdn.jsdelivr.net/npm/element-plus@2/dist/index.full.min.mjs",
          "@iconify/vue": "https://cdn.jsdelivr.net/npm/@iconify/vue@5/dist/iconify.mjs"
        }
      }
---

<ul id="menu" class="not-prose container mx-auto px-4 flex flex-wrap gap-3 w-full text-sm border-b-2 py-4 mt-2 mb-24 font-medium">
<li><RouterLink to="/" id="logo">SK<Icon icon="fa7-solid:mountain" class="align-text-bottom size-5 inline-block" />LD</RouterLink></li>
<li v-for="{ frontmatter: { title }, to, id } in the.$children.slice(1)" :key="id"><RouterLink :to>{{ title }}</RouterLink></li>
<li><a href="https://github.com/skaldapp" target="_blank" rel="noopener noreferrer"><Icon icon="carbon:logo-github" class="align-middle size-6 inline-block" /></a></li>
<li><Icon icon="carbon:sun" class="align-middle size-6 dark-size-6 cursor-pointer inline-block dark-hidden" @click="toggleDark()" /><Icon icon="carbon:moon" class="align-middle size-6 dark-size-6 cursor-pointer hidden !dark-inline-block" @click="toggleDark()" /></li>
</ul>

::div{.min-h-dvh.container.mx-auto.px-4}

:RouterView

::

::div{.bg-[var(--nord6)].dark-bg-[var(--nord0)].mt-32}

:::div{.container.mx-auto.px-4.py-8}

:h3[🚀 Ready to structure your ideas?]

Start simple: create your first note. If needed — add style, interactivity, or publishing. Skald grows with your tasks.

:el-button[Download for free]{.not-prose type="primary" tag="a" href="https://github.com/skaldapp/skaldapp/releases/latest" target="_blank" rel="noopener noreferrer"}
:el-button[Try in browser]{.not-prose type="primary" tag="a" href="https://skaldapp.github.io/skaldapp" target="_blank" rel="noopener noreferrer"}

:::

::

:elBacktop

<script setup lang="js">
import { inject } from "vue";
import ElementPlus from "element-plus";
import { useDark, useToggle } from "@vueuse/core";
import { Icon } from "@iconify/vue";

const toggleDark = useToggle(useDark());
const docs = inject("docs");
const the = docs[$id];
const app = window.__vue_app__;

app.use(ElementPlus);
app.component("Icon", Icon);

</script>

<style>
@import url("https://cdn.jsdelivr.net/npm/element-plus@2/theme-chalk/index.css");
@import url("https://cdn.jsdelivr.net/npm/element-plus@2/theme-chalk/dark/css-vars.css");

:root {
  --nord0: #2E3440;
  --nord1: #3B4252;
  --nord2: #434C5E;
  --nord3: #4C566A;
  --nord4: #D8DEE9;
  --nord5: #E5E9F0;
  --nord6: #ECEFF4;
  --nord7: #8FBCBB;
  --nord8: #88C0D0;
  --nord9: #81A1C1;
  --nord10: #5E81AC;
  --nord11: #BF616A;
  --nord12: #D08770;
  --nord13: #EBCB8B;
  --nord14: #A3BE8C;
  --nord15: #B48EAD;
}
</style>

<style lang="postcss">
body {
  @apply dark-bg-[var(--nord1)];
}
</style>

<style scoped lang="postcss">
#menu {
  @apply border-[var(--nord8)];

  & li:nth-last-child(2) {
    @apply ml-auto -mr-4;
  }

  & a.router-link-active:not(#logo) {
    @apply bg-[var(--nord8)] text-[var(--nord6)];
  }
}

#menu a {
  @apply "text-[var(--nord0)] transition px-3 py-2 rounded-md hover-text-[var(--nord10)] dark-text-[var(--nord6)]";
}
</style>
