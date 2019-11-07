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
