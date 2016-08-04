------

**[Back to the readme 📖](readme.md)**

------


<!-- MarkdownTOC -->

- [Making it better without making it over](#making-it-better-without-making-it-over)
- [Demystifying Web workers and service workers](#demystifying-web-workers-and-service-workers)
- [Using WebGL](#using-webgl)

<!-- /MarkdownTOC -->


## Making it better without making it over
> **Rebecca Murphey**

> tw: [@rmurphey](http://twitter.com/rmurphey)

* Approaching old javascript and not rewriting it all
* Starting with single source of truth for state/data
* ESlint ftw
* Lessons learned
  * experience alone of hacking on "vintage code" affords opportunities to learn
  * every technology decision is eventually regrettable
  * education is a powerful enabler of improvement
  * building for the web is better today


## Demystifying Web workers and service workers
> **Nolan Lawson**

> tw: [@nolanlawson](http://twitter.com/nolanlawson)

* these apis have potential to fundamentally change how we make websites
* Web Workers
  * older spec
* long running javascript takes the thread, blocks animations, gifs, forms etc. completely blocking
* every line of frontend js has momentarily stopped our pages from working 
* JANK booyeah
  * death by a thousand cuts - lots of tiny operations in js
* 1000ms / 60 frames = 16.7ms to work with for js
* async? using our happy callbacks, promises 
  * myth - invoking an async api will be in background thread until call back - not true (takes up less of thread, but still there)
  * [http://nolanlawson.github.io/database-comparison/](http://nolanlawson.github.io/database-comparison/)
  * fetch - will still block
* stuff that blocks the dom
  * indexdb
  * XHR
  * JSON.parse
  * fetch
  * Garbage collection
  * Javascript in general
* Web workers does not block the dom or run on the main thread
* Ability to escape single thread, using a background thread 
* Supported in all major browsers ie10+, everything else
* Communicate with Web Workers using async message passing (just limit how many times you hit it)
* [Pokedex.org](http://www.pokedex.org)
* Service Workers
  * solves offline issue
  * very similar to web workers
  * one extra power - intercept requests on the main thread and give a response
  * support not great - chrome, firefox
* WW vs SW
  * tab control
    * ww - have tab control
    * sw - shared across all tab instances of an origin
  * lifespan
    * ww - same as tab
    * sw - independent
* Protips
  * beware of API support - 
    * there is no access to the DOM directly
    * no local storage (but indexdb works)
    * no XHR in SW, only fetch
    * [MDN - Functions and classes for Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Functions_and_classes_available_to_workers)
    * [html5workertest.com](http://html5workertest.com)
    * [Promise-worker library](https://github.com/nolanlawson/promise-worker)
    * [Pseudo-worker](https://github.com/nolanlawson/pseudo-worker)
* Powerful concepts for the web 
  * parallelism - web workers
  * offline - service workers
* [Slides](https://github.com/nolanlawson/cascadia-2016)


## Using WebGL
> **Seth Samuel**

> tw: [@sethfsamuel](http://twitter.com/sethfsamuel)

* what is it - a js api to let us talk to the graphics card
* closest we can get to the metal as a js dev
* how does it work
  * api to webgl
  * webgl sends to OS
  * OS to graphics driver
  * GPU paints to canvas
* Shaders
  * Data > Vertex Shader > Fragment Shader > Graphics!
* Vertex Shader
  * transform data into 3d space coords
* Generation happens completely in parallel
* Non blocking calculations - FPS staying up
* Why is it so powerful?
  * CPU v GPU
  * CPU does lots of things pretty well
  * GPU is very specialized - math in parallel very fast
* How to get data out of WebGL
  * `canvas.getImageData` - dump pixels as an array
  * Implementation challenges
    * high cost of serialization
* Why
  * GPU parallel
  * `0(n) < 0(n^3)`
* Potential applications
  * Hash collision - check password system safety 
  * Bitcoin mining
  * Media encoding
  * Machine learning
  * Signal analysis/processing
  * Protein Folding
* Blockers
  * No bit operations
  * Unresponsive Window
  * OS level timeouts 
* How to solve
  * update implementation of shading version
  * Canvas Webgl in web worker
* Summary
  * awesome
  * powerful
