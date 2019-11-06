---
layout: default
permalink: /llvm
---
# LLVM

The [LLVM](https://llvm.org) library facilitates the generation of native code on many platforms. Many compilers (e.g., clang, swift and rustc) rely on LLVM in their code generation phase. LLVM may also be used to create a JIT interpreter. 

API bindings for accessing the library's functionality exist for a number of languages beyond C++ and C. The C binding is a thin shim over the native C++ API. The bindings for other languages typically are FFI's into the C binding. The API names are usually very similar between bindings.

A compiler's back-end code generator:

* Translates the language's final IR into LLVM IR. Most commonly, a binary, in-memory representation of the LLVM IR is built using the API. However, it is also possible to generate the LLVM IR as a text file, and then use LLVM tools to perform the rest of the processing.
* Optimizes the LLVM IR. The LLVM library offers [many helpful optimization passes](https://llvm.org/docs/Passes.html) that can be chosen.
* Translates the LLVM IR into the target's native assembler (text) or object file format.
* (optionally) Invokes the appropriate linker to create a target-specific library or an executable program.

## Resources for Learning

LLVM is quite comprehensive, rich and helpful. However, its richness can make it feel intimidating to learn. The following resources can help:

* [LLVM Tutorial](https://llvm.org/docs/tutorial/index.html). The tutorial walks through (and provides all the C++ code for) building a compiler for the toy language Kaleidoscope. This covers a lot of the basic concepts.
* [LLVM Language Reference Manual](https://llvm.org/docs/LangRef.html). This provides a comprehensive description of all the semantics for the LLVM IR. Although its examples demonstrate the text form of the IR, the semantics (and the names for them) are helpful to know even when building IR using the API.
* [Mapping High-Level Constructs to LLVM IR](https://media.readthedocs.org/pdf/mapping-high-level-constructs-to-llvm-ir/latest/mapping-high-level-constructs-to-llvm-ir.pdf). This offers many samples of LLVM IR code suitable for implementing a variety of language abstractions.
* Finding the name for a C API can usually be found by searching the Core.h include file in the C binding's include folder (llvm-c).
* It can save time sometimes to look at Github repositories to see how other language compilers use the LLVM APIs (for example: [here](https://github.com/jondgoodwin/cone/tree/master/src/c-compiler/genllvm)).

## Caveats

Despite the backing and dependencies of major players (Apple, Mozilla, etc.), use of the open-source LLVM is at your own risk. Historical experience suggests caution is warranted in these areas:

* **Documentation**. After you get past the tutorial, the documentation is succinct and reference-oriented. Don't expect any recipes or advice on solving common problems. For example, the documentation lists the optimization passes, but provides precious little information about what they do, which to choose and what order to perform them in. This [nice trick](https://stackoverflow.com/questions/14608250/how-can-i-find-the-size-of-a-type) for calculating the sizeof a type is also undocumented. Be prepared to rely on Google search, what other compilers do, and even the LLVM source code to obtain answers to some of your questions.
* **IR error messages**. If you make a mistake when using the API bindings to dynamically generate LLVM IR, the library is likely to simply generate a compile-ending exception. It's up to you to use your favorite debugger and diagnostic magic to figure out what you did wrong based on the very brief "error message" that accompanies the exception.
* **Version Upgrades**. Upgrade LLVM versions only as necessary, as version upgrades historically have included breaking changes, some of which are silent and undocumented. When you do elect to upgrade, do some code coverage metrics on your test suite first.
* **Garbage Collection**. Don't expect much help, if any, from LLVM with regard to tracing garbage collection mechanisms. It should not be a surprise that it is not a priority, given that C, Swift and Rust don't use a tracing GC and have no near-term plans to add such support. Be aware that while there are features in place in LLVM that are intended to make GC implementation possible, they are not exercised by any of the major consumers of LLVM as of this writing. As such, there is a major gap between the theoretical capabilities of LLVM as a GC-enabled platform, and the practical realities of what has been built and brought to production quality/robustness.
* **Generating Executable Binaries**. The most polished route to executable generation in LLVM is to use either the platform linker (gold, link.exe) or to rely on `lld` to do linking for you. This experience is pretty solid and has the advantage of being well-tested. However, there are situations that are much less polished (such as generating fully debuggable programs on Windows using LLD, and pretty much anything with Wasm). LLVM does provide a lot of infrastructure but occasionally you'll have to do a moderate amount of plumbing to make it all work.

## Tips for Installing LLVM

Although the LLVM website provides excellent detailed installation instructions, it can be valuable to know:

* Windows users may want to spend some time planning ahead for your installation before downloading/generating anything. CMake (the tool used to generate Visual Studio projects to build LLVM) can do a lot of things so if you're not familiar with it already, this is an excellent opportunity to learn about the options it gives you. Things to consider include how you will install multiple versions of LLVM, where the source and binaries will live, and how you will configure your LLVM-consuming project(s) to point to those locations. For Windows, one needs to download the full LLVM source code and [build it from that](https://llvm.org/docs/GettingStartedVS.html). Once CMake has created the bin folder, it will contain a Microsoft Visual Studio .sln file, enabling LLVM to be built using the VS IDE. The source code for the Kaleidoscope tutorial is included as part of the source. These project files are very useful for determining the massive list of LLVM libs that need to be included as part of the linkedit.
* On many Unix-based operating systems, the typical package manager (e.g., debian's apt-get) can be used to install "llvm-dev". If the clang compiler or linkeditor are desired, those must be installed as separate packages.

## WebAssembly support

LLVM does include an experimental code generator for [WebAssembly](https://www.reddit.com/r/ProgrammingLanguages/wiki/gen/webassembly). However, since this generator is experimental, it is not built as part of the standard build process. The way you ask for it is by adding -DLLVM_EXPERIMENTAL_TARGETS_TO_BUILD=WebAssembly to your CMake invocation. Once built, you can generate WebAssembly code using the target triple of "wasm32-unknown-unknown-wasm".
