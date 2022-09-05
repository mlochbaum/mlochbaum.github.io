---
layout: page
title:  "Repositories"
---

This page is a resume-like overview of my open-source work, describing
the purpose and the extent of my contributions for selected projects.
Most of them also have an adequate README file, but these are intended
for a typical user of the project and may require niche knowledge (e.g.
of J) to understand.

### [BQN](https://mlochbaum.github.io/BQN) (BQN, mainly)
BQN is my second major programming language, driven by the frustration
that no one seems to have captured the appeal of
[APL](https://en.wikipedia.org/wiki/APL_(programming_language)) in a
modern design with things like closures and namespaces. Some
[problems](https://mlochbaum.github.io/BQN/commentary/problems.html)
notwithstanding, I consider BQN a success on these grounds already, and
it's gathered a small community of users.

I implemented as much of BQN as practical in the language itself, making
it easy to port to new platforms. The compiler is array-based, advancing
the methods used in [Co-dfns](https://github.com/Co-dfns/Co-dfns). I've
implemented the easy Javascript VM, but a few programmers have taken up
the challenge of hosting BQN in lower-level languages. The main offline
implementation, [CBQN](https://github.com/dzaima/CBQN), is mostly
[dzaima](https://github.com/dzaima)'s work.

I've written the documentation, specification, and tutorials,
including a markdown processor in BQN to build the website and BQN code
to generate the diagrams. But I must credit
[razetime](https://github.com/razetime) for all the help... you know,
the [help](https://mlochbaum.github.io/BQN/help/index.html) pages for
primitives you get if you right-click one of the symbols buttons.

#### [bqn-libs](https://github.com/mlochbaum/bqn-libs/)
Miscellaneous BQN utilities, and the closest thing it has to a standard
library right now.

#### [BQNcrate](https://mlochbaum.github.io/bqncrate)
To make learning BQN easier, I cloned Adám Brudzewsky's
[APLcart](https://github.com/abrudz/aplcart), translating many APL
examples to BQN and adding other snippets.

### [Singeli](https://github.com/mlochbaum/Singeli) (BQN)
A domain-specific language for building fast array language algorithms.
Designed in collaboration with [dzaima](https://github.com/dzaima), who
built an initial Java implementation. The current implementation is my
rewrite in BQN.

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
it's now a popular feature of the site and used by over 20 other
measurers to share their own data. In addition to the README, this
project has pretty extensive
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

### [BQNoise](https://github.com/mlochbaum/BQNoise) (BQN)
Utilities for music mixing, mastering, synthesis, and sequencing in
BQN. Documented only in comments in the source files. My tracks
[on Bandcamp](https://lochbaum.bandcamp.com/) have been produced in J up
to 2021 and BQN after.

#### [Music](https://github.com/mlochbaum/Music) (BQN)
Framework and source for synthesized music.

#### [BQN Musician](https://mlochbaum.github.io/BQN-Musician/index.html) (BQN)
Teaches music using BQN. My intention was to focus on programming
synthesized music, but so far I've only written some pages on the theory
of scales.

#### [JSound](https://github.com/mlochbaum/JSound) (J)
The older utilities in J, which I have now left behind.

### Sorting (C, Singeli)
I've done some research on modern sorting algorithms for CPU-native
types (that is, integers and floats). I keep notes on
[this page](https://mlochbaum.github.io/BQN/implementation/primitive/sort.html).
My main focus is now on
[Singeli Sort](https://github.com/mlochbaum/SingeliSort), a many-way
hybrid with the goal of combining the advantages of as many known
methods as possible. I've also made minor contributions to
[fluxsort](https://github.com/scandum/fluxsort) and published some
initial research for Singeli Sort as
[distribution crumsort](https://github.com/mlochbaum/distcrum).

#### [Robin Hood Sort](https://github.com/mlochbaum/rhsort) (C)
A new distribution sorting algorithm that beats all other methods I know
of to sort 1e5 or fewer uniformly random 4-byte elements. Its
performance gets better or worse based on the clumpiness of the input
distribution.

### [JtoLaTeX](https://github.com/mlochbaum/JtoLaTeX) (J)
The coolest J code I've written, in my opinion: a half-compiler,
half-preprocessor to create LaTeX using J code. It replaces J operations
with symbolic counterparts to build a syntax tree, and then turns the
tree into LaTeX code. A particular design goal is to make the output
code look natural even when the input is idiomatic J, so it uses
knowledge about order of operations and mathematical convention to
parenthesize only when necessary. Addons provide other utilities like
matrix handling, uncertainty calculation, greek and other symbols, and
set notation. Base code and the more important addons are well
documented in the `doc` folder.

### [htmllint](https://github.com/htmllint/htmllint) (Javascript)
A school project that I and three other students designed for a class at
UNC, with input from a small team at IBM.

### J programming language (C)
I made some contributions to the J source code around 2016 and have
since stopped (I am now using BQN rather than J for my own programming
when possible). Commits scattered across:

- [jsource](https://github.com/jsoftware/jsource): the official Github
  mirror of J's source.
- [unbox](https://github.com/iocane/unbox): a fork of the J source code.
  I prefer to work with it over the official J source since the build
  system is nicer, and my changes appear here first.
- [openj/core](https://github.com/mlochbaum/core): defunct. I keep it
  around because there are still some changes which I have not added to
  unbox.
