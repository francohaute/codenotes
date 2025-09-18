# Basics

## Sources

- [CSS tricks](https://css-tricks.com/almanac/properties/)

- [Flexbox](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/)
- [Comeau's reset file](https://www.joshwcomeau.com/css/custom-css-reset/)

- Why you should only place the href on the head of the html file?
- Cascade:
    - specificity.
    - Inheritance:
        - What beats Inheritance?
    - The tie-braker of all is that is there are more than one element with the 
      same specificity then the last declared one will prevaled.
- Boxing principle:
    - block and inline
    - span
- flexbox:
    - flex container and flex items
    - direction
    - soft-wrap
- alignment:
    - primary axis and cross axis
- hypothetycal size:
    - depending on the layout the parent might restrict the children size
- What is box-sizing? How can you pervent a child who uses 100 percent of width 
  to overflow the parent?

## Units

- Absolut and relative units.
- line height and font size

- Color keywords are not used in production. Their purpose is for examples to 
  tell the viewer what to look for.

- what is the difference between using an alpha color code and setting the opacity?

## Default style

- What are resets?
- How to fix the problems of dealing with differents defaults?

## Selectors

- pseudo classes and dynamic pseudo classes [link](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Pseudo_classes_and_elements) 
- pseudo elements [link](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) 
- attribute selectors [link](https://learn.shayhowe.com/advanced-html-css/complex-selectors/) 
- target identifier

## Fonts

- Fallback font and web safe fonts.
- How to package a optimize font (woff) [link](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Text_styling/Web_fonts)
- Best practices for font rendering [link](https://web.dev/articles/font-best-practices)
- Best practices for font size [link](https://web.dev/learn/design/typography)

## Functions

- min, max and clamp [link](https://web.dev/articles/min-max-clamp)

## Custom properties

- How does inheritance works? What is the default?
- What are valid reasons to limit the scope of a property?
- How to define multiple fallbaacks?
- @property at rule: [docs](https://developer.mozilla.org/en-US/docs/Web/CSS/@property)
    - What are the advantages vs a regular declaration?
- When is a property considered invalid? How does the browser deals with it?
