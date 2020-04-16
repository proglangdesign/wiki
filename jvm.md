---
permalink: /jvm
---

# Java Virtual Machine

The JVM is a Virtual Machine that hosts the Java language by providing an abstracted
machine that the Java compiler can target. By targetting the JVM, you can have your
language run on multiple platforms while only needing to write a code generator for one.
The instruction set the JVM uses is called **JVM Bytecode**.

The JVM is a stack based VM with a limited set of registers. It loads _class files_ 
containing bytecode at runtime and compiles them using a Just-In-Time (JIT) compiler.
The JVM has been optimized heavily over the years and can support allocating millions
of objects. 

## Benefits

Leveraging the JVM provides a number of benefits for your language:

* **Porability** is a non-issue because the JVM runs on most hardware.

* **Interoperability with Java** is painless and provides you with the wealth of 
libraries and frameworks already in existence.

* **Optimized Garbage Collection**. It's pretty tough to beat the JVM's GC. You 
can tune it to your heart's content, and you can try out different GCs if the 
default one isn't giving you the performance you want.

* **Backwards Compatibility** is guarenteed for your produced Jars, so consumers don't need to worry about recompiling your language when they want to update Java.

## Caveats

Being a Virutal Machine that compiles bytecode at runtime means you have to ship
your entire codebase in one jar file. This can be an issue for a number of reasons:

* **Security**. Your code is essentially open to the public. Java decompilers 
already work extremely well and they keep getting better. 

* **Size**. Including your standard library on top of whatever other libraries are being included can bulk up the size of your jars by a lot.

## Libraries

There are a number of libraries that can produce JVM Bytecode, each offering a unique
interface.

* [ASM](https://asm.ow2.io/) is focused on [performance](https://asm.ow2.io/performance.html) and as such has an API that is quite low-level. It is used by [Kotlin](https://github.com/JetBrains/kotlin/tree/master/compiler/backend/src/org/jetbrains/kotlin/codegen) and [Groovy](https://github.com/apache/groovy/blob/GROOVY_2_4_15/src/main/org/codehaus/groovy/classgen/AsmClassGenerator.java).

* [Javassist](https://www.javassist.org/) is a higher-level library that offers an easier to use interface.

* [BCEL](http://commons.apache.org/proper/commons-bcel/) is the Apache Foundation's bytecode library. It hasn't had a lot of development happen in a while but it's still a viable option.


## Resources for Learning

* [DZone](https://dzone.com/articles/introduction-to-java-bytecode) has an in depth tutorial showing the JVM's stack based architecture and how it runs JVM Bytecode.

* [Oracle's JVM Specification](https://docs.oracle.com/javase/specs/jvms/se14/html/jvms-6.html) provides a list of instructions as well as a lot of documentation on what operations are legal.
