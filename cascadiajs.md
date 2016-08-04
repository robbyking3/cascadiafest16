------

**[Back to the readme 📖](readme.md)**

------


<!-- MarkdownTOC -->

- [Making it better without making it over](#making-it-better-without-making-it-over)
- [Demystifying Web workers and service workers](#demystifying-web-workers-and-service-workers)

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

