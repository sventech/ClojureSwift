ClojureSwift
============

Clojure hosted on Apple's Swift language and [LLVM bitcode](http://en.wikipedia.org/wiki/LLVM). The main goal is to enable the creation of iOS and Mac OS X apps written in idiomatic Clojure. There should be good interoperability with Swift and Objective-C, and access to all the usual libraries and frameworks without hassle. The best approach might be to transpile to Swift and use Apple's tools.

### Literature Review

##### [Clojure-ObjC](https://github.com/galdolber/clojure-objc "ClojureObjc") by Gal Dolber
Modified Clojure (JVM) compiler into a transpiler that produces Java code. Compile it to Objective-C LLVM bitcode using [Google's J2ObjC](https://github.com/google/j2objc "J2ObjC") with his own [lein-objcbuild](https://github.com/galdolber/lein-objcbuild "lein-objcbuild plugin") Leiningen plugin. Relatively mature, but not yet widely used.

##### [Goby](https://github.com/mfikes/goby "Goby ClojureScript on iOS") by Mike Fikes
Develop iOS apps with ClojureScript. Goby targets the iOS JavaScript runtimes (JSExport, JavaScriptCore), allowing a REPL connected to an iOS device during development! Each iOS libary requires bridge code to be added, but eventually complex apps can be made. One app is already in the app store, and performance is good since native libraries can be called from JavaScript. See example app [Shrimp](https://github.com/mfikes/shrimp "Shrimp example Goby app"). Also see [Owen Mathews' blog post about JavaScript on iOS](""http://www.bignerdranch.com/blog/javascriptcore-and-ios-7/"). *Eclipse license*

##### [Swift-Lambdatron](https://github.com/austinzheng/swift-lambdatron/ "Swift Lambdatron") by Austin Zheng 
Currently a REPL capable of running a subset of Clojure. Still in very early phase, no docs yet. Design is very clean and easy to read. *Eclipse license*

##### [ClojureC]("https://github.com/schani/clojurec/" "ClojureC") by Mark Probst &amp; 5 others
Modified ClojureScript compiler into transpiler that produces C code, has examples for XCode/iOS and Android development. Uses Boehm Garbage Collector (which is available on HomeBrew as `bdw-gc`) and [Klib]("https://github.com/attractivechaos/klib"). Provides support for Leiningen builds and testing.

##### [Tocatta](https://github.com/jduey/toccata "Tocatta Clojure to Native Compiler") by Jim Duey
Clojure subset, transpiles to C and targets the Clang compiler (which happens to be the default for Apple's XCode). It produces native binaries.  It currently relies on the Boehm GC (see above). Still very early phase, no docs and poorly formatted C code. Very clever design. *Eclipse license*

##### [UIKit](https://github.com/galdolber/uikit "Clojure UIKit") by Gal Dolber
Allows you to create iOS interfaces directly from Clojure code using Apple's AutoLayout system. It looks fairly mature (alpha vs. 5th commit for most of these projects), but perhaps somewhat limited in scope. *MIT + GPLv2 licenses*

##### [Jet](https://github.com/brettwooldridge/jet "jet Swift-to-JVM bytecode compiler") by Brett Wooldridge
Compiler for Apple's Swift language that produces JVM bytecode targeting Java 8+. This might be useful info in handling interoperability well. *Apache 2.0 license*

##### [RoboVM](https://github.com/robovm/robovm "RoboVM Ahead of time JVM compiler") by RoboVM
RoboVM translates Java bytecode into native ARM or x86 code. Several people have implemented iOS apps with Clojure on the platform. Simple access (syntactic sugar) for various APIs and frameworks. Performance is reported to be quite good, uses Boehm GC. *GPLv2 license except debugger*

##### [CL-LLVM](https://github.com/sellout/CL-LLVM "CL-LLVM") by Greg Pfeil
Common Lisp compiler targeting LLVM bitcode. This might be leveraged to produce a Clojure compiler. Uses C FFI (foreign function interface) to LLVM. *MIT License*

##### [FFI-LLVM (Ruby)](https://github.com/postmodern/ffi-llvm "FFI LLVM") by Postmodern
Ruby interfaces to the LLVM bitcode system. This provides a lot of example code for working with LLVM at a low level. *BSD? license*

##### [ClojureCLR](https://github.com/clojure/clojure-clr) + [Mono](http://xamarin.com/platform) by several people
ClojureCLR could theoretically run on iOS with Mono. Several people have talked about it, but I can't find any evidence that it has been done, especially with open source examples. This might be viable for Clojure on iOS since Microsoft is contributing their CLR code to Mono, but interoperability with native code would undoubtedly be very poor.

##### [Clojure Google Group](https://groups.google.com/forum/#!searchin/clojure/swift/clojure/HaswRFJw29g/sH1xGpitmNgJ) by several participants
Several people who are interested have contributed info, including the authors of several projects above.

### Details / FAQ
Important questions

* TCO (Tail Call Optimization) for recursion is supported by Swift.
* Integers, Floating Point numbers, and other common types are already implemented by swift-lambdatron.
* GC (Garbage Collection) is a problem. clojure-objc only has issues for interop bridged code. Will Swift's standard ARC (automatic reference counting) be enough? How can we implement GC cleanly?
* How can we implement it so we're not duplicating everything? (e.g., core.async rewrite)
* File extension: *.clsw perhaps, or use cljx
* Copy [RoboVM's idea of YAML API]("https://github.com/robovm/robovm/tree/master/cocoatouch/src/main/bro-gen") with a Transit (JSON-compatible) description of Apple frameworks with automatic bridge code generation
* [ReactiveCocoa + Swift]("http://www.scottlogic.com/blog/2014/07/24/mvvm-reactivecocoa-swift.html") would probably be a good idea.



