## “Purity”

Mathematical functions have often been described as “pure” in terms of some specified variables. e.g.:

> the first term is a pure function of x and the second term is a pure function of y

Because of this, I think that finding a true “first” occurrence will be near-impossible.

For programming languages, a little searching shows that [Ada 95](http://www.adacore.com/multimedia/Ada95_RM_HTML/RM-10-2-1.html) (`pragma Pure`), [High Performance Fortran](http://www.vcpc.univie.ac.at/information/mirror/HPFF/hpf1/hpf-v10/subsubsection2_5_3_1_1.html) (1993) (`PURE`) and [VHDL-93](http://www.vhdl.org/isac/IRs-VHDL-93/IR1083.txt) (`pure`) all contain formal notions of what 'pure functions' are.

Haskell (1990) is fairly obvious, but purity isn't explicit. GCC's C has [various function attributes](http://gcc.gnu.org/onlinedocs/gcc/Function-Attributes.html) for various differing levels of 'pure'.

A couple of books: [*Rationale for the C programming language*](http://books.google.com/books?id=yxLISD0TAbEC&lpg=PA48&dq=%22pure%20function%22&pg=PA48#v=onepage&q=%22pure%20function%22&f=false) (1990) uses the term, as does [*Programming Languages and their Definitions*](http://books.google.com/books?id=mCoN_I5vjX0C&lpg=PA139&dq=%22a%20pure%20function%22&pg=PA139#v=onepage&q=%22a%20pure%20function%22&f=false) (1984). However, both apparently only use it once! *Programming the IBM Personal Computer, Pascal* (also 1984) uses the term, but it isn't clear from Google's restricted view whether or not the Pascal compiler had support for it. (I suspect not.)

An interesting note is that "Preliminary Green" (one of four candidates for Ada), [actually had a fairly strict 'function' definition](http://www.adahome.com/LRM/83/Rationale/Text/ratl-c8.hlp) – even memory allocation was disallowed. However, this was dropped before it became Ada, where functions can have side-effects (I/O or global variables), but can't modify their arguments.

[C28-6571-3](http://www.bitsavers.org/pdf/ibm/360/pli/C28-6571-3_PL_I_Language_Specifications_Jul66.pdf) (the first PL/I reference manual, written before the compiler) shows that PL/I had support for pure functions, in the form of the `REDUCIBLE` (= pure) attribute, as far back as 1966 - when the compiler was first released.

This last document specifically notes that it includes `REDUCIBLE` as a new change since document C28-6571-2. So REDUCIBLE, which is possibly the first incarnation of formal pure functions in programming languages, appeared somewhere between January and July 1966.

The earliest instance of "pure function" on Google Groups in this sense [is from 1988](http://groups.google.com/group/comp.lang.c/browse_thread/thread/9ca30dbe495fe14/1afe80f3eef4a3fc?q=%22pure+function%22#1afe80f3eef4a3fc), which easily postdates the book references.

### Timeline

* Jan–Jul 1966: PL/I (`REDUCIBLE`)
* 1978: Preliminary Green (`function`)
* 1993: High Performance Fortran (`PURE`), VHDL-93 (`pure`)
* 1995: Ada 95 (<code><strong>pragma</strong> Pure</code>)
* 1990: Haskell (all functions)
