ClojureSwift
============

Attempt to implement a Clojure dialect on top of Apple's Swift language and LLVM bitcode.

### Literature Review
##### [swift-lambdatron](https://github.com/austinzheng/swift-lambdatron/ "Swift Lambdatron") by Austin Zheng 
Currently a REPL capable of running a subset of Clojure. His design is very clean and easy to read. Still in very early phase, no docs yet.

##### [tocatta](https://github.com/jduey/toccata "Tocatta Clojure to Native Compiler") by Jim Duey
Clojure subset compiler written in C and targeted at the Clang compiler. It produces native code. Still very early phase, no docs and poorly formatted code. Very clever design.

##### [uikit](https://github.com/galdolber/uikit "Clojure UIKit") by Gal Dolber
Allows you to create iOS interfaces directly from Clojure code. It is fairly mature, but perhaps somewhat limited...

##### [clojure-objc](https://github.com/galdolber/clojure-objc "ClojureObjc") by Gal Dolber
Modified Clojure (JVM) compiler into a transpiler that produces Java code. Then you compile it to Objective-C LLVM bitcode using [Google's J2ObjC](https://github.com/google/j2objc "J2ObjC") with his own [lein-objcbuild](https://github.com/galdolber/lein-objcbuild "lein-objcbuild plugin") plugin.

##### [jet](https://github.com/brettwooldridge/jet "jet Swift-to-JVM bytecode compiler") by Brett Wooldridge
Compiler for Apple's Swift language that produces JVM bytecode targeting Java 8+.

