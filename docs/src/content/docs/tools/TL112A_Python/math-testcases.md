---
title: "Python Engineering Utilities — math testcases"
description: "Converted Text Note / Report from math_testcases.txt (TXT, 15 KB)."
---

:::note
Converted from `TL112A_Python/tools/Lib/test/math_testcases.txt` (Text Note / Report; original TXT, about 15 KiB). Text below is extracted automatically; layout, images, and review mark-up from the original are not preserved.
:::

[Back to TL112A_Python](./)

*Conversion method: ver batim transcription.*

```text
-- Testcases for functions in math.
--
-- Each line takes the form:
--
-- <testid> <function> <input_value> -> <output_value> <flags>
--
-- where:
--
--   <testid> is a short name identifying the test,
--
--   <function> is the function to be tested (exp, cos, asinh, ...),
--
--   <input_value> is a string representing a floating-point value
--
--   <output_value> is the expected (ideal) output value, again
--     represented as a string.
--
--   <flags> is a list of the floating-point flags required by C99
--
-- The possible flags are:
--
--   divide-by-zero : raised when a finite input gives a
--     mathematically infinite result.
--
--   overflow : raised when a finite input gives a finite result that
--     is too large to fit in the usual range of an IEEE 754 double.
--
--   invalid : raised for invalid inputs (e.g., sqrt(-1))
--
--   ignore-sign : indicates that the sign of the result is
--     unspecified; e.g., if the result is given as inf,
--     then both -inf and inf should be accepted as correct.
--
-- Flags may appear in any order.
--
-- Lines beginning with '--' (like this one) start a comment, and are
-- ignored.  Blank lines, or lines containing only whitespace, are also
-- ignored.

-- Many of the values below were computed with the help of
-- version 2.4 of the MPFR library for multiple-precision
-- floating-point computations with correct rounding.  All output
-- values in this file are (modulo yet-to-be-discovered bugs)
-- correctly rounded, provided that each input and output decimal
-- floating-point value below is interpreted as a representation of
-- the corresponding nearest IEEE 754 double-precision value.  See the
-- MPFR homepage at http://www.mpfr.org for more information about the
-- MPFR project.


-------------------------
-- erf: error function --
-------------------------

erf0000 erf 0.0 -> 0.0
erf0001 erf -0.0 -> -0.0
erf0002 erf inf -> 1.0
erf0003 erf -inf -> -1.0
erf0004 erf nan -> nan

-- tiny values
erf0010 erf 1e-308 -> 1.1283791670955125e-308
erf0011 erf 5e-324 -> 4.9406564584124654e-324
erf0012 erf 1e-10 -> 1.1283791670955126e-10

-- small integers
erf0020 erf 1 -> 0.84270079294971489
erf0021 erf 2 -> 0.99532226501895271
erf0022 erf 3 -> 0.99997790950300136
erf0023 erf 4 -> 0.99999998458274209
erf0024 erf 5 -> 0.99999999999846256
erf0025 erf 6 -> 1.0

erf0030 erf -1 -> -0.84270079294971489
erf0031 erf -2 -> -0.99532226501895271
erf0032 erf -3 -> -0.99997790950300136
erf0033 erf -4 -> -0.99999998458274209
erf0034 erf -5 -> -0.99999999999846256
erf0035 erf -6 -> -1.0

-- huge values should all go to +/-1, depending on sign
erf0040 erf -40 -> -1.0
erf0041 erf 1e16 -> 1.0
erf0042 erf -1e150 -> -1.0
erf0043 erf 1.7e308 -> 1.0

-- Issue 8986: inputs x with exp(-x*x) near the underflow threshold
-- incorrectly signalled overflow on some platforms.
erf0100 erf 26.2 -> 1.0
erf0101 erf 26.4 -> 1.0
erf0102 erf 26.6 -> 1.0
erf0103 erf 26.8 -> 1.0
erf0104 erf 27.0 -> 1.0
erf0105 erf 27.2 -> 1.0
erf0106 erf 27.4 -> 1.0
erf0107 erf 27.6 -> 1.0

erf0110 erf -26.2 -> -1.0
erf0111 erf -26.4 -> -1.0
erf0112 erf -26.6 -> -1.0
erf0113 erf -26.8 -> -1.0
erf0114 erf -27.0 -> -1.0
erf0115 erf -27.2 -> -1.0
erf0116 erf -27.4 -> -1.0
erf0117 erf -27.6 -> -1.0

----------------------------------------
-- erfc: complementary error function --
----------------------------------------

erfc0000 erfc 0.0 -> 1.0
erfc0001 erfc -0.0 -> 1.0
erfc0002 erfc inf -> 0.0
erfc0003 erfc -inf -> 2.0
erfc0004 erfc nan -> nan

-- tiny values
erfc0010 erfc 1e-308 -> 1.0
erfc0011 erfc 5e-324 -> 1.0
erfc0012 erfc 1e-10 -> 0.99999999988716204

-- small integers
erfc0020 erfc 1 -> 0.15729920705028513
erfc0021 erfc 2 -> 0.0046777349810472662
erfc0022 erfc 3 -> 2.2090496998585441e-05
erfc0023 erfc 4 -> 1.541725790028002e-08
erfc0024 erfc 5 -> 1.5374597944280349e-12
erfc0025 erfc 6 -> 2.1519736712498913e-17

erfc0030 erfc -1 -> 1.8427007929497148
erfc0031 erfc -2 -> 1.9953222650189528
erfc0032 erfc -3 -> 1.9999779095030015
erfc0033 erfc -4 -> 1.9999999845827421
erfc0034 erfc -5 -> 1.9999999999984626
erfc0035 erfc -6 -> 2.0

-- as x -> infinity, erfc(x) behaves like exp(-x*x)/x/sqrt(pi)
erfc0040 erfc 20 -> 5.3958656116079012e-176
erfc0041 erfc 25 -> 8.3001725711965228e-274
erfc0042 erfc 27 -> 5.2370464393526292e-319
erfc0043 erfc 28 -> 0.0

-- huge values
erfc0050 erfc -40 -> 2.0
erfc0051 erfc 1e16 -> 0.0
erfc0052 erfc -1e150 -> 2.0
erfc0053 erfc 1.7e308 -> 0.0

-- Issue 8986: inputs x with exp(-x*x) near the underflow threshold
-- incorrectly signalled overflow on some platforms.
erfc0100 erfc 26.2 -> 1.6432507924389461e-300
erfc0101 erfc 26.4 -> 4.4017768588035426e-305
erfc0102 erfc 26.6 -> 1.0885125885442269e-309
erfc0103 erfc 26.8 -> 2.4849621571966629e-314
erfc0104 erfc 27.0 -> 5.2370464393526292e-319
erfc0105 erfc 27.2 -> 9.8813129168249309e-324
erfc0106 erfc 27.4 -> 0.0
erfc0107 erfc 27.6 -> 0.0

erfc0110 erfc -26.2 -> 2.0
erfc0111 erfc -26.4 -> 2.0
erfc0112 erfc -26.6 -> 2.0
erfc0113 erfc -26.8 -> 2.0
erfc0114 erfc -27.0 -> 2.0
erfc0115 erfc -27.2 -> 2.0
erfc0116 erfc -27.4 -> 2.0
erfc0117 erfc -27.6 -> 2.0

---------------------------------------------------------
-- lgamma: log of absolute value of the gamma function --
---------------------------------------------------------

-- special values
lgam0000 lgamma 0.0 -> inf      divide-by-zero
lgam0001 lgamma -0.0 -> inf     divide-by-zero
lgam0002 lgamma inf -> inf
lgam0003 lgamma -inf -> inf
lgam0004 lgamma nan -> nan

-- negative integers
lgam0010 lgamma -1 -> inf       divide-by-zero
lgam0011 lgamma -2 -> inf       divide-by-zero
lgam0012 lgamma -1e16 -> inf    divide-by-zero
lgam0013 lgamma -1e300 -> inf   divide-by-zero
lgam0014 lgamma -1.79e308 -> inf divide-by-zero

-- small positive integers give factorials
lgam0020 lgamma 1 -> 0.0
lgam0021 lgamma 2 -> 0.0
lgam0022 lgamma 3 -> 0.69314718055994529
lgam0023 lgamma 4 -> 1.791759469228055
lgam0024 lgamma 5 -> 3.1780538303479458
lgam0025 lgamma 6 -> 4.7874917427820458

-- half integers
lgam0030 lgamma 0.5 -> 0.57236494292470008
lgam0031 lgamma 1.5 -> -0.12078223763524522
lgam0032 lgamma 2.5 -> 0.28468287047291918
lgam0033 lgamma 3.5 -> 1.2009736023470743
lgam0034 lgamma -0.5 -> 1.2655121234846454
lgam0035 lgamma -1.5 -> 0.86004701537648098
lgam0036 lgamma -2.5 -> -0.056243716497674054
lgam0037 lgamma -3.5 -> -1.309006684993042

-- values near 0
lgam0040 lgamma 0.1 -> 2.252712651734206
lgam0041 lgamma 0.01 -> 4.5994798780420219
lgam0042 lgamma 1e-8 -> 18.420680738180209
lgam0043 lgamma 1e-16 -> 36.841361487904734
lgam0044 lgamma 1e-30 -> 69.077552789821368
lgam0045 lgamma 1e-160 -> 368.41361487904732
lgam0046 lgamma 1e-308 -> 709.19620864216608
lgam0047 lgamma 5.6e-309 -> 709.77602713741896
lgam0048 lgamma 5.5e-309 -> 709.79404564292167
lgam0049 lgamma 1e-309 -> 711.49879373516012
lgam0050 lgamma 1e-323 -> 743.74692474082133
lgam0051 lgamma 5e-324 -> 744.44007192138122
lgam0060 lgamma -0.1 -> 2.3689613327287886
lgam0061 lgamma -0.01 -> 4.6110249927528013
lgam0062 lgamma -1e-8 -> 18.420680749724522
lgam0063 lgamma -1e-16 -> 36.841361487904734
lgam0064 lgamma -1e-30 -> 69.077552789821368
lgam0065 lgamma -1e-160 -> 368.41361487904732
lgam0066 lgamma -1e-308 -> 709.19620864216608
lgam0067 lgamma -5.6e-309 -> 709.77602713741896
lgam0068 lgamma -5.5e-309 -> 709.79404564292167
lgam0069 lgamma -1e-309 -> 711.49879373516012
lgam0070 lgamma -1e-323 -> 743.74692474082133
lgam0071 lgamma -5e-324 -> 744.44007192138122

-- values near negative integers
lgam0080 lgamma -0.99999999999999989 -> 36.736800569677101
lgam0081 lgamma -1.0000000000000002 -> 36.043653389117154
lgam0082 lgamma -1.9999999999999998 -> 35.350506208557213
lgam0083 lgamma -2.0000000000000004 -> 34.657359027997266
lgam0084 lgamma -100.00000000000001 -> -331.85460524980607
lgam0085 lgamma -99.999999999999986 -> -331.85460524980596

-- large inputs
lgam0100 lgamma 170 -> 701.43726380873704
lgam0101 lgamma 171 -> 706.57306224578736
lgam0102 lgamma 171.624 -> 709.78077443669895
lgam0103 lgamma 171.

[… truncated after 8000 characters …]
```
