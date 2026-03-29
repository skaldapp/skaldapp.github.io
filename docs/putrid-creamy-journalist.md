---
title: Easy
icon: twemoji:page-facing-up
template: true
attrs:
  un-cloak: true
---

# Skald is Easy

[Markdown](https://en.wikipedia.org/wiki/Markdown){target="_blank"} is a **lightweight markup language** that allows you to format text using simple and intuitive syntactic constructs. It was created in 2004 by John Gruber and Aaron Swartz with the goal of making text as readable as possible both in its original form and after conversion to HTML or other formats.

Skald supports creating texts in Markdown format, both in visual and text mode, which allows you to easily and quickly format content using simple and understandable syntactic constructs.

<elMenu mode="horizontal" :router="true" :default-active="$route.path"><elMenuItem v-for="{ name, to, frontmatter: {title} } in doc.$children" :index="to" class="!px-5">{{ title ?? name }}</elMenuItem></elMenu>

:RouterView

<script setup>
import { inject } from "vue";

const docs = inject("docs");
const doc = docs[$id];
</script>
