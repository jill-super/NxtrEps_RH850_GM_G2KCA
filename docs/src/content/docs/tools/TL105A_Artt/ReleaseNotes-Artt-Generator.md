---
title: "Architecture Tooling — ReleaseNotes Artt Generator"
description: "Converted Release Notes from ReleaseNotes_Artt_Generator.pdf (PDF, 44 KB)."
---

:::note
Converted from `TL105A_Artt/tools/ReleaseNotes_Artt_Generator.pdf` (Release Notes; original PDF, about 44 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL105A_Artt](./)

*Conversion method: automatic text extraction from the Portable Document Format.*

--- Page 1 ---
Page 1 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
BMW Package Release Notes
Artt_Generator-2.0.2
Package Status:
Released
Author:
BMW Group
Version:
2.0.2
Release Date:
23-Nov-2011

--- Page 2 ---
Page 2 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
1 Revision History
 1.0.1
 03-Oct-2008
Initial revision. CR70051, CR70068.
 1.0.2
 29-Jun-2009
Support of more BAC2.1 templates. CR70168, 
CR70166, CR70167, CR70195, CR70237, 
CR70267.
 1.0.3
 27-Oct-2009
Performance optimization CR70341.
 1.1.0
 11-Nov-2009
User friendliness and portability CR70397, 
CR70343.
 1.1.1
 27-May-2010
CR70519.
 1.2.0
 30-Jun-2010
New validation feature CR70359, CR .
 1.3.0
 11-Oct-2010
AUTOSAR 4.0 schema CR .
 2.0.0
 15-Mar-2011
Behaviour of ValueOf() changed CR71004, 
CR71005.
 2.0.1
 14-Apr-2011
Method ModuleConfAtDefRefTo() added CR71008.
 2.0.2
 23-Nov-2011
CR71146, CR71147.
 Revision
 Date
 Remarks

--- Page 3 ---
Page 3 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
2 Package Enumeration Scheme
3 Package Description
artt is a command line application allowing to generate text files, including source code, from 
AUTOSAR descriptions. As input data artt uses a template file describing static content and 
structure of the desired output and one or more AUTOSAR descriptions, which are serving as 
provider for dynamic content. Since AUTOSAR descriptions are XML files, templates for artt 
typically use XPATH expressions referring to certain elements in the input file.
This package is maintained by BMW AUTOSAR Core Support, via Request Tracker (https://sc-
support.bader-muenchen.de/rt3/) or telephone hotline (+49-89-382-32233).
Every package carries a 3-digit version number. The following table explains how compatibility 
between versions can be determined from the version number:
 Minor Version
 ĺ
A new feature was added. New version is 
backwards compatible to old version.
 Major Version
 ĺ
API of package changed. Versions are not 
compatible. If the new package is used, other 
packages must be changed as well.
 Patch Version
 ĺ
A defect has been fixed. Versions are fully 
compatible.
 Changed Version
 Example
 Compatibility

--- Page 4 ---
Page 4 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
4 Revisions and Modifications
Revision 2.0.2 [Released]
Changed Files:
Compatibility:
Description of Changes:
Item
Description
CR ID:
CR Headline:
Description of Issues:
Changed Files:
Helper.tt
Compatibility:
Fully compatible
Description of Changes:
Changed the implementation to use the correct artt internal 
implicit bool operator to map a ValueNode to a bool.
Marked the helper function BoolValueOf and its wrapper Enabled
() as being obsolete since these helpers can simply be substuitted 
with core artt functions.
Item
Description
CR ID:
71147
CR Headline:
Wrong implementation of BoolValueOf
Description of Issues:
The included template utility file Helper.tt contained a helper 
function BoolValueOf. This implementation was wrong since it did 
not respect the various representations of bool-values allowed by 
the autosar schema.
Changed Files:
artt.chm
Compatibility:
Fully compatible
Item
Description
Description of Changes:
Extended the documentation of ChangeContext method in 
ArGtcBase to reflect that a call to ChangeContext(null) will 
successfully reset the context to the root context AND return false. 
(although one could expect that it returns true because the context 
change was successfull.
CR ID:
71146
CR Headline:
ARTT ChangeContext returns false when called with null as 
parameter.
Description of Issues:
Misleading documentation

--- Page 5 ---
Page 5 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
Revision 2.0.1 [Stable]
artt.chm
Changed Files:
artt.exe
Compatibility:
no restrictions to older AUTOSAR versions
Item
Description
Description of Changes:
Creates XPATH to the <c>MODULE-CONFIGURATION</c> node 
(for AUTOSAR versions before 4.0) 
or the <c>ECUC-MODULE-CONFIGURATION-VALUES</c> 
node (starting with AUTOSAR version 4.0) of the module 
configuration that is based on the module definition with the given 
shortname.
CR ID:
71008
CR Headline:
new method ModuleConfAtDefRefTo()
Description of Issues:
New method ModuleConfAtDefRefTo() added.

--- Page 6 ---
Page 6 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
Revision 2.0.0 [Stable]
Changed Files:
artt.exe
Compatibility:
Instead of writing:
boolean blub = <#= ValueOf(<xpath to BOOLEAN-VALUE>) #>
now it has to be written:
boolean blub = <#= (ValueOf(<xpath to BOOLEAN-VALUE>) == 
true ? “TRUE” : “FALSE”) #>
Item
Description
Description of Changes:
The method ValueOf() now always returns just the string found  in 
the template file without an interpretation of it.
CR ID:
71005
CR Headline:
ValueOf-Method shall not try to interprete ECUC-BOOLEAN-
VALUE
Description of Issues:
In versions less the 2 the ValueOf() method returned the string 
found in the tt-file if it was not a boolean value. In case of a 
boolean value, it retruned "TRUE" or "FALSE".
Changed Files:
artt.exe
Compatibility:
no restrictions to older AUTOSAR versions
Item
Description
Description of Changes:
Also in case of a thrown exception in template file an output file is 
generated.
CR ID:
71004
CR Headline:
artt generator shall write output file even in case of error
Description of Issues:
Also for Environment.Exit in template file an outputfile is 
generated.

[… 8 further page(s) not extracted …]
