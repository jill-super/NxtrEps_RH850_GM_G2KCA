---
title: "Python Engineering Utilities — test doctest"
description: "Converted Text Note / Report from test_doctest.txt (TXT, 0 KB)."
---

:::note
Converted from `TL112A_Python/tools/Lib/test/test_doctest.txt` (Text Note / Report; original TXT, about 0 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL112A_Python](./)

*Conversion method: ver batim transcription.*

```text
This is a sample doctest in a text file.

In this example, we'll rely on a global variable being set for us
already:

  >>> favorite_color
  'blue'

We can make this fail by disabling the blank-line feature.

  >>> if 1:
  ...    print 'a'
  ...    print
  ...    print 'b'
  a
  <BLANKLINE>
  b

```
