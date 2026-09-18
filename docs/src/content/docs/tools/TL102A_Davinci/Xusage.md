---
title: "DaVinci Configuration Support — Xusage"
description: "Converted Text Note / Report from Xusage.txt (TXT, 1 KB)."
---

:::note
Converted from `TL102A_Davinci/tools/Developer/Reporting/jre/bin/client/Xusage.txt` (Text Note / Report; original TXT, about 1 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL102A_Davinci](./)

*Conversion method: ver batim transcription.*

```text
    -Xmixed           mixed mode execution (default)
    -Xint             interpreted mode execution only
    -Xbootclasspath:<directories and zip/jar files separated by ;>
                      set search path for bootstrap classes and resources
    -Xbootclasspath/a:<directories and zip/jar files separated by ;>
                      append to end of bootstrap class path
    -Xbootclasspath/p:<directories and zip/jar files separated by ;>
                      prepend in front of bootstrap class path
    -Xnoclassgc       disable class garbage collection
    -Xincgc           enable incremental garbage collection
    -Xloggc:<file>    log GC status to a file with time stamps
    -Xbatch           disable background compilation
    -Xms<size>        set initial Java heap size
    -Xmx<size>        set maximum Java heap size
    -Xss<size>        set java thread stack size
    -Xprof            output cpu profiling data
    -Xfuture          enable strictest checks, anticipating future default
    -Xrs              reduce use of OS signals by Java/VM (see documentation)
    -Xcheck:jni       perform additional checks for JNI functions
    -Xshare:off	      do not attempt to use shared class data
    -Xshare:auto      use shared class data if possible (default)
    -Xshare:on	      require using shared class data, otherwise fail.

The -X options are non-standard and subject to change without notice.

```
