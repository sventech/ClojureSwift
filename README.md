ClojureSwift
============

Attempt to implement a Clojure dialect on top of Apple's Swift language and LLVM bitcode. The main goal is to enable the creation of iOS and Mac OS X apps written in idiomatic Clojure. There should be good interoperability with Swift and Objective-C, and access to all the usual libraries and frameworks without hassle.

### Literature Review

##### [Goby](https://github.com/mfikes/goby "Goby ClojureScript on iOS") by Mike Fikes
Develop iOS apps with ClojureScript. Goby targets the iOS JavaScript capabilities, allowing a REPL during development. Each iOS libary requires bridge code to be added, but eventually complex apps could be made. One app is already in the app store, and performance is good.

##### [swift-lambdatron](https://github.com/austinzheng/swift-lambdatron/ "Swift Lambdatron") by Austin Zheng 
Currently a REPL capable of running a subset of Clojure. Still in very early phase, no docs yet. Design is very clean and easy to read.

##### [tocatta](https://github.com/jduey/toccata "Tocatta Clojure to Native Compiler") by Jim Duey
Clojure subset compiler written in C and targeted at the Clang compiler. It produces native code.  It currently relies on the Boehm Garbage Collector. Still very early phase, no docs and poorly formatted code. Very clever design.

##### [uikit](https://github.com/galdolber/uikit "Clojure UIKit") by Gal Dolber
Allows you to create iOS interfaces directly from Clojure code. It is fairly mature, but perhaps somewhat limited in scope.

##### [clojure-objc](https://github.com/galdolber/clojure-objc "ClojureObjc") by Gal Dolber
Modified Clojure (JVM) compiler into a transpiler that produces Java code. Then you compile it to Objective-C LLVM bitcode using [Google's J2ObjC](https://github.com/google/j2objc "J2ObjC") with his own [lein-objcbuild](https://github.com/galdolber/lein-objcbuild "lein-objcbuild plugin") plugin.

##### [jet](https://github.com/brettwooldridge/jet "jet Swift-to-JVM bytecode compiler") by Brett Wooldridge
Compiler for Apple's Swift language that produces JVM bytecode targeting Java 8+. This might be useful info in handling interoperability well.

##### [cl-llvm](https://github.com/sellout/CL-LLVM "CL-LLVM") by Greg Pfeil
Common Lisp compiler targeting LLVM bitcode. This might be leveraged to produce a Clojure compiler. Uses C FFI (foreign function interface) to LLVM.

##### [ffi-llvm (Ruby)](https://github.com/postmodern/ffi-llvm "FFI LLVM") by Postmodern
Ruby interfaces to the LLVM bitcode system. This provides a lot of example code for working with LLVM at a low level.


