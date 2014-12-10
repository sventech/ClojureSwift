ClojureSwift
============

Implement Clojure with Apple's Swift language and [LLVM bitcode](http://en.wikipedia.org/wiki/LLVM). The main goal is to enable the creation of iOS and Mac OS X apps written in idiomatic Clojure. There should be good interoperability with Swift and Objective-C, and access to all the usual libraries and frameworks without hassle.

### Literature Review

##### [clojure-objc](https://github.com/galdolber/clojure-objc "ClojureObjc") by Gal Dolber
Modified Clojure (JVM) compiler into a transpiler that produces Java code. Compile it to Objective-C LLVM bitcode using [Google's J2ObjC](https://github.com/google/j2objc "J2ObjC") with his own [lein-objcbuild](https://github.com/galdolber/lein-objcbuild "lein-objcbuild plugin") plugin. Relatively mature, but not yet widely used.

##### [Goby](https://github.com/mfikes/goby "Goby ClojureScript on iOS") by Mike Fikes
Develop iOS apps with ClojureScript. Goby targets the iOS JavaScript runtimes, allowing a REPL during development. Each iOS libary requires bridge code to be added, but eventually complex apps can be made. One app is already in the app store, and performance is good since native libraries can be called from JavaScript. See example app [Shrimp](https://github.com/mfikes/shrimp "Shrimp example Goby app").

##### [swift-lambdatron](https://github.com/austinzheng/swift-lambdatron/ "Swift Lambdatron") by Austin Zheng 
Currently a REPL capable of running a subset of Clojure. Still in very early phase, no docs yet. Design is very clean and easy to read.

##### [tocatta](https://github.com/jduey/toccata "Tocatta Clojure to Native Compiler") by Jim Duey
Clojure subset compiler written in C and targeted at the Clang compiler (which happens to be the default for Apple's XCode). It produces native binaries.  It currently relies on the Boehm Garbage Collector. Still very early phase, no docs and poorly formatted code. Very clever design.

##### [uikit](https://github.com/galdolber/uikit "Clojure UIKit") by Gal Dolber
Allows you to create iOS interfaces directly from Clojure code. It is fairly mature, but perhaps somewhat limited in scope.

##### [jet](https://github.com/brettwooldridge/jet "jet Swift-to-JVM bytecode compiler") by Brett Wooldridge
Compiler for Apple's Swift language that produces JVM bytecode targeting Java 8+. This might be useful info in handling interoperability well.

##### [cl-llvm](https://github.com/sellout/CL-LLVM "CL-LLVM") by Greg Pfeil
Common Lisp compiler targeting LLVM bitcode. This might be leveraged to produce a Clojure compiler. Uses C FFI (foreign function interface) to LLVM.

##### [ffi-llvm (Ruby)](https://github.com/postmodern/ffi-llvm "FFI LLVM") by Postmodern
Ruby interfaces to the LLVM bitcode system. This provides a lot of example code for working with LLVM at a low level.

##### [Clojure Google Group](https://groups.google.com/forum/#!searchin/clojure/swift/clojure/HaswRFJw29g/sH1xGpitmNgJ) by several participants
Several people who are interested have contributed info, including the authors of several projects above.

### Details / FAQ
Important questions commonly asked

* TCO (Tail Call Optimization) for recursion is supported by Swift.
* Integers, Floating Point numbers, and other common types are already implemented by swift-lambdatron.
* GC (Garbage Collection) is an important question. clojure-objc only has problems for interoperability. Will Swift's standard ARC (automatic reference counting) be enough? How can we implement GC cleanly?
* How can we implement it so we're not duplicating everything? (e.g., core.async rewrite)
* File extension: *.clsw perhaps



