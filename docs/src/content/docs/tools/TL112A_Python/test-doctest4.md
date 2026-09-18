---
title: "Python Engineering Utilities — test doctest4"
description: "Converted Text Note / Report from test_doctest4.txt (TXT, 0 KB)."
---

:::note
Converted from `TL112A_Python/tools/Lib/test/test_doctest4.txt` (Text Note / Report; original TXT, about 0 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL112A_Python](./)

*Conversion method: ver batim transcription.*

```text
This is a sample doctest in a text file that contains non-ASCII characters.
This file is encoded using UTF-8.

In order to get this test to pass, we have to manually specify the
encoding.

  >>> u'föö'
  u'f\xf6\xf6'

  >>> u'bąr'
  u'b\u0105r'

  >>> 'föö'
  'f\xc3\xb6\xc3\xb6'

  >>> 'bąr'
  'b\xc4\x85r'

```
