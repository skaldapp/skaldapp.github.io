---
title: Extensions
attrs:
  un-cloak: true
  class:
    - w-full
icon: twemoji:page-facing-up
---

## Code

Use triple backticks `` ` `` to wrap code, specify the language name after the opening `` ` `` to enable syntax highlighting:

````Markdown

```JavaScript

const fibonacci = (length) => Array.from({ length }, function (_, $) { return this[$] = this[$ - 1] + this[$ - 2] || $ }, []);

console.log(fibonacci(10)); // [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]

```

````

Will produce the following result:

```JavaScript

const fibonacci = (length) => Array.from({ length }, function (_, $) { return this[$] = this[$ - 1] + this[$ - 2] || $ }, []);

console.log(fibonacci(10)); // [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]

```

## Tables

**Markup**

```Markdown

| Left aligned | Center aligned | Right aligned |
| :----------- | :------------: | ------------: |
| Content 1    |    Content 1   |     Content 1 |
| Content 2    |    Content 2   |     Content 2 |
| Content 3    |    Content 3   |     Content 3 |

```

::elCard{header="Result" header-class="font-bold"}

| Left aligned | Center aligned | Right aligned |
| :----------- | :------------: | ------------: |
| Content 1    |    Content 1   |     Content 1 |
| Content 2    |    Content 2   |     Content 2 |
| Content 3    |    Content 3   |     Content 3 |

::

## Mathematical Formulas

Use double dollar signs $$ to wrap formulas that will be displayed on a separate centered line. For example, the Schrödinger equation:

**Markup**

```

$$
i\hbar\frac{\partial}{\partial t}\Psi(\mathbf{r},t) = \hat{H}\Psi(\mathbf{r},t)
$$

```

::elCard{header="Result" header-class="font-bold"}

$$
i\hbar\frac{\partial}{\partial t}\Psi(\mathbf{r},t) = \hat{H}\Psi(\mathbf{r},t)
$$

::

## Images

**Markup**

```Markdown

![Markdown](uploads/markdown.png) - ![](uploads/markdown.png "Markdown Logo") - ![Markdown](uploads/markdown.png "Markdown Logo")

![1.00](uploads/elder.jpg "Elder")

```

::elCard{header="Result" header-class="font-bold"}

![Markdown](uploads/markdown.png) - ![](uploads/markdown.png "Markdown Logo") - ![Markdown](uploads/markdown.png "Markdown Logo")

![1.00](uploads/elder.jpg "Elder")

::