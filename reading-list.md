---
permalink: /reading-list
---
# /r/ProgrammingLanguages Reading List
This is a list of valuable resources for programming language design and implementation.

If contributing, add your resource to the appropriate section, give a short description and appropriate credit. Keep sections in alphabetical order.

# Online resources 

## Start-to-finish tutorials

* [Build Your Own Lisp](http://www.buildyourownlisp.com/) by Daniel Holden

  A book that serves both as a tutorial on C and writing a Lisp interpreter.

* [Crafting Interpreters](http://www.craftinginterpreters.com/) by Bob Nystrom (/u/munificent)
 
  An ongoing book about writing interpreters by Bob Nystrom of [Game Programming Patterns](http://gameprogrammingpatterns.com/) fame. Very comprehensive, includes code both in Java and C.

* [Let's Build a Compiler](https://compilers.iecc.com/crenshaw/) by Jack Crenshaw

  An old (1988-1995), non-technical series about writing a simple compiler in Turbo Pascal. Like most books on this topic, most of the knowledge contained within is still relevant today, though. 

## Compiler architecture

* [A Nanopass Framework for Compiler Education](http://www.cs.indiana.edu/%7Edyb/pubs/nano-jfp.pdf) - Dipanwita Sarkar, Oscar Waddell, R. Kent Dybvig

  A paper describing compilers as series of transformations in dozens of small compiler passes.

## Language design

* [Rosetta Code](http://rosettacode.org/wiki/Rosetta_Code)

  Collects solutions to the same problem in as many different programming languages as possible. Helpful for seeing how other languages handle certain tasks, and getting a better idea of what your syntax will be like.

# Books

## General compiler implementation

* [Compiler Design and Construction](https://www.amazon.com/dp/0442275366) - Arthur Pyster

  Guides the reader through implementing a Pascal compiler, explaining both the technical and practical details.

* [Compilers: Principles, Techniques, and Tools](https://www.amazon.com/dp/0321486811/) - Alfred V. Aho, Monica S. Lam, Ravi Sethi, and Jeffrey D. Ullman

  **The Dragon Book**. Classic text, but much is outdated, and a beginner won't be able to tell which.  There's more modern and approachable books, such as:

* [Engineering a Compiler](https://www.amazon.com/Engineering-Compiler-Keith-Cooper/dp/012088478X/) -  Keith Cooper, Linda Torczon

  In-depth treatment of algorithms and techniques used in a modern compiler, focused on code optimization and generation, with examples from multiple languages.

* [Modern Compiler Design](https://www.amazon.com/Modern-Compiler-Design-Dick-Grune/dp/1461446988) - Dick Grune, Ceriel Jacobs, Koen G. Langendoen, Kees van Reeuwijk, Henri Bal

  Often recommended as the more up-to-date and approachable alternative to the dragon book; along with it and Engineering a Compiler, the "holy trinity" of compiler implementation books.

* [Modern Compiler Implementation in ML](https://www.amazon.com/gp/product/0521607647) -  Andrew W. Appel 

  A complete walkthrough and discussion of implementing a robust, feature-rich compiler in ML; there's also Java and C translations.

# Software, Frameworks

* [RPython](https://rpython.readthedocs.io/en/latest/) 

  Toolchain for writing complete interpreters in a statically typed subset of Python; gives you a garbage collector and JIT interpreter for free. Used by [PyPy](http://pypy.org/), [Lever](https://github.com/cheery/lever), [Monte](https://github.com/monte-language/typhon), [Pixie](https://github.com/pixie-lang/pixie).

* [The LLVM Compiler Infrastructure Project](https://llvm.org/)

  Collection of modular and reusable compiler and toolchain technologies. Very powerful. [Additional LLVM resources](https://www.reddit.com/r/ProgrammingLanguages/wiki/gen/llvm). Major LLVM compilers: Clang, Rustc, Swift, GHC(?), Pony.

* [WebAssembly](http://webassembly.org/)

  Native assembly target for the browser. [Additional WebAssembly resources](https://www.reddit.com/r/ProgrammingLanguages/wiki/gen/webassembly).
