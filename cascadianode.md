------

**[Back to the readme 📖](readme.md)**

------

<!-- MarkdownTOC -->

- [Making a Robot Eye with JavaScript - or Magic of Computer Vision Unraveled](#making-a-robot-eye-with-javascript---or-magic-of-computer-vision-unraveled)
- [Computer Vision, Robots, and Mobile Games.](#computer-vision-robots-and-mobile-games)
- [Sparkly LEDs and Javascrpt](#sparkly-leds-and-javascrpt)
- [](#)
- [Web code and self exploration](#web-code-and-self-exploration)
- [API design through the lens of photography](#api-design-through-the-lens-of-photography)
- [Javascript Memory](#javascript-memory)
- [Managing Packages](#managing-packages)
- [Demystifying Javascript Engines](#demystifying-javascript-engines)

<!-- /MarkdownTOC -->



## Making a Robot Eye with JavaScript - or Magic of Computer Vision Unraveled
> **Mariko Kosaka**

> tw: [@kosamari](http://twitter.com/kosamari)

* web worker postmessage on message
* carno convolution

## Computer Vision, Robots, and Mobile Games.
> **Pawel Szymczykowski**

> tw: [@makenai](http://twitter.com/makenai)

* [tapster.io](www.tapster.io) - open source robot to test mobile devices - get made at maker space with 3d printing
* [J5-Delta](https://github.com/makenai/j5-delta)
* OpenCV - computer vision
* wrote a finite state machine
  * conceptual model of behaviour
  * machina node - [https://www.npmjs.com/package/machina](https://www.npmjs.com/package/machina)
* [slides](http://bit.ly/crossyroadbot)


## Sparkly LEDs and Javascrpt
> **Russell Hay**

> tw: [@russellhay](http://twitter.com/russellhay)

* LEDs, similar to pixels
  * Neopixels
  * APA102c / Dotstar / Superled
* Self Contained vs Host Computer
* Self Container
  * simple setup with minimal parts
  * only printf style debugging
  * limited memory for animation
  * manual memory management
  * battery concious
* Host computer
* To do
  * biggish capacitor 
  * resistor on data line
  * calculate power usage
* Johnny 5 and node-pixel
* [Slides](http://RussTheAerialist/hsgfz-slides)

## 
> **Jenn Turner**

> tw: [@jennwrites](http://twitter.com/jennwrites)

* Open source systems
  * can be viewed as a members only club


## Web code and self exploration
> **IvanaMcConnell**

> tw: [IvanaMcConnell](http://twitter.com/IvanaMcConnell)

* how technology affects our humanity
* how we define our identity to self and others
* 

## API design through the lens of photography
> **Bryan huges**

> tw: [@nebrius](http://twitter.com/nebrius)

* API - a defined contract between developers
* 


## Javascript Memory
> **Safia**

> tw: [@captainsafia](http://twitter.com/captainsafia)

> w: [safia.rocks](http://safia.rocks)

* memory utilization should still be moderate in order to meet user demands
* not all users are on the latest tech
* you don't want to be _that_ app that makes the OS chug
* memory management
  * manual memory management
    * allocate memory space for your data
  * automatic memory management === garbage collection
    * cleans it up when no longer used
  * V8 engine wooo in chrome and node 
  * memory heap data structure - root node pointing down, ends on terminating nodes
  * V8 allocation
    * new space
    * old pointer space
    * old data space
    * large object space (larger than 8mb)
    * code space - compiled just in time
  * reachability - if no way to tranverse to it through the tree - orphaned items outside of root
  * how does it collect garbage
    * stop the world technique - pauses running program, execute garbage collection cycle
  * V8 diff cleaning approaches per new or old data
    * called a generational garbage collector
  * scavenging - copies tree, gets rid of orphans
  * mark and sweep 
    * first - traverse heap and mark objects
    * second - sweep and cleanup
  * Practical uses or questions to ask 
    * how much memory is my app using?
    * how often do garbage collection cycles occur in my app?
  * Requires right tooling
  * chrome devtools - profiles tab with heap snapshots
    * detached dom elements - search for it
  * node.js side 
    * memwatch - 
    * heapdump - can load into chrome profiler
    * V8-profiler
  * examples of when to use this knowledge
    * apps just running and causing the app to crash over time
    * jank could be garbage collection happening too often


## Managing Packages
> **Stephen Boennemann**

> tw [@Boennemann](http://twitter.com/boennemann)

* greenkeeper managing dependencies
* modules are constantly changing
* [npm.im/semantic-release](http://npm.im/semantic-release)
* skimdb.npmjs.com for couch db changelog tail
* npm.im/github-change-remote-file
* flow
  * npm notify change in registry
  * new version? 
  * dependencies?
  * new PR
* `npm i -g greenkeeper`
* app.greenkeeper.io
* use version ranges in package.json
* have a solid test suite
* `dist-tags` in npm
* [bit.ly/dist-tags](http://bit.ly/dist-tags)


## Demystifying Javascript Engines
> ****

> tw: [@a0viedo](http://twitter.com/a0viedo)

* inflection point 2006/2007
* bit.ly/js-engines