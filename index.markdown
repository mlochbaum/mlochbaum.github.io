---
layout: page
title:  "Repositories"
---

This page is a resume-like overview of my open-source work. It describes
the purpose of each project and the extent of my contributions. Most
projects also have an adequate README file, but these are intended for a
typical user of the project and may require niche knowledge (e.g. of J)
to understand.

## Personal projects

All code designed and written by me.

### [BQN](https://mlochbaum.github.io/BQN) (BQN, mainly)
BQN is my second major programming language, driven by the frustration
that no one seems yet to have built a "sensible"
[APL](https://en.wikipedia.org/wiki/APL_(programming_language))
derivative: one that maintains the core array programming ideas but
accounts for well-understood best practices in array theory and general
programming language design. K is perhaps the nearest fit aside from the
unmaintained A+, but it doesn't use multidimensional arrays at all, and
doesn't make outer scopes visible from inner ones, leaving a lot to be
desired by these criteria. BQN is not without
[problems](https://mlochbaum.github.io/BQN/problems.html) but seems to
do pretty well at the basics.

The BQN implementation uses the array-based compiler paradigm pioneered
by [Co-dfns](https://github.com/Co-dfns/Co-dfns), extending its scope
from only the core compiler to scanning, parsing, and code generation as
well. The documentation is also converted from markdown to HTML using
similar techniques. Because so much of the language is self-hosted, it
is very easy to port to new platforms, with the drawback that so many
implementation layers leads to a very slow runtime (improvements to the
compiler can probably fix this, with substantial effort).

### [ILanguage](https://github.com/mlochbaum/ILanguage) (C)
I is an experimental (avant-garde, even) programming language inspired by
J. I began creating it after the stunning realization that my two favorite
features of J---rank and forks---were actually the same concept! A paper
describing this idea, a generalization of what Haskell calls the Functor
typeclass, is shown
[in the I repository](https://github.com/mlochbaum/ILanguage/blob/master/doc/BuiltInMapping/BuiltInMapping.pdf).
It assumes no knowledge of any specific language. The language uses a
number of other interesting ideas which are described in its documentation
and guided examples.

Some features of the implementation include:

- Memory management implemented with reference counts.
- A soft-typing framework built into the language. Any type can be a
  combination of elementary types, in which case values of that type are
  type-value pairs.
- JIT compilation targetting x86 directly for pretty large portions of
  the language.

### [CrinGraph](https://github.com/mlochbaum/CrinGraph) (Javascript)
Headphone reviewer Crinacle had measurements of hundreds (like, a lot of
hundreds) of in-ear monitors with no easy way to put two of them in the
same graph. I volunteered to make a comparison tool to do just this, and
it's now a popular feature of an increasingly popular site, with audio
enthusiasts using the screenshot tool to share nicely labelled
comparisons on a daily basis. In addition to the README, this project
has pretty extensive
[documentation](https://github.com/mlochbaum/CrinGraph/blob/master/Documentation.md)
which really should stand on its own but you're obviously here to read
about me so I'll get in a few bullet points worth of bragging that don't
belong in the docs:

- That smoothing spline's no easy feat. I wrote my own diagonal LDL
  decomposition and solver. The results are noticeably cleaner and more
  faithful than typical octave smoothing.
- Normalizing the headphones requires solving what volume would give you
  a specific target loudness. How to find this? Newton's method. I took
  the derivative of ISO 226:2003.

Crinacle helped guide the design, and I also took input from Discord
user space_wadet, who is a professional UI designer.

### [JtoLaTeX](https://github.com/mlochbaum/JtoLaTeX) (J)
This is a half-compiler, half-preprocessor which creates LaTeX using J
code. It replaces J operations with symbolic counterparts to build a
syntax tree, and then turns the tree into LaTeX code. A particular design
goal is to make the output code look natural even when the input is
idiomatic J. The converter uses knowledge about order of operations and
mathematical convention to parenthesize only when necessary, and it is
very rare to need to add or remove parentheses while using JtoLaTeX.
Addons provide other utilities like matrix handling, uncertainty
calculation, greek and other symbols, and set notation.

The base code and the more important addons are well documented in the
`doc` folder.

### [JSound](https://github.com/mlochbaum/JSound) (J)
These are the utilities I use for music mixing and mastering, as well as
some other tools for working with sound. Features include a tool for
reading and writing wave files, a large collection of IIR filters, and
sound synthesis tools.

Since this is more of a library than an application, documentation is
provided only in the form of comments in the source files.

### [JScripts](https://github.com/mlochbaum/JScripts) (J)
Various J scripts not large enough to merit an entire repository.

### [vim-earl-grey](https://github.com/mlochbaum/vim-earl-grey) (Vimscript)
Earl Grey is a compile-to-Javascript language with (in my opinion) a very
elegant design. I hope to work with it more in the future. This repository
contains vimscript code for highlighting it. Harder than it sounds, since
the grammar used for highlighting is far from context-free!


## Collaborations

Projects that I have contributed to significantly. My contributions are
noted.

### [htmllint](https://github.com/htmllint/htmllint) (Javascript)
A school project that I and three other students designed for a class at
UNC, with input from a small team at IBM. I am now the sole active
maintainer. This does not mean I want to work in web dev.


## Forks

Projects that I have changed, but only to a small extent.

### J programming language (C)
I made some contributions to the J source code around 2016 and have
since stopped (I am now using BQN rather than J for my own programming
when possible).

- [jsource](https://github.com/jsoftware/jsource): the official Github
  mirror of J's source.
- [unbox](https://github.com/iocane/unbox): a fork of the J source code.
  I prefer to work with it over the official J source since the build
  system is nicer, and my changes appear here first.
- [openj/core](https://github.com/mlochbaum/core): defunct. I keep it
  around because there are still some changes which I have not added to
  unbox.

### [exafmm](https://github.com/mlochbaum/exafmm) (C++)
A project which aims to unify research on the fast multipole method so
that variations on the algorithm (in particular, different kernels) are
easily comparable. I made several modifications to exafmm for my master's
thesis and am working on merging some of them back in.

### [st](https://github.com/mlochbaum/st) (C)
The terminal I use. The only significant change from the code distributed
by suckless is the addition of xft font rendering.
