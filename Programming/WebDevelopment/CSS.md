# CSS

### Resources
[w3schools](https://www.w3schools.com)  
[coderops](https://www.tympanus.net/codrops/css_reference)  
[HTML Dog](https://www.htmldog.com/references/css/properties)  
[CanIUse](https://www.caniuse.com)

### Selection

Class selection: `.`  
ID selection: `#`  

Precedence: inline, embedded, external

## **General**

Comments: `/* */`

*Do not add a space between property values and the unit*

Background order
1. background-color
2. background-image
3. background-repeat
4. background-attachment
5. background-position

Clearfix
```css
.clearfix::after {
  content: "";
  clear: both;
  display: table;
}
```

Attribute selectors  

`[attribute="value"]`: single attribute  
`[attribute~="value]`: from multiple attributes  
`[attribute|="value]`: starting with  
`[attribute^="value]`: begins with  
`[attribute$="value]`: ends with  
`[attribute*="value]`: contains

Counters  

counter-reset - Creates or resets a counter  
counter-increment - Increments a counter value  
content - Inserts generated content  
counter() or counters() function - Adds the value of a counter to an element

### Units

cm: centimeters  
mm: millimeters  
in: inches (1in = 96px = 2.54cm)  
px : pixels (1px = 1/96th of 1in)  
pt: points (1pt = 1/72 of 1in)  
pc: picas (1pc = 12 pt)  

em: Relative to the font-size of the element (2em means 2 times the size of the current font)   
ex: Relative to the x-height of the current font (rarely used)   
ch: Relative to width of the "0" (zero)   
rem: Relative to font-size of the root element   
vw: Relative to 1% of the width of the viewport   
vh: Relative to 1% of the height of the viewport   
vmin: Relative to 1% of viewport's smaller dimension   
vmax: Relative to 1% of viewport's larger dimension   
%: Relative to the parent element

## **Animation**

`pointer-events: none`: remove events from pointer triggers  

### Keyframes

```css
.element {
  animation: [name] [duration] [timing-function] [delay] [iteration-count] [direction] [fill-mode] [play-state]
}

@keyframes name {
  from {

  } to {

  }

  ...

  0%

  100%, ...
}
```

### Snippets

`:nth-child(#)`

### Selection Symbols

`+`: adjacent children  
`>`: direct children  
`~`: all following


## **SASS**

`@for $i from NUM through NUM`