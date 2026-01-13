# jj\_big_numbers
An Eiffel library for manipulating arbitrarily large numbers.  It implements addition, subtraction,  multiplication and division.

This library depends on the [JJ\_NATURAL](http://github.com/boxer41a/jj_naturals) classes, which adds a class between NUMERIC and the NATURAL\_xxx classes.  Through generic anchors using JJ_NATURAL, the top level class, [jj\_big\_natural](http://github.com/boxer41a/jj_big_numbers/classes/jj_big_natural.e), allows developement and testing with 8-bit numbers instead of 32- or 64-bit numbers, which are too hard to manually trace.

To use the example ecf files, checkout the library to a location identified by the envirnment variable "JJ_GITHUB".

### Demo/Test/Timing
The demo program and the timeing tests use the [Eiffel_GMP](https://github.com/colin-adams/eiffel_gmp) library, which depends on [The GNU Multiple Precision Arithmetic Library](https://gmplib.org), in order to compare results.  The timing tests also depend on [JJ\_TEMPORAL classes](http://github.com/boxer41a/jj_temporal).


The timing tests compare execution times for this library to the execution times of corresponding routines in "eiffel_gmp" (an Eiffel binding to the GNU Multiple Precision Arithmetic Library).

In my ecf files I used environment variable "JJ_OTHER" to identify the file-system location for non-eiffel libraries or eiffel libraries that depend on non-eiffel libraries.

### Problems
Some tests fail with segmentation fault.  I think this is caused by a bug in the compiler.  See the newsgroup [message](https://groups.google.com/g/eiffel-users/c/Ha7_Ig8FsAM/m/cHuue2-9BwAJ) from Alexander quoted here: 

> Indeed, there is a bug in C code generation for a particular combination of anchored types and generic polymorphism, involving redeclaration of a reference type into an expanded one. We were trying to find a reasonable workaround, but according to your comments to the messages from the users of the mailing list, there is no way to get rid of the anchored type and to keep just the generic one. With such restrictions, the suggestion to stick to reference types as actual generic parameters in your classes seems most appropriate until the bug is fixed.