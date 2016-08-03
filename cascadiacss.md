# CascadiaFest

<!-- MarkdownTOC -->

- [Color Theory](#color-theory)
- [Bauhaus Design in the Browser](#bauhaus-design-in-the-browser)
- [Code Patterns for Pattern-Making](#code-patterns-for-pattern-making)

<!-- /MarkdownTOC -->


## Color Theory
> **Natalya Shelborne**
> tw: @natalyathree

* Color wheel - color relationships
* http://tallys.github.io/color-theory/
* sass functions 
* HSL maps to cognitive model of how colors relate - using degrees
* Make it pop - one color saturated, other colors toned down
* third of your viewport a neutral color to reduce cognitive load 
* color picking is a decision tree based on two complimentary colors

_Questions_
* only use two colors?

## Bauhaus Design in the Browser
> **Justin McDowell**
> tw: @revoltpuppy

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
* brauser support 

## Code Patterns for Pattern-Making
> **Miriam Suzanne**
> tw: @mirisuzanne

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

