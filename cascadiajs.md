------

**[Back to the readme 📖](readme.md)**

------


<!-- MarkdownTOC -->

- [Making it better without making it over](#making-it-better-without-making-it-over)
- [Demystifying Web workers and service workers](#demystifying-web-workers-and-service-workers)
- [Using WebGL](#using-webgl)
- [In defense of static sites](#in-defense-of-static-sites)
- [3rd party javascript](#3rd-party-javascript)

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


## In defense of static sites
> **Liz Abinante**

> tw: [@feministy](https://twitter.com/feministy)

* js fatigue can be a thing, takes a while sometimes to get things running
* users don't care about our technical debt, they want new features and better experiences
* static sites
  * no database 
  * no backend
  * no JS (mostly)
* what do you need JS for?
* static sites are cheap
* S3 won't fall over (usually)
* Shared responsibility for deploy and owning it 
* it's just files uploaded
* very performant
* Use cases
  * portfolios
  * blogs
  * resumes
  * prototypes
  * events and confs
  * brick and mortar businesses
  * informational marketing sites
* Use an api to generate content ahead of time


## 3rd party javascript
> **Noah Adams**

> tw: [@noah_adams](https://twitter.com/noah_adams)

* 3rd part script
  * end user
  * publisher of website
  * anyone else involved
* Examples - Google Analytics, Intercom, Disqus, BazaarVoice, Social Sharing widgets
* What
  * Data collection, Analytics
  * add functionality (chat, comments)
  * integrations with other services (social sharing)
* Third party javascript book (somewhat out of date now)
* Integration and Delivery
  * don't break the site
  * simple as including `<script>` tag
  * or a js snippet
  * or tag manager 
  * how to load 
    * asap
    * without blocking rendering
    * without blocking `load` event
    * async
    * in phases with small payload and config early
    * more as it's needed or convenient
    * load once then cache
  * Bake in configuration 
    * global hooks
    * comman queue pattern
  * Markup conventions 
    * store configs in `data` attributes
  * Load without clocking the critical path (add `async` attribute to script)
  * Load more without blocking the load event
    * use ajax, wait until after load, or block load event
  * Deliver Code
    * minify, gzip, compress images
    * cache
    * only loader needs short cache time
    * use a CDN for everything you can
  * deploying client side apps 1,000 at a time - talk by rmurphey [slides](https://speakerdeck.com/rmurphey/deploying-client-side-apps-1000-or-so-at-a-time)
* Building Defensively 
  * like being a guest in someone's home
  * don't let the site break you
  * your integration adds another attach surface
  * unauthorized access, XSS etc
  * Building web ui defensively 
    * `<iframe>` 
    * `window.open()`
    * web components?
    * container to dom, with unique Id, serve CSS reset for absolutely everything
  * Building JS defensively 
    * contending for every resource - cookies, localstorage, memory, global namespace
    * what can go wrong examples
      * browser apis can be extended or changed by customer sites so you can't trust them
    * fixes - create an iframe, get window object, and return the XML request to make sure
    * making cross domain request
      * XHR and CORS
      * or using [easyXDM](https://github.com/oyvindkinsey/easyXDM)
* Tools, Testing, and Iteration 
  * [universal module definition](https://github.com/umdjs/umd)
  * dynamic checks for module loaders can create race conditions
  * Testing
    * use unit tests
    * test for global variable leaks
    * run against lots of browsers - sauce labs, browser stack, testily 
  * build a way to test new versions of your third party scripts against running versions of peoples' page - [charles](https://www.charlesproxy.com/), fiddler
* [Slides](bit.ly/3rdpartyjs)