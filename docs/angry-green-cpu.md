---
title: Hard
icon: twemoji:page-facing-up
attrs:
  un-cloak: true
template: true
---

# Skald is Professional

## Using Vue in Markdown

In Skald, every Markdown file is compiled to HTML and then processed as a Vue single-file component. This means you can use any Vue features within Markdown, including dynamic templating, using Vue components, or adding arbitrary Vue component logic to the page by adding a `<script>` tag.

<elMenu mode="horizontal" :router="true" :default-active="$route.path"><elMenuItem v-for="{ name, to, frontmatter: { title } } in doc.$children" :index="to" class="!px-5">{{ title ?? name }}</elMenuItem></elMenu>

:RouterView

<script setup>
import { inject } from "vue";

const docs = inject("docs");
const doc = docs[$id];
</script>
