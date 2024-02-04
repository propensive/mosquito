[<img alt="GitHub Workflow" src="https://img.shields.io/github/actions/workflow/status/propensive/mosquito/main.yml?style=for-the-badge" height="24">](https://github.com/propensive/mosquito/actions)
[<img src="https://img.shields.io/discord/633198088311537684?color=8899f7&label=DISCORD&style=for-the-badge" height="24">](https://discord.gg/7b6mpF6Qcf)
<img src="/doc/images/github.png" valign="middle">

# Mosquito

____

Euclidean vectors, in contrast to scalars and arbitrary collections, represent
values in _a fixed multiple_ number of dimensions. _Mosquito_ provides a
representation of vectors, `Euclidean`, whose generic type encapsulates both
its element type and size. In some sense, a `Euclidean` can be considered a
hybrid of a `Tuple` (whose size in known) and a collection (whose elements are
homogeneous). Mosquito supports the use case of _generic programming_ with
`Euclidean` vectors, but facilitates linear algebra operations, including
working with matrices and scalar and vector products.

## Features

- representation of Euclidean vectors and matrices
- provides many common linear algebraic operations
- vectors and matrices are generically-typed
- linear algebraic operations abstract over arithmetic operations
- results are dependently-typed on inputs


## Availability Plan

Mosquito has not yet been published. The medium-term plan is to build Mosquito
with [Fury](https://github.com/propensive/fury) and to publish it as a source build on
[Vent](https://github.com/propensive/vent). This will enable ordinary users to write and build
software which depends on Mosquito.

Subsequently, Mosquito will also be made available as a binary in the Maven
Central repository. This will enable users of other build tools to use it.

For the overeager, curious and impatient, see [building](#building).

## Getting Started





## Status

Mosquito is classified as __embryotic__. For reference, Scala One projects are
categorized into one of the following five stability levels:

- _embryonic_: for experimental or demonstrative purposes only, without any guarantees of longevity
- _fledgling_: of proven utility, seeking contributions, but liable to significant redesigns
- _maturescent_: major design decisions broady settled, seeking probatory adoption and refinement
- _dependable_: production-ready, subject to controlled ongoing maintenance and enhancement; tagged as version `1.0.0` or later
- _adamantine_: proven, reliable and production-ready, with no further breaking changes ever anticipated

Projects at any stability level, even _embryonic_ projects, can still be used,
as long as caution is taken to avoid a mismatch between the project's stability
level and the required stability and maintainability of your own project.

Mosquito is designed to be _small_. Its entire source code currently consists
of 249 lines of code.

## Building

Mosquito will ultimately be built by Fury, when it is published. In the
meantime, two possibilities are offered, however they are acknowledged to be
fragile, inadequately tested, and unsuitable for anything more than
experimentation. They are provided only for the necessity of providing _some_
answer to the question, "how can I try Mosquito?".

1. *Copy the sources into your own project*
   
   Read the `fury` file in the repository root to understand Mosquito's build
   structure, dependencies and source location; the file format should be short
   and quite intuitive. Copy the sources into a source directory in your own
   project, then repeat (recursively) for each of the dependencies.

   The sources are compiled against the latest nightly release of Scala 3.
   There should be no problem to compile the project together with all of its
   dependencies in a single compilation.

2. *Build with [Wrath](https://github.com/propensive/wrath/)*

   Wrath is a bootstrapping script for building Mosquito and other projects in
   the absence of a fully-featured build tool. It is designed to read the `fury`
   file in the project directory, and produce a collection of JAR files which can
   be added to a classpath, by compiling the project and all of its dependencies,
   including the Scala compiler itself.
   
   Download the latest version of
   [`wrath`](https://github.com/propensive/wrath/releases/latest), make it
   executable, and add it to your path, for example by copying it to
   `/usr/local/bin/`.

   Clone this repository inside an empty directory, so that the build can
   safely make clones of repositories it depends on as _peers_ of `mosquito`.
   Run `wrath -F` in the repository root. This will download and compile the
   latest version of Scala, as well as all of Mosquito's dependencies.

   If the build was successful, the compiled JAR files can be found in the
   `.wrath/dist` directory.

## Contributing

Contributors to Mosquito are welcome and encouraged. New contributors may like
to look for issues marked
[beginner](https://github.com/propensive/mosquito/labels/beginner).

We suggest that all contributors read the [Contributing
Guide](/contributing.md) to make the process of contributing to Mosquito
easier.

Please __do not__ contact project maintainers privately with questions unless
there is a good reason to keep them private. While it can be tempting to
repsond to such questions, private answers cannot be shared with a wider
audience, and it can result in duplication of effort.

## Author

Mosquito was designed and developed by Jon Pretty, and commercial support and
training on all aspects of Scala 3 is available from [Propensive
O&Uuml;](https://propensive.com/).



## Name

A mosquito is a typical example of a vector: an animal that transmits a pathogen or disease.

In general, Scala One project names are always chosen with some rationale,
however it is usually frivolous. Each name is chosen for more for its
_uniqueness_ and _intrigue_ than its concision or catchiness, and there is no
bias towards names with positive or "nice" meanings—since many of the libraries
perform some quite unpleasant tasks.

Names should be English words, though many are obscure or archaic, and it
should be noted how willingly English adopts foreign words. Names are generally
of Greek or Latin origin, and have often arrived in English via a romance
language.

## Logo

The logo represents the _x_, _y_ and _z_ axes of a vector space.

## License

Mosquito is copyright &copy; 2024 Jon Pretty & Propensive O&Uuml;, and
is made available under the [Apache 2.0 License](/license.md).

