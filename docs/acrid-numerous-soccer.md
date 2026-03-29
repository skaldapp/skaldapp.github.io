---
title: Medium
icon: twemoji:page-facing-up
attrs:
  un-cloak: true
template: true
---

# Skald is Effective

[HTML](https://developer.mozilla.org/en/docs/Web/HTML){target="_blank"} (HyperText Markup Language) is a standardized markup language for creating documents viewed in web browsers. HTML was developed by British scientist Tim Berners-Lee as a language for exchanging scientific and technical documentation, suitable for use by people who are not layout specialists.

One of Skald's powerful features is the ability to directly embed HTML code, which provides richer expressiveness and functional extensions for your documents.

<elMenu mode="horizontal" :router="true" :default-active="$route.path"><elMenuItem v-for="{ name, to, frontmatter: { title } } in doc.$children" :index="to" class="!px-5">{{ title ?? name }}</elMenuItem></elMenu>

:RouterView

<script setup>
import { inject } from "vue";

const docs = inject("docs");
const doc = docs[$id];
</script>