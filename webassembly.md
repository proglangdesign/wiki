---
permalink: /webassembly
---
# WebAssembly

[WebAssembly](http://webassembly.org/) is the proposed "native execution" language for web browsers, intended as a higher-performing and language-agnostic alternative to Javascript. Most popular browsers support it.

There are several approaches a language compiler can take to support WebAssembly as a target platform:

* [Emscripten SDK](http://webassembly.org/getting-started/developers-guide/), a voluminous tool-chain for generating WebAssembly code. There are many ways to make use of Emscripten. One approach would involve the compiler first generating C or C++, and then Emscripten would be used to finish the transformation to WebAssembly. Another approach is for the compiler's backend to perform code generation using Emscripten's fork of LLVM and its WebAssembly target (wasm32-unknown-emscripten), which can be transformed into wasm files using Emscripten tools.
* LLVM's "experimental" WebAssembly target. Using this approach, any compiler using LLVM as a code generation backend would directly emit WebAssembly object files. LLVM's wasm-ld tool would then be used to linkedit the generated object files into ready-to-use .wasm files.
* Directly emit WebAssembly files (wasm or wat). The WebAssembly tool chain can be helpful (e.g., for converting wat to the wasm binary format).

## Building a WebAssembly-capable LLVM

Because the WebAssembly target (wasm32-unknown-unknown-wasm) is currently experimental, you don't get it when building vanilla LLVM (e.g., using a package manager such as apt-get). One must custom-build LLVM, specifying "-DLLVM_EXPERIMENTAL_TARGETS_TO_BUILD=WebAssembly" as one of the CMake options. [This page](https://gist.github.com/yurydelendik/4eeff8248aeb14ce763e) shows a sequence of steps for downloading and building the LLVM toolchain correctly for WebAssembly.

## Resources for Learning

These pages offer valuable information and provide useful links:

* [WebAssembly Semantics](http://webassembly.org/docs/semantics/) details the key concepts governing how WebAssembly works. WebAssembly is notably different from processor-specific assembly languages in many ways. It is very important to understand these differences, as they impose significant limits on what you can do and how you can do it.
* [WebAssembly Javascript API](https://developer.mozilla.org/en-US/docs/WebAssembly) specifies the Javascript APIs that must be used to instantiate and run a WebAssembly module.
* [Working with C and WebAssembly](https://aransentin.github.io/cwasm/#demo). Although focused on a C example, this concise, but meaty walkthrough takes you step-by-step through details well worth knowing: particularly, how to use the LLVM tools and techniques for interfacing between Javascript and WebAssembly.
* [wat-wasm demo](https://github.com/webassembly/wabt#online-demos), websites able to convert the text-based WebAssembly files (wat) to viewable binary files (wasm), etc.
* [Future feature tracking](https://github.com/WebAssembly/design/blob/master/FutureFeatures.md#tracking-issues), listing features being proposed and developed, particular [anyref](https://gist.github.com/rossberg/be5962c37e5e749285272622f52b4223) which improves interop with Javascript.
* [WebAssembly Community Group](https://www.w3.org/community/webassembly/) and [meetings](https://github.com/webassembly/meetings).

## Caveats

WebAssembly is still very early in its lifecycle and only supports what they call their Minimum Viable Product (MVP). Thus:

* Some functionality is missing:  garbage collection, reference types, threads, etc. With some creativity, there are ways to get around some of these limits.
* Few have gone down this road, so breadcrumbs that help overcome obstacles can sometimes be hard to find
* Expect the implementation and tools to be imperfect, potentially inconsistent and almost certainly in flux.

## Pointers on targeting WebAssembly directly

Targeting WebAssembly directly is probably easier than targeting it via LLVM or a similar back-end, because, in order to target LLVM, you need to understand things like SSA form and PHI nodes, which are not necessary in order to target WebAssembly directly. That is, as long as you do not care about the optimizations made possible by LLVM. So, here are a few things that we think might be helpful to know:

### Writing while-loops in WebAssembly

When reading the WebAssembly specification, it might not be obvious at the first sight how to write a while-loop in WebAssembly. However, here is [an example of how you can implement while-loops](https://github.com/FlatAssembler/AECforWebAssembly/blob/56f4bdb11c39e1dd546bfd35180784634212762a/compiler.cpp#L1184C1-L1199C4) in your compiler that is targeting WebAssembly:
```c++
  } else if (text == "While") {
    if (children.size() < 2 or children[1].text != "Loop") {
      std::cerr << "Line " << lineNumber << ", Column " << columnNumber
                << ", Compiler error: Corrupt AST, aborting (or else we will "
                   "segfault)!"
                << std::endl;
      exit(1);
    }
    assembly += "(block\n\t(loop\n\t\t(br_if 1\n\t\t\t(i32.eqz\n"
                "\t\t\t;; Compiling the condition of the while-loop: " +
                children[0].getLispExpression() + "\n" +
                convertToInteger32(children[0], context).indentBy(4) +
                "\n\t\t\t)\n\t\t)\n" +
                children[1].compile(context).indentBy(2) +
                "\n\t\t(br 0)\n\t)\n)";
  }
```

### Unaligned access

When browsers are executing WebAssembly, they are allowing unaligned access. A 32-bit integer does not have to be at a memory address that is divisible by 4 bytes. However, that does not mean that, when writing a compiler targeting WebAssembly, you should completely ignore the problem of unaligned access. First of all, aligned access translates to faster machine code on ARM devices, and it is important that the Internet scripts written in your programming language run decently fast on mobile. Second, WebAssembly does not run only in a browser, but outside-of-the-browser tools such as WebAssembly System Interface (WASI) are not as permissive as the browsers are. WasmTime, for example, is the most popular WASI runtime, and it requires that the pointers passed to the WASI-specific functions are pointing to aligned variables. For example, it is requiring that the last argument to the `fd_write` function (the `nwritten`, pointing to an integer where the number of bytes that have been written to the file will be written) is divisible by four. Watch out for that, or else a simple "*Hello world!*" program might crash!
