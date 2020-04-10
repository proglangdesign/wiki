---
permalink: /backend
---

# Backend

The backend of a compiler takes the representation of the language it's compiling and
emits its target language. Over time, libraries were created to modularize this process
and make it easier for a compiler designer to target common architectures.

There are two main ways to translate a language to machine code: **Ahead-of-time  Compilation** and **Just-in-time Compilation**. AOT Compilers emit machine code 
immediately, while JIT Compilers won't translate code until it needs to be executed.
This separates backend frameworks into **Code Generators** and **Virtual Machines**.
There isn't a huge difference between these terms, but usually CGs refer to backends 
that use AOT compilation, and VMs refer to backends that use JIT compilation. This line
can be blurred with frameworks like [LLVM](/llvm) that provide both.

## Code Generator

Code Generators offer libraries and tools for generating native code for a variety of
architectures. There are many platforms one can choose, and as such this list is not 
comprehensive. These usually consist of an Intermediate Representation that a compiler
will emit. The library will take that IR and produce machine code for one of the 
instruction sets it supports.

* [LLVM](/llvm)
* [CraneLift](https://github.com/bytecodealliance/wasmtime/tree/master/cranelift)
* [QBE](https://c9x.me/compile/)
* [GRIN](https://grin-compiler.github.io/)

## Virtual Machine

Virtual Machines act similarly, except one can translate code to a VM's instruction set
and execute it at a later date. This usually requires bundling the VM with your program
or expecting the VM to be on the user's machine. The VM will handle translating the
program to machine code at runtime through JIT compilation.

* [JVM](/jvm)
* CLR
