# PGF More Pages

This is an extension of the `pgfpages` package that is made available through
the TikZ/PGF package.
The key addition is the ability to split a number of *logical* pages over a
number of *physical* pages.
The original package only allows consideration of one physical page at a time.

# Installation

Put the file `pgfmorepages.sty` somewhere that TeX can find it.

# Usage

Usage is the same as, and is compatible with, `pgfpages`.  In your preamble
put:

~~~
\usepackage{pgfmorepages}
~~~

Note that this is a replacement for `pgfpages` so will complain if that is
already loaded.

Then choose a layout via

~~~
\pgfpagesuselayout{5 index cards}
~~~

exactly as for `pgfpages`.  The layouts for `pgfpages` are available for
`pgfmorepages` as are several new ones.

# Predefined Layouts

* `rounded corners`
* `resize to`
* `two screens with lagging second`
* `two screens with optional second`
* `2 on 1`
* `4 on 1`
* `8 on 1`
* `16 on 1`
* `4 on 2, odd then even`
* `4 on 2, even then odd`
* `4 on 2, book format`
* `8 on 4, book format`
* `8 on 4, book format, reverse second, single sided`
* `5 index cards`


