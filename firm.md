---
permalink: /firm
---
# FIRM

[libFirm](https://pp.ipd.kit.edu/firm/) is a C library that provides a graph-based intermediate representation,
optimizations, and assembly code generation suitable for use in compilers.

It is an academic project developed since 1998 at the Karlsruhe university.

## FIRM vs LLVM

See also the [dedicated section](https://pp.ipd.kit.edu/firm/LLVM.html) of the official documentation.

### High level constructs

Classes and unions are first class citizen ([`new_type_class`](https://pp.ipd.kit.edu/firm/api_1.22/a00154.html#ga6d34295cc14cf26cd67f29f28839ff40) and [`new_type_union`](https://pp.ipd.kit.edu/firm/api_1.22/a00156.html#gabda60673a5630e0fa5a8e9a5c1e3c479)).
While in LLVM for a union you will use GEPs it completly lacks the class abstraction.

### Sign

The [sign](https://pp.ipd.kit.edu/firm/api_1.22/a00141.html#ga42490c367589bdf8e784df08ae90c32b) is part of integer types.
In LLVM it is rather up to the programmer to choose or not the signed version of an operator.

### Fast compilation

Generating FIRM is fast. To the cost of a couple of seconds you can update libfirm binaries when you recompile your project.
With LLVM, and assuming you use the C API, you'll rather choose to link against the pre-compiled libraries.

### source assembly

FIRM outputs source assembly files (the [be_main](https://pp.ipd.kit.edu/firm/api_1.22/a00008.html#ga3ea092eb25dd79b88ddc6c3d96817912) function generates the file).
This means that a C compiler has to be part of your projects toolchain.
With LLVM you will require [LLC](https://llvm.org/docs/CommandGuide/llc.html) and then only a linker is required.

### License

FIRM is licensed under the terms of the LGPL v2.1. That means that if you link it statically,
your project should be LGPL as well.
LLVM license is more permissive.

## Examples

The main example is a [C compiler](https://github.com/libfirm/cparser) developed by the same team as the library.
See also [the dedicated section](https://pp.ipd.kit.edu/firm/Projects.html) of the official documentation.
