---
title: Formatting
attrs:
  un-cloak: true
  class:
    - w-full
icon: twemoji:page-facing-up
---

## Basic Formatting

| **Effect**       | **Syntax**      | **Example**         |
| ---------------- | --------------- | ------------------- |
| Italic           | `*text*`        | *Italic*            |
| Bold             | `**text**`      | **Bold**            |
| Bold Italic      | `***text***`    | ***Bold Italic***   |
| Strikethrough    | `~~text~~`      | ~~Strikethrough~~   |

## Advanced Formatting

| **Type**  | **Syntax**      | **Example**    |
| --------- | --------------- | -------------- |
| Code      | `const a=1;`    | `const a=1;`   |
| Formula   | `$E = mc^2$`    | $E = mc^2$     |

## Links

**Markup**

```Markdown

[Link text](https://skaldapp.ru)

[Link with title](https://skaldapp.ru "Link title")

```

::elCard{header="Result" header-class="font-bold"}

[Link text](https://skaldapp.ru)

[Link with title](https://skaldapp.ru "Link title")

::

| **Type**             | **Syntax**                                          | **Example**                                         |
| -------------------- | --------------------------------------------------- | --------------------------------------------------- |
| Absolute link        | `[skaldapp.ru](https://skaldapp.ru)`                | [skaldapp.ru](https://skaldapp.ru)                  |
| Relative link        | `[medium](/medium/)`                                | [medium](/medium/)                                  |
| Heading link         | `[Basic Formatting](#basic-formatting)`             | [Basic Formatting](#basic-formatting)               |

:elAlert{.not-prose title="Table of Contents" type="primary" description="To generate a table of contents for all headings on the page, use `[[toc]]`" show-icon :closable="false"}

## Auto Links

**Markup**

```Markdown

https://skaldapp.ru

skaldapp@outlook.com

```

::elCard{header="Result" header-class="font-bold"}

<https://skaldapp.ru>

<skaldapp@outlook.com>

::

## Image Link

**Markup**

```Markdown

[![1.00](uploads/valkyrja.jpg)](https://skaldapp.ru)

```

::elCard{.not-prose header="Result" header-class="font-bold"}

[![1.00](uploads/valkyrja.jpg)](https://skaldapp.ru)

::