# PGF More Pages

This is an extension of the `pgfpages` package that is made available through
the TikZ/PGF package.
The key addition is the ability to split a number of *logical* pages over a
number of *physical* pages.
The original package only allows consideration of one physical page at a time.

Another extra feature is that it is possible to change the layout
mid-document with a new use of `\pgfpagesuselayout`.
In particular, the layout `1 on 1` effectively resets the layout back
to normal (in point of fact, it maintains the `pgfpages` mechanism but
just puts one logical page on each physical page).

I've used this package a few times in [answers on
TeX-SX](https://tex.stackexchange.com/search?q=pgfmorepages) so that's
a useful source of examples.

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

I've started putting extra layouts in a separate file so if you want to
use one of these layouts, you need to issue the following command after
loading the package and before using one of these layouts.  To see
which layouts are "extra", see below.

~~~
\pgfmorepagesloadextralayouts
~~~

To choose a layout, use:

~~~
\pgfpagesuselayout{5 index cards}
~~~

exactly as for `pgfpages`.  The layouts for `pgfpages` are available for
`pgfmorepages` as are several new ones.

## Layout Options

I've added another option to the set of keys that can be specified in
the layout command:

~~~
\pgfpagesuselayout{2 on 1}[border code=\pgfusepath{draw}]
~~~

When `pgf(more)pages` sets up a logical page, it puts a rectangle path
around it.
The layout specification can use that path in some way.
This option exposes that to the user at call time as well (providing
the layout specification allows for it, most have been adapted to do so).

# Predefined Layouts

The available layouts are as follows.

## PGFPages

These are from the original `pgfpages` package:

* `rounded corners`
* `resize to`
* `two screens with lagging second`
* `two screens with optional second`
* `2 on 1`
* `4 on 1`
* `6 on 1`
* `8 on 1`
* `16 on 1`

## PGFMorePages

These are loaded by default:

* `4 on 2, odd then even`
* `4 on 2, even then odd`
* `4 on 2, book format`
* `8 on 4, book format`
* `8 on 4, book format, reverse second, single sided`
* `5 index cards`

## Extra Layouts

These are loaded via the command
`\pgfmorepagesloadextralayouts`:

* `1 repeated 4 times on 1`
* `repeated 2-up`
* `repeated 4-up`
* `1 on 1`

