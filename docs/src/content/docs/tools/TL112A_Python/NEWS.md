---
title: "Python Engineering Utilities — NEWS"
description: "Converted Text Note / Report from NEWS.txt (TXT, 38 KB)."
---

:::note
Converted from `TL112A_Python/tools/Lib/idlelib/NEWS.txt` (Text Note / Report; original TXT, about 38 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL112A_Python](./)

*Conversion method: ver batim transcription.*

```text
What's New in IDLE 2.7.9?
=========================

*Release data: 2014-12-07* (projected)

- Issue #16893: Update Idle doc chapter to match current Idle and add new
  information.

- Issue #3068: Add Idle extension configuration dialog to Options menu.
  Changes are written to HOME/.idlerc/config-extensions.cfg.
  Original patch by Tal Einat.

- Issue #16233: A module browser (File : Class Browser, Alt+C) requires a
  editor window with a filename.  When Class Browser is requested otherwise,
  from a shell, output window, or 'Untitled' editor, Idle no longer displays
  an error box.  It now pops up an  Open Module box (Alt+M). If a valid name
  is entered and a module is opened, a corresponding browser is also opened.

- Issue #4832: Save As to type Python files automatically adds .py to the
  name you enter (even if your system does not display it).  Some systems
  automatically add .txt when type is Text files.

- Issue #21986: Code objects are not normally pickled by the pickle module.
  To match this, they are no longer pickled when running under Idle.

- Issue #22221: IDLE now ignores the source encoding declaration on the second
  line if the first line contains anything except a comment.

- Issue #17390: Adjust Editor window title; remove 'Python',
  move version to end.

- Issue #14105: Idle debugger breakpoints no longer disappear
  when inseting or deleting lines.


What's New in IDLE 2.7.8?
=========================

*Release date: 2014-06-29*

- Issue #21940: Add unittest for WidgetRedirector. Initial patch by Saimadhav
  Heblikar.

- Issue #18592: Add unittest for SearchDialogBase. Patch by Phil Webster.

- Issue #21694: Add unittest for ParenMatch. Patch by Saimadhav Heblikar.

- Issue #21686: add unittest for HyperParser. Original patch by Saimadhav
  Heblikar.

- Issue #12387: Add missing upper(lower)case versions of default Windows key
  bindings for Idle so Caps Lock does not disable them. Patch by Roger Serwy.

- Issue #21695: Closing a Find-in-files output window while the search is
  still in progress no longer closes Idle.

- Issue #18910: Add unittest for textView. Patch by Phil Webster.

- Issue #18292: Add unittest for AutoExpand. Patch by Saihadhav Heblikar.

- Issue #18409: Add unittest for AutoComplete. Patch by Phil Webster.


What's New in IDLE 2.7.7?
=========================

*Release date: 2014-05-31*

- Issue #18104: Add idlelib/idle_test/htest.py with a few sample tests to begin
  consolidating and improving human-validated tests of Idle. Change other files
  as needed to work with htest.  Running the module as __main__ runs all tests.

- Issue #21139: Change default paragraph width to 72, the PEP 8 recommendation.

- Issue #21284: Paragraph reformat test passes after user changes reformat width.

- Issue #20406: Use Python application icons for Idle window title bars.
  Patch mostly by Serhiy Storchaka.

- Issue #21029: Occurrences of "print" are now consistently colored as
  being a keyword (the colorizer doesn't know if print functions are
  enabled in the source).

- Issue #17721: Remove non-functional configuration dialog help button until we
  make it actually gives some help when clicked. Patch by Guilherme Simes.

- Issue #17390: Add Python version to Idle editor window title bar.
  Original patches by Edmond Burnett and Kent Johnson.

- Issue #20058: sys.stdin.readline() in IDLE now always returns only one line.

- Issue #19481: print() of unicode, str or bytearray subclass instance in IDLE
  no more hangs.

- Issue #18270: Prevent possible IDLE AttributeError on OS X when no initial
  shell window is present.

- Issue #17654: Ensure IDLE menus are customized properly on OS X for
  non-framework builds and for all variants of Tk.


What's New in IDLE 2.7.6?
=========================

*Release date: 2013-11-10*

- Issue #19426: Fixed the opening of Python source file with specified encoding.

- Issue #18873: IDLE now detects Python source code encoding only in comment
  lines.

- Issue #18988: The "Tab" key now works when a word is already autocompleted.

- Issue #18489: Add tests for SearchEngine. Original patch by Phil Webster.

- Issue #18429: Format / Format Paragraph, now works when comment blocks
  are selected. As with text blocks, this works best when the selection
  only includes complete lines.

- Issue #18226: Add docstrings and unittests for FormatParagraph.py.
  Original patches by Todd Rovito and Phil Webster.

- Issue #18279: Format - Strip trailing whitespace no longer marks a file as
  changed when it has not been changed. This fix followed the addition of a
  test file originally written by Phil Webster (the issue's main goal).

- Issue #18539: Calltips now work for float default arguments.

- Issue #7136: In the Idle File menu, "New Window" is renamed "New File".
  Patch by Tal Einat, Roget Serwy, and Todd Rovito.

- Issue #8515: Set __file__ when run file in IDLE.
  Initial patch by Bruce Frederiksen.

- Issue #5492: Avoid traceback when exiting IDLE caused by a race condition.

- Issue #17511: Keep IDLE find dialog open after clicking "Find Next".
  Original patch by Sarah K.

- Issue #15392: Create a unittest framework for IDLE.
  Preliminary patch by Rajagopalasarma Jayakrishnan
  See Lib/idlelib/idle_test/README.txt for how to run Idle tests.

- Issue #14146: Highlight source line while debugging on Windows.

- Issue #17532: Always include Options menu for IDLE on OS X.
  Patch by Guilherme Simes.


What's New in IDLE 2.7.5?
=========================

*Release date: 2013-05-12*

- Issue #17838: Allow sys.stdin to be reassigned.

- Issue #14735: Update IDLE docs to omit "Control-z on Windows".

- Issue #17585: Fixed IDLE regression. Now closes when using exit() or quit().

- Issue #17657: Show full Tk version in IDLE's about dialog.
  Patch by Todd Rovito.

- Issue #17613: Prevent traceback when removing syntax colorizer in IDLE.

- Issue #1207589: Backwards-compatibility patch for right-click menu in IDLE.

- Issue #16887: IDLE now accepts Cancel in tabify/untabify dialog box.

- Issue #14254: IDLE now handles readline correctly across shell restarts.

- Issue #17614: IDLE no longer raises exception when quickly closing a file.

- Issue #6698: IDLE now opens just an editor window when configured to do so.

- Issue #8900: Using keyboard shortcuts in IDLE to open a file no longer
  raises an exception.

- Issue #6649: Fixed missing exit status in IDLE. Patch by Guilherme Polo.

- Issue #17390: Display Python version on Idle title bar.
  Initial patch by Edmond Burnett.


What's New in IDLE 2.7.4?
=========================

*Release date: 2013-04-06*

- Issue #17625: In IDLE, close the replace dialog after it is used.

- IDLE was displaying spurious SystemExit tracebacks when running scripts
  that terminated by raising SystemExit (i.e. unittest and turtledemo).

- Issue #9290: In IDLE the sys.std* streams now implement io.TextIOBase
  interface and support all mandatory methods and properties.

- Issue #16829: IDLE printing no longer fails if there are spaces or other
  special characters in the file path.

- Issue #16819: IDLE method completion now correctly works for unicode literals.

- Issue #16504: IDLE now catches SyntaxErrors raised by tokenizer. Patch by
  Roger Serwy.

- Issue #1207589: Add Cut/Copy/Paste items to IDLE right click Context Menu
  Patch by Todd Rovito.

- Issue #13052: Fix IDLE crashing when replace string in Search/Replace dialog
  ended with '\'. Patch by Roger Serwy.

- Issue #9803: Don't close IDLE on saving if breakpoint is open.
  Patch by Roger Serwy.

- Issue #14958: Change IDLE systax highlighting to recognize all string and byte
  literals currently supported in Python 2.7.

- Issue #14962: Update text coloring in IDLE shell window after changing
  options.  Patch by Roger Serwy.

- Issue #10997: Prevent a duplicate entry in IDLE's "Recent Files" menu.

- Issue #12510: Attempting to get invalid tooltip no longer closes IDLE.
  Original patch by Roge

[… truncated after 8000 characters …]
```
