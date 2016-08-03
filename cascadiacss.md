------

**[Back to the readme 📖](readme.md)**

------


<!-- MarkdownTOC -->

- [Color Theory](#color-theory)
- [Bauhaus Design in the Browser](#bauhaus-design-in-the-browser)
- [Code Patterns for Pattern-Making](#code-patterns-for-pattern-making)
- [CSS Pseudo & beyond](#css-pseudo--beyond)
- [Creating Beautiful, Accessible, and User-Friendly Forms](#creating-beautiful-accessible-and-user-friendly-forms)
- [Flipping Tables](#flipping-tables)
- [Components, tools, and services](#components-tools-and-services)
- [PostCSS in Sass](#postcss-in-sass)
- [SVG: so very good](#svg-so-very-good)

<!-- /MarkdownTOC -->


## Color Theory
> **Natalya Shelborne**

> tw: [@natalyathree](http://twitter.com/natalyathree)

* Color wheel - color relationships
* http://tallys.github.io/color-theory/
* sass functions 
* HSL maps to cognitive model of how colors relate - using degrees
* Make it pop - one color saturated, other colors toned down
* third of your viewport a neutral color to reduce cognitive load 
* color picking is a decision tree based on two complimentary colors

_Questions_
* is it best to only use two base complimentary colors?

## Bauhaus Design in the Browser
> **Justin McDowell**

> tw: [@revoltpuppy](http://twitter.com/revoltpuppy)

* Form and function - bauhaus times
* CSS as art
* viewport units
  * typography based on viewport 
* transform
  * perspective simmilar to zoom
  * translateZ similar to dollya
* grid
  * making mondrian
  * define columns and rows with units, sep by spaces
  * per cell define row start and end based on totals in parent
* shapes
  * flow text around
  * `shape-outside`, `shape-inside`
* brauser support heh

## Code Patterns for Pattern-Making
> **Miriam Suzanne**

> tw: [@mirisuzanne](http://twitter.com/mirisuzanne)

* building css systems depend on your context
* bootstrap doesn't work for everyone
* integration - show context and relationships
  * process, toolkit
* DRY
* Don't stretch for patterns
* Do build one offs - doesn't need everything to be a pattern
* Patterns add meaning
  * two elements sharing a purpose 
* Sass should add meaning 
  * move complexity into functions and mixins
* Specificity versus reach and explicitness
* Naming conventions across team
* Pattern layers
  * config > layout > components > elements
* Style approaches - atomic, ITCSS
* Separation of concerns (logic, data, structure, presentation)
* Color styling for palette
  * using a map in Sass - key, value. `map-get` in sass - meaningful structure
* Make patterns the lazy option
* Using markup preprocessors with templates

## CSS Pseudo & beyond
> **Mike Kivikoski

> tw: [@mkivikoski](http://twitter.com/mkivikoski)

> w: [bit.ly/pseudo-slides](http://bit.ly/pseudo-slides)

> design build test repeat podcast

* `:classes` vs `::elements`
* lots of different types now available

## Creating Beautiful, Accessible, and User-Friendly Forms
> **Clarissa Peterson**

> tw: [@clarissa](http://twitter.com/clarissa)

* less inputs is better for the user
* use the newer input types - `month, date, datetime, email, url, number`
  * use min and max to get logical dates
  * pattern matching using regex
* avoid dropdowns if lower amount of options
* radiobuttons as buttons using `input:checked` 
  * wrap in a label, use a pseudo element or add a span inside after the input 
* optgroups to organize big dropdowns
* don't use placeholders without labels
* default placeholder text doesn't meet accessibility standards
* pseudo `:valid, :invalid` with items that have a pattern and required attribute

## Flipping Tables
> **Stephanie Hobson**

> tw: [@stephaniehobson](http://twitter.com/stephaniehobson)

* techniques to flip tables from wide to tall
* creating structure
  * `thead, tbody, tfoot` 
  * tables can have multiple tbodys
  * attributes: `scope`
* designing tables
  * left align text, right align numbers with monospace fonts
  * contrast, repitition, alignment, proximity
* styling
  * `vertical-align: middle`  on td th
  * border collapse and spacing on `table` only
  * general styling first then overriding them
  * td:nth-child for column specificity 
  * tr:nth-child td for rows
* adapting tables to small screens
  * change content (thousands of etc)
  * linearize data by changing display types on `tr` and `td`
  * size constrained container with overflow-x
  * sticky headings with js (or some hacky markup/css combinations)
  * change to graph format with dense information
* examples
  * hand tailoring to each context of use

## Components, tools, and services
> **Alice Bartlett**

> tw: [@alicebartlett](http://twitter.com/alicebartlett)

* considerations for creating a component system
* financial times is fragmented, needed a system to maintain consistency
* components
  * html, css, js
  * prefix for system (origami uses `o`, like `o-video`)
* how to developers use the components in their projects 
* the best tooling is no tooling
* if sites all use the same language === easy
* however - different languages require different approaches
  * option 1 - template resolution for every language 
  * option 2 - no templating
* Using Origami
  * use copy and paste
  * needs consistent naming conventions (in this case, BEM)
  * Build service that generates code needed for components
  * NPM package for smaller things like color 
* Documentation
  * needs to reach your user base's expectations
  * be approachable
  * documentation styleguide is useful
* Marketing 
  * need to sell it within the organization
  * get advocates in the organization
* Support
  * be kind and open to their hesitation
  * addressing concerns
* Examples
  * [https://www.futurelearn.com/pattern-library](https://www.futurelearn.com/pattern-library)
  * lightning design system

## PostCSS in Sass
> **James Steinbach**

> tw: [@jdsteinbach](http://twitter.com/jdsteinbach)

> w: [https://jdsteinbach.com/sass-postcss/#/](https://jdsteinbach.com/sass-postcss/#/)

> gh: [www.github.com/jdsteinbach](http://www.github.com/jdsteinbach)

* Don't let pride stop you from trying new tools
* Both are preprocessors
* PostCSS generates an abtract syntax tree of CSS
  * this gives us an API to loop through the object and modify it
* Sass, Less, Stylus pros
  * variables
  * conditionals & loops
  * functions
  * documentation and community
* PostCSS Pros
  * manipulate CSS
    * vendor prefixes, syntax cleanup, sorting, shortening, formatting
  * custom syntax
    * things like grid builders - `@include span(3 of 12);` versus `span: 3 12;`
* PostCSS tips
  * avoid non-css input
  * careful with "prolly-fill" code
* Plugins
  * autoprefixer
  * postcss-sorting
  * cssnano
  * (**my fav**) stylelint (highlights pitfalls like declarations that have width declared but is set to `display: inline;`)
  * css-colorguard
  * cssstats
  * list-selectors
  * postcss-bem-linter

## SVG: so very good
> **Tyler Sticka**

> tw: [@tylersticka](http://twitter.com/tylersticka)

* how to make resolution independent icons
  * triangles with clever border hacks
* Icon fonts are the most pervasive hack
* Github legitimized it with release of octicons, bootstrap with font awesome
* How it works
  1. start with svgs
  2. map to unicode (usually in private use area)
  3. generates binary font files
  4. Optimize legibility in css
  5. Use pseudo elements with classes
* Convenience trumps the problems with it
* Icon fonts create issues for dislexic users with specific extensions that replace webfonts
  * all the icons get replaced with the lovely blank box (gobble-dee-gook as he said)
* ⭐⭐⭐⭐🐴
* Adobe gave us postscript to describe vectors for print
* Bitmap sucks for icons (well basically)
* Scalable Vector Graphics to the rescue!
  * vector based
  * XML based
  * subset of HTML5
* 97% of global user support (better support than font-face)
* SVG is an open format (not a black box like JPG, GIF, etc)
* Opens up possibilities to access all component parts
* `currentColor` inherits from parent CSS color
* `<style>` blocks with media queries in the SVG source file - **NICE**
* manipulate images with filters
* Useful, accessible, fun
