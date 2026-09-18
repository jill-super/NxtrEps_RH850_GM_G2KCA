---
title: "Component Runtime Environment Generator Support — CHANGES"
description: "Converted Text Note / Report from CHANGES.txt (TXT, 16 KB)."
---

:::note
Converted from `TL101A_CptRteGen/tools/Sip/DaVinciConfigurator/Core/plugins/gnu.trove_3.0.3/res/CHANGES.txt` (Text Note / Report; original TXT, about 16 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL101A_CptRteGen](./)

*Conversion method: ver batim transcription.*

```text
--- 2.1.0 ---
No substantial changes.

--- 2.1.0 a3 ---
Bugs fixed:
  - [ 2685774 ] THashMap serialization bug in 2.0.4

--- 2.1.0 a2 ---
Bugs fixed:
  - [ 2166456 ] clone() for TObject<XXX>HashMap is inefficient
  - [ 2166768 ] add toString() method to maps. Thanks to Ozgur Aydinli.
  - [ 2688770 ] TxxxArrayList serializes full capacity instead of full size
  - [ 2687519 ] Primitive Lists hashCode is calculated w/o regard for order
  - Fixed issues related to removing items multiple times from TLinkedList
    and using removeFirst/Last when no items are in the list.

New Features
  - [ 2126522 ] add putAll() to the HashMaps. Thanks to Ozgur Aydinli.

--- 2.1.0 a1 ---
Bugs fixed:
  - [ 2143564 ] THashSet serialization
  - [ 1960418 ] Decorators serialization
  - [ 2127841 ] Use <Type>.valueOf on wrap/unwrap in T#K##V#HashMapDecorator

New Features:
  - Added "Dectorators" class for easier creation of decorator classes.
  - [ 2152149 ] Improve performance by avoiding Math/StrictMath (thanks to Mark Beevers)

--- 2.0.5 a1 ---
Bugs fixed:
  - [ 2037709 ] bug in .keys(<T>[]) method

New Features:
  - added keys(e[]) method to P2O maps (TIntObjectHashMap, etc.)

--- 2.0.4 ---
Bugs fixed:
  - [ 1959853 ] @return for put and putIfAbsent is incorrect

--- 2.0.4 rc1 ---
Bugs Fixed:
  - [ 1952509 ] Replace StringBuffer with StringBuilder
  - [ 1952508 ] pufIfAbsent for maps
  - [ 1955103 ] Hashing Strategy Not Retained After Serialization

--- 2.0.4 a2 ---
Bugs fixed:
  - Correct an error in TLinkedList that caused nodes to not be properly linked
    when using addAfter(T,T).

--- 2.0.4 a1 ---
Bugs fixed:
  - [ 1946240 ] THash.ensureCapacity(...) bug 

--- 2.0.3 ---
Bugs Fixed:
  - [ 1932929 ] add toString() methods to THashSet and THashMap
  - Switched to Arrays.fill (which seems to be slightly faster) for clearing 

--- 2.0.2 ---
Bugs Fixed:
  - [ 1821911 ] get(0) doesn't throw exception when TLinkedList is empty
  - [ 1800288 ] Trivial typo fixes


--- 2.0.1 ---
Bugs Fixed:
  - Fixed implementation of PArrayList.min() and .max().
  

--- 2.0.1 rc1 ---
New Features:
[ 1778999 ] Publish a source-JAR with future releases

Misc:
  - Switched version from 2.1 to 2.0.1.


--- 2.0.1 ALPHA 3 (previously: 2.1 ALPHA 3) ---
Bugs Fixed:
[ 1764177 ] bug in binary search


--- 2.0.1 ALPHA 2 (previously: 2.1 ALPHA 2) ---
New Features:
[ 1748566 ] add <T> T[] getValues(T[] a)

Bugs Fixed:
- Corrected hashcode computation for longs. Should result in better
  lookup performance.
  

--- 2.0.1 ALPHA 1 (previously: 2.1 ALPHA 1) ---

New Features:
[ 1741864 ] add TLinkedList addAfter method

Bugs Fixed:
[ 1738760 ] T*HashMap.retainEntries should suspend automatic compaction.
- Corrected hashcode computation for longs. Should result in better
  lookup performance.

Misc:
  - Added an assertion in HashFunctions to throw an assertion if a
    value of NaN is used in a lookup/insert/delete from a map.
  - Added TLinkedList.getNext() and getPrevious() methods.


--- 2.0 ---
Unchanged from 2.0rc1


--- 2.0rc1 ---

New Features:
[ 1606090 ] adjustOrPutValue
[ 1604073 ] Generate primitive stacks
[ 1632250 ] Do maps implement Iterable
[ 1670933 ] Provide access to stack native arrays
[ 1690743 ] Add subList(begin, end) to ArrayLists
Added forEach(TObjectProcedure) method to TLinkedList

Bugs Fixed:
[ 1640353 ] Generator fails on multiple file systems
[ 1676866 ] Not handling REMOVED flag correctly in TObjectHash.index(T)
[ 1642768 ] Exception removing from iterator when auto-compact occurs



--- 2.0a2 ---

New Features:
[ 779039 ] expose decorator's set/map

Bugs Fixed:
[ 1428614 ] THashMap.values().remove() can remove multiple mappings
[ 1506751 ] TxxxArrayList.toNativeArray(offset, len) is broken
[ 1606095 ] Critical Iterator Error


--- 2.0a1 ---

This release adds support for generics, which were introduced in JSE 1.5.
Starting with this release, JSE 1.5 or greater is required in order to run Trove.
Special thanks to JetBrains for their initial work providing generics support.

Also added in this release is automatic compaction, such that manually calling
compact() is no longer necessary (although it may still provide performance
benefits in certain situations). Compactions are by default
performed automatically when a certain number of removes are performed based on
the size of the set or map. The compaction factor can be specified via
THash.setAutoCompactionFactor(float) (the default compaction factor is set to
match the load factor). So, for example, if a map is created with an initial
capacity of 10 and a load factory of 0.5, a compaction will be performed after
5 removes. If a size is later grown to 1000, then a compaction will occur after
500 removes. When a set/map is rehashed, the time to next compaction is reset.
   NOTE: auto-compaction can be disabled by setting the autoCompactionFactory
      (via THash.setAutoCompactionFactor) to zero. Manually compacting a
      collection will also reset the auto-compaction counter, so that manually
      compacting more often than auto-compaction wants to occur effectively also
      disables auto-compaction. 
   NOTE: while manually calling compact() is no longer strictly necessary,
      results should always be verified in your application to ensure that
      the auto-compaction scheme and the compaction factors work well for your
      individual scenario.
      
Support for more primitve types has been introduced.

Object serialization has been changed to use Externalization. Unfortunately this
means that objects serialized with earlier versions cannot be read by this
release. The up-side is that this gives enough flexibility to ensure that we
won't need to break serialization again. The other benefit is that the output
is more efficient/compact and readable...  especially when used with XML
serialization mechanisms such as XStream.


New Features:
[ 918059 ] should rehash when below low water mark upon remove
[ 1153656 ] generics?

Bugs Fixed:
[ 1518795 ] NullPointerException in TLinkedList's removeFirst()/Last()
[ 1277703 ] make T**HashMap serializable
[ 1417563 ] TLinkedList.add(int,Object) bug
[ 1518823 ] another TLinkedList.add(int,Object) bug
[ 1461458 ] THashMap.equals(..) method is not consistent
[ 1571435 ] Error in cloning of TObjectXXXHashMap instances


--- 1.1b5 ---

Bugs fixed:
[ 1391359 ] Duplicate iteration in THashSet.toArray(Object[])
    removed the duplication
[ 1382196 ] THashMap.entrySet().retainAll()
    implemented missing methods on elements of entrySet, refactored retainAll
    to use retainEntries, which saves a bunch of allocations
[ 1378868 ] CVS has junit.jar checked in as ASCII
    flipped on '-kb' for this file
[ 1193416 ] TByteArrayList throws ArrayIndexOutOfBoundsException wrongly
    fixed off by one error


--- 1.1b4 ---

Accepted patch for feature request 926921 - adds support for short,
byte collections.  Also adds support for null object keys.  THIS
WILL BREAK SERIALIZATION.

A big thanks to Steven Lunt for putting this patch together.

Added testSerializablePrimitives unit test to validate that behavior
reported in 1113420 does work as it's supposed to.

Fixed doc problem reported in 939016

Fixed 995597, missing serial version IDs.  NOTE: THashMap, THashSet
and TLinkedList have IDs generated by serialver and are believed
to be b/w compatible.  The generated collections, however, are NOT
reverse compatible versions and so will break archived collections
created with earlier versions of trove.

Fixed 937977 -- primitive array lists were not doing a true deep clone
of the underlying array.  This is fixed


--- 1.1b3 ---

Fixed 918045 -- bug in *Decorator classes made it impossible to subclass
the decorators and make those subclasses cloneable.  Thanks to Steve
Lunt for the bug report.


--- 1.1b2 ---

Fixed 901135 -- bug in T*Hash.insertionIndex() methods that prevented
us from reclaiming the very first REMOVED slot if that's what the
first hash landed upon.  In applications that do lots

[… truncated after 8000 characters …]
```
