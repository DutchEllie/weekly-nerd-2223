# WebAssembly

WebAssembly (WASM) is a technology in the browser (and outside of it) that aims to be a sort of native assembly code, but for every platform.
It feels a little like the JVM, right?
A sort of bytecode that runs on every device that can run the translation layer, and since browsers are already there they can serve as the perfect translation layer.

## Use cases

WebAssembly aims to provide a platform for developers to write applications for the web that require more performance or low-level access than Javascript can provide.
This is especially useful for extremely large codebases, as WebAssembly can be decoded far faster than Javascript can be parsed [source](https://webassembly.org/docs/faq/).
The performance is faster as well (although not as fast as you might hope for), being anywhere between 1x and 16x as fast [source](https://www.adservio.fr/post/how-fast-and-efficient-is-wasm#el2).
The website for WebAssembly lists a few use cases that WASM should be able to handle much better than Javascript, such as:

* Games
* Peer-to-peer code
* CAD applications
* Image recognition
* VPN

## How to use

You can use WebAssembly right now, as it is implemented in all modern browsers that people actually use!
Programming in WebAssembly is quite simple, since most modern languages have a way to transpile code to WebAssembly.
You can write your code in familiar and fun languages such as Go, C++ or even Rust.

But, there is also nothing holding you back from writing WebAssembly directly as it is.
There is a textual representation of WebAssembly called WAT (WebAssembly Text) and it looks a bit like this:

```wat
(module
    ;; Imports from JavaScript namespace
    (import  "console"  "log" (func  $log (param  i32  i32))) ;; Import log function
    (import  "js"  "mem" (memory  1)) ;; Import 1 page of memory (54kb)
    
    ;; Data section of our module
    (data (i32.const 0) "Hello World from WebAssembly!")
    
    ;; Function declaration: Exported as helloWorld(), no arguments
    (func (export  "helloWorld")
        i32.const 0  ;; pass offset 0 to log
        i32.const 29  ;; pass length 29 to log (strlen of sample text)
        call  $log
        )
)
```

The above code is a Hello World-type function in WebAssembly.
The code syntax itself looks a bit like Javascript and LISP had a child together, making it possibly the most ugly code ever written.
I have to say, I am sort of disappointed to find out that the similatities between LISP and WASM end at the syntax because LISP is quite cool, but I digress.

