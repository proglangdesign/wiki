---
permalink: /resources
---
# Resources
Also check out the [/r/ProgrammingLanguages Reading List](/wiki/reading-list).

## Unsorted
* [Live Functional Programming with Typed Holes](https://arxiv.org/pdf/1805.00155.pdf)
* [A tour of metaprogramming models for generics](http://thume.ca/2019/07/14/a-tour-of-metaprogramming-models-for-generics/)
* [Lambda Calculus: Then & Now](https://turing100.acm.org/lambda_calculus_timeline.pdf)
* [Co-designing a Type system and a Runtime](https://www.infoq.com/presentations/pony-type-system/)
* [Visual Programming Codex](https://github.com/ivanreese/visual-programming-codex)
* [Programming and Programming Languages](https://papl.cs.brown.edu/2019/Introduction.html)
* [Programming in the twenty-first century](https://prog21.dadgum.com/archives.html)
* [Simple Made Easy](https://www.infoq.com/presentations/Simple-Made-Easy/)
* [Fun treasure trove of interesting ideas on OO, Type Theory, Databases, etc. on Luca Cardelli's site:](http://lucacardelli.name/indexPast.html)
* [Newton vs the machine: solving the chaotic three-bodyproblem using deep neural networks](https://arxiv.org/pdf/1910.07291.pdf)
* [Writing a Concatenative Programming Language: Introduction](https://suhr.github.io/wcpl/intro.html),
  [Comma is a Product: the Algebra of Concatenative Programming](https://suhr.github.io/papers/calg.html),
  [Cancellation Based Pattern Matching](https://suhr.github.io/papers/cpat.html)
* [Compiler Errors for Humans: Rethinking the terminal UX in Elm 0.15.1](https://elm-lang.org/news/compiler-errors-for-humans),
  [The Syntax Cliff: Teaching syntax with Elm 0.19.1](https://elm-lang.org/news/the-syntax-cliff)
* [Coinductive Definition: A Counterpoint to Inductive Definition](https://www.cs.ubc.ca/~rxg/cpsc509/06-coinduction.pdf): Ron Garcia's (PL prof at UBC) notes for introducing conduction.
* [Debugging Dynamically Generated Code (Reflection.Emit)](https://blogs.msdn.microsoft.com/jmstall/2005/02/03/debugging-dynamically-generated-code-reflection-emit/): You target MSIL and you are writing your compiler in a .NET langauge you pretty much get debugging for free.
* [A neat talk about some of the implementation tricks in Chez Scheme](https://www.youtube.com/watch?v=BcC3KScZ-yA)
* [Parse, don't validate](https://lexi-lambda.github.io/blog/2019/11/05/parse-don-t-validate/)

## Compilers & Interpreters & Stuff
### Unsorted
* [Can Logic Programming Execute as Fast as Imperative Programming?](https://www.info.ucl.ac.be/~pvr/Peter.thesis/Peter.thesis.html) The thesis on Aquarius Prolog. It's a paper fantastically useful to try and understand the dirty parts of logic languages.
* [Portable Executable (PE) and Common Object File Format (COFF)](https://docs.microsoft.com/en-us/windows/desktop/Debug/pe-format)
* [Generating C code that people actually want to use](http://jonathan.protzenko.fr/2019/01/04/behind-the-scenes.html)
* [Hardware Exceptions](https://docs.microsoft.com/en-us/cpp/cpp/hardware-exceptions?view=vs-2017)
* [Structures in jemalloc](https://medium.com/iskakaushik/eli5-jemalloc-e9bd412abd70), and in more detail, <https://media.blackhat.com/bh-us-12/Briefings/Argyoudis/BH_US_12_Argyroudis_Exploiting_the_%20jemalloc_Memory_%20Allocator_WP.pdf>
* [Beam bytecode compilation for examples](http://gomoripeti.github.io/beam_by_example/)
* [Checking Beliefs in Dynamic Networks](https://www.microsoft.com/en-us/research/publication/checking-beliefs-in-dynamic-networks/): May be useful for verifying compiler correctness.
* [Latency and throughput of x86 ISA](http://uops.info/table.html)
* [Simple, direct, AST to ASM translation](https://ijzerbaard.github.io/Direct-AST-to-ASM-translation/)
* [What's new in CPUs since the 80s?](https://danluu.com/new-cpu-features/)
* [What is Zig's Comptime](https://kristoff.it/blog/what-is-zig-comptime/)
* ["Optimization" based on undefined behavior hurts performance](https://c9x.me/compile/bib/ubc.pdf)
* [Software optimization resources](https://www.agner.org/optimize)

### More resources (collections)
* [The Bootstrapping Wiki](https://bootstrapping.miraheze.org/wiki/Main_Page): Building up compilers and interpreters from nothing.
* [Awesome Compilers](https://github.com/aalhour/awesome-compilers): A curated list of resources on compilers, interpreters, and runtimes.
* [GRIN: a compiler back-end for lazy and strict functional languages, related articles thread](https://github.com/grin-compiler/grin/issues/1)

### Tutorials
* [Crafting Interpreters](http://www.craftinginterpreters.com/)
* [How to implement a programming language in JavaScript](http://lisperator.net/pltut/) small little tutorial
* [Building a Compiler with MLIR](https://www.youtube.com/watch?v=cyICUIZ56wQ)
* [Let's Build A Simple Interpreter. Part 1.](https://ruslanspivak.com/lsbasi-part1/)
* [Writing a Compiler in Rust](https://thume.ca/2019/04/18/writing-a-compiler-in-rust/)
* [University of Salzburg - Introduction to Compiler Construction](https://vimeopro.com/user12798068/university-of-salzburg-introduction-to-compiler-construction): A great resource to learn parsing and code generation.
* [Compiling a Functional Language Using C++](https://danilafe.com/blog/00_compiler_intro/)
* [Stanford CS 143 Compilers](https://web.stanford.edu/class/archive/cs/cs143/cs143.1128/)

### LLVM
* [LLVM tutorial](https://llvm.org/docs/tutorial/MyFirstLanguageFrontend/index.html)
* [LLVM backend development by example (RISC-V)](https://www.youtube.com/watch?v=AFaIP-dF-RA)
* [Creating an LLVM Backend](https://jonathan2251.github.io/lbd/)
* [Dart on LLVM](https://medium.com/dartlang/dart-on-llvm-b82e83f99a70): Some slight actual usage of llvm's gc.statepoint and gc.reloate thats not documentation.
* LLVM Stackmap example usage:
  * [Stack Map Format](https://llvm.org/docs/StackMaps.html#stackmap-format)
  * <https://github.com/dotnet/llilc/blob/master/lib/GcInfo/GcInfo.cpp>
  * <https://go.googlesource.com/gollvm/+/refs/heads/master/passes/>

### Scheduling & Concurrency
* [A fork() in the road](https://www.microsoft.com/en-us/research/uploads/prod/2019/04/fork-hotos19.pdf)
* [Golang's secheduler internals](https://golang.org/s/go11sched)

### JIT Compilers
* [Adventures in JIT compilation: Part 1 - an interpreter](https://eli.thegreenplace.net/2017/adventures-in-jit-compilation-part-1-an-interpreter/)
* [JIT vs. AOT: Unity And Conflict of Dynamic and Static Compilers for Java](https://www.youtube.com/watch?v=nzKqdxL8EXY&)

### Compilers
* [8cc - A Small C Compiler](https://github.com/rui314/8cc), [9cc - A Small C Compiler (new version)](https://github.com/rui314/9cc)
* [I wrote a self-hosting C compiler in 40 days (2015)](https://news.ycombinator.com/item?id=20889704)
* [Go: Overview of the Compiler (Go 1.13)](https://medium.com/a-journey-with-go/go-overview-of-the-compiler-4e5a153ca889)
* [Tour of the DMD D Programming Language Compiler](https://dconf.org/2016/talks/bright.pdf)
* [Spelunking D Compiler Internals](https://youtu.be/l_96Crl998E)
* [Turbo Pascal 3.0 Compiler / Code Generation Internals](https://pcengines.ch/tp3.htm)

### Virtual Machines
* [Virtual Machine Showdown: Stack Versus Registers](https://www.usenix.org/legacy/events/vee05/full_papers/p153-yunhe.pdf>)
* [Comparison of Earlang Runtime System and Java Virtual Machine](http://ds.cs.ut.ee/courses/course-files/To303nis%20Pool%20.pdf)
* [A No-Frills Introduction to Lua 5.1 VM Instructions](http://luaforge.net/docman/83/98/ANoFrillsIntroToLua51VMInstructions.pdf)
* [Virtual Machine DIspatch Experiments in Rust](https://pliniker.github.io/post/dispatchers/)
* [Write your Own Virtual Machine](https://justinmeiners.github.io/lc3-vm/)

### Parsing
#### Parsing with derivatives
* [Parsing with derivatives](http://matt.might.net/articles/parsing-with-derivatives/)
* [On the Complexity and Performance of Parsing with Derivatives](https://michaeldadams.org/papers/derivatives2/)

#### Top Down operator Precedence Parsing (aka Pratt Parsing)
* Top Down Operator Precedence (by Vaughan Pratt): [PDF](https://daesan.com/wp-content/uploads/2018/05/top_down_operator_precedence.pdf), [HTML](https://tdop.github.io/)
* Top Down Operator Precedence (by Douglas Crockford): [Blog Post](http://crockford.com/javascript/tdop/tdop.html), [GitHub](https://github.com/douglascrockford/TDOP)
* Simple Top-Down Parsing in Python: [Blog Post](http://effbot.org/zone/simple-top-down-parsing.htm), [SVN](http://svn.effbot.org/public/stuff/sandbox/topdown/)
* Pratt Parsers: Expression Parsing Made Easy: [Blog Post](http://journal.stuffwithstuff.com/2011/03/19/pratt-parsers-expression-parsing-made-easy/), [GitHub](https://github.com/munificent/bantam)
* [Crafting Interpreters - Compiling Expressions: A Pratt Parser](http://www.craftinginterpreters.com/compiling-expressions.html#a-pratt-parser)
* [Pratt Parsing and Precedence Climbing Are the Same Algorithm](https://www.oilshell.org/blog/2016/11/01.html)
* [Parsing expressions by precedence climbing](https://eli.thegreenplace.net/2012/08/02/parsing-expressions-by-precedence-climbing)
* Pratt Parser combinator for Parsec: [Hackage](https://hackage.haskell.org/package/parsec-pratt), [GitHub](https://github.com/jh3141/parsec-pratt/)
* L Language:
  * [Pratt parser in pictures](http://l-lang.org/blog/TDOP---Pratt-parser-in-pictures/)
  * [tdop.mli](http://l-lang.org/documentation/compiler_hyperbook/parser/tdop.mli/)
  * [tdop.ml](http://l-lang.org/documentation/compiler_hyperbook/parser/tdop.ml/)
  * [expression.ml](http://l-lang.org/documentation/compiler_hyperbook/parser/expression.ml/)

## Design
* [Aphorisms on programming language design](http://www.rntz.net/post/2017-01-27-aphorisms-on-pl-design.html)
* [Growing a Language, by Guy Steele](https://www.youtube.com/watch?v=_ahvzDzKdB0): There's also a [PDF](http://www.cs.virginia.edu/~evans/cs655/readings/steele.pdf), but watch the video first to avoid spoilers!
* [Rob Pike - Simplicity is Complicated](https://youtu.be/rFejpH_tAHM): Interesting food for thought, regardless how people feel about Go.
* [On Language Design (Lambda Days)](https://youtu.be/f3rP3JRq7Mw)
* [Brian Kernighan on successful language design](https://www.youtube.com/watch?v=Sg4U4r_AgJU)
* [An Empirical Analysis of C Preprocesser Use](https://homes.cs.washington.edu/~mernst/pubs/c-preprocessor-tse2002.pdf)

## Fun
* [Reversing the Technical Interview](https://aphyr.com/posts/340-reversing-the-technical-interview),
  [Hexing the Technical Interview](https://aphyr.com/posts/341-hexing-the-technical-interview),
  [Typing the Technical Interview](https://aphyr.com/posts/342-typing-the-technical-interview)

## Language Lists
* [Our community languages on proglangdesign.net](https://proglangdesign.net/#projects)
* [Languages on codelani.com](https://codelani.com/lists/languages.html): A huge list of programming languages
* [The Programming Languages Zoo](https://plzoo.andrej.com/): A collection of miniature programming languages which demonstrates various concepts and techniques used in programming language design and implementation.

## Learn existing languages
* [Curry: A Tutorial Introduction](https://www-ps.informatik.uni-kiel.de/currywiki/_media/documentation/tutorial.pdf): A lot can be learned from contrasting Curry and Mercury.
* [What I Wish I Knew When Learning Haskell](http://dev.stephendiehl.com/hask/): People writing compilers in Haskell might learn a thing or two from reviewing this.

## Memory management
* [Polonius and region errors](https://smallcultfollowing.com/babysteps/blog/2019/01/17/polonius-and-region-errors/)
* [Aaron J. Weiss, POPL 2019](https://twitter.com/aatxe/status/1086999418858016769)
* [A really early proposal for borrow checking in Rust](https://github.com/graydon/rust/wiki/Proposal-for-regions)
* [Memory Allocation Strategies](https://www.gingerbill.org/series/memory-allocation-strategies/): For those interested in the history of Rust.
* [Safely Sharing Data - Reference Capabilities in the Pony Programming Language](https://www.youtube.com/watch?v=u1JfYa413fY)
* [Mesh: Compacting Memory Management for C/C++ Applications](https://arxiv.org/abs/1902.04738)

### Garbage Collection
* [Managing Virtual Memory in Win32](https://www.labri.fr/perso/betrema/winnt/virtmm.html)
* [Mapping Multiple Memory Views in User Space](https://nullprogram.com/blog/2016/04/10/)
* [Tri-Color Garbage Collector](http://sean.cm/a/tricolor-garbage-collector)
* [A First Look Into ZGC](https://dinfuehr.github.io/blog/a-first-look-into-zgc/)
* [Shenandoah GC](https://www.jfokus.se/jfokus18/preso/Shenandoah-GC--What-We-Know-In-2018.pdf)
* [An Efficient Non-Moving Garbage Collector for Functional Languages](http://www.pllab.riec.tohoku.ac.jp/papers/icfp2011UenoOhoriOtomoAuthorVersion.pdf)
* [Algorithms for Dynamic Memory Management](http://www.cs.technion.ac.il/~erez/courses/gc/lectures/02-compaction.pdf)
* [Mark-Sweep and Mark-Compact GC](http://www.cs.tau.ac.il/~maon/teaching/2014-2015/seminar/seminar1415a-lec2-mark-sweep-mark-compact.pdf)
* [Orca: GC and Type System Co-Design for Actor Languages (Pony)](https://www.ponylang.org/media/papers/orca_gc_and_type_system_co-design_for_actor_languages.pdf)
* [Golang's Real-time GC in Theory and Practice](https://making.pusher.com/golangs-real-time-gc-in-theory-and-practice/)
* [The Memory Subsystem: Stacks, Heaps, and Garbage Collection](https://happi.github.io/theBeamBook/#CH-Memory)
* [Getting to Go: The Journey of Go's Garbage Collector](https://blog.golang.org/ismmkeynote)
* [New Garbage Collector - The LuaJIT Wiki](http://wiki.luajit.org/New-Garbage-Collector)
* [Visuaizing Garbage Collection Algorithms](https://spin.atomicobject.com/2014/09/03/visualizing-garbage-collection-algorithms/)
* [Understand How Much Memory Your Python Objects Use](https://code.tutsplus.com/tutorials/understand-how-much-memory-your-python-objects-use--cms-25609)
* [Understanding String heap size in Javascript / V8 - Stack Overflow](https://stackoverflow.com/questions/40512393/understanding-string-heap-size-in-javascript-v8)
* <http://hg.openjdk.java.net/zgc/zgc/file/01f601c8d727/src/hotspot/share/gc>
* [A tour of V8: Garbage Collection](http://jayconrod.com/posts/55/a-tour-of-v8-garbage-collection)
* [Erlang Garbage Collector](https://www.erlang-solutions.com/blog/erlang-garbage-collector.html)
* [Garbage Collection Design - .NET CoreCLR](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/garbage-collection.md)
* [GopherCon 2018 - Allocator Wrestling](https://about.sourcegraph.com/go/gophercon-2018-allocator-wrestling): A whirlwind tour of the Go memory allocator and garbage collector, with tools and tips on how to optimize.

### Syntax
* [Syntax Across Languages](http://rigaux.org/language-study/syntax-across-languages/)
* [The History of Rust](https://youtu.be/79PSagCD_AY): See how the developers of Rust re-framed features, streamlined, and improved upon the language.
* [How to Design an IDE-Friendly Language](https://youtu.be/lubc8udiP_8)
* [Choosing Your Next Programming Language](https://www.youtube.com/watch?v=lc_ZZxFV9Jo): Worth watching to think about multi-paradigm.

## Types
### Unsorted
* [The Laffer Curve of Types](https://felleisen.org/matthias/Thoughts/The_Laffer_Curve_of_Types.html)
* [Algebraic Effects for the Rest of Us](https://overreacted.io/algebraic-effects-for-the-rest-of-us/)
* [A Primer on Type Systems](https://www.cs.uaf.edu/users/chappell/public_html/class/2018_spr/cs331/docs/types_primer.html)
* [Bidirectional Type Checking](https://www.youtube.com/watch?v=utyBNDj7s2w)
* [What the heck is polymorphism](https://dev.to/jvanbruegge/what-the-heck-is-polymorphism-nmh)

### Dependent
* [A Tutorial Implementation of a Dependently Typed Lambda Calculus](https://www.andres-loeh.de/LambdaPi/), aka LambdaPi or Simply Easy. Written using Haskell.
* [Checking Dependent Types with Normalization by Evaluation: A Tutorial](http://davidchristiansen.dk/tutorials/nbe/)
* [Programming Language Foundations in Agda](https://plfa.github.io/)

### Gradual
* [Gradual Typing and Principled Language Interoperability](http://www.ccs.neu.edu/home/amal/course/7480-s19/)
* [The Behavior of Gradual Types: A User Study](https://cs.brown.edu/~sk/Publications/Papers/Published/tgpk-beh-grad-types-user-study/paper.pdf)

### Linear/Uniqueness/Substructural
* [Linearity in Haskell](http://edsko.net/2017/01/08/linearity-in-haskell/)
* [Uniqueness Typing Simplified](http://www.edsko.net/pubs/ifl07-paper.pdf)
* [Frank Pfenning (2012) - Linear Logic Lecture 01](https://www.youtube.com/watch?v=Bx2_CGzeMT4&list=PLo61mJSqK5cWnrvfIcn89amVRgN9llVJG): in-depth linear logic course, ranging over process calculus, linear functional languages, and logic programming
