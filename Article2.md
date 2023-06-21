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
The syntax looks a little like LISP, which is unfortunate for readability, but does help in its basedness-factor.

## My experience

I have written two websites using WebAssembly myself, the most impressive one being [proper-website-2](https://dutchellie.nl/DutchEllie/proper-website-2).
This was my website for a while until I replaced it with a SvelteKit website.
The website itself is still hosed on [old.quenten.nl](https://old.quenten.nl/) if you fancy giving it a visit.

The code of this website was written using Go with a framework called [go-app](https://go-app.dev/), which unfortunately has not seen an update in over a year now.
The website was a joy to write and it was very interesting to work with a framework like this, that facilitates not only everything you need to write a website with exclusively WebAssembly, but also makes it a progressive webapp without you having to put in any work at all!
Now, I did make some [awful code that only a mother could love](https://dutchellie.nl/DutchEllie/proper-website-2/src/branch/main/src/guestbook.go) back then, but that's besides the point.

I found that the website is quite fast, but it isn't noticable against any other webapp that just uses Javascript instead.
The biggest bit of loading time is found in the initial loading of the app, where you have to download several megabytes of WASM file to run the website :).

## Closing words

I find WebAssembly to be a promising technology for the web and want to use it more in the future, if I ever get the chance.
There are also applications of WebAssembly that fall outside the browser, such as creating entirely platform independant application containers with Docker.
I am definitely going to try to make use of these use cases for WebAssembly.
