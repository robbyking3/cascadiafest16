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
* when to use tables
  * 
* creating structure
* designing tables
* styling
* adapting tables to small screens