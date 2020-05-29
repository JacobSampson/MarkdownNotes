# HTML

### Resources

[WebPlatform](https://www.webplatform.org)  
[Mozilla](https://www.devloper.mozilla.org)  
[W3](https://www.w3.org)

### Structure

```markup
<!DOCTYPE HTML>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <meta name="" description="">
        <title></title>
    </head>
    <body>
        <header></header>
        <nav></nav>
        <footer></footer>
    </body>
</html>
```

Content Models: flow, metadata, embedded, interactive, heading, phrasing, and sectioning

## Tags

`<meta></meta>`: set options, link to external scripts

### Structure

`<p></p>`: paragraph  
`<h1></h1>`: heading 1  
`<nav></nav>`: navigation  
`<article></article>`: complete, standalone piece of content  
`<section></section>`: section  
`<aside></aside>`: not wholly related  
`<div></div>`: division  
`<header></header>`  
`<footer></footer>`  
`<main></main>`: directly related to or expands upon the central topic of a document

`<br>`: line break

Character entity references `&NAME;`: insert special characters

* `nbsp`, `amp`, `copy`...

### Alteration

`<em></em>` or `<i></i>`: emphasis \(logical or presentational\)  
`<strong></strong>` or `<b></b>`: bold \(logical or presentational\)  
`<pre></pre>`: monospace, displayed as written

Image  
`<img src="" width="" height="" alt="">`

### Links

`<a href="" title="" rel=""></a>`

* Point to a file to download
* _Add `download="NAME"` attribute for files that can be opened by a browser_

`<a href="#ID"></a>`: link to a section in the page

### Lists

Unordered List  
`<ul></ul>`

* `<li></li>`

Ordered List  
`<ol start="NUM" reversed type=""></ol>`

* `<li></li>`

Definition/Description List  
`<dl></dl>`

* `<dt></dt>`: term
* `<dd></dd>`: description

## Attributes

`lang`: language  
`class`: category of content  
`id`: individual item  
`role`: accessibility values

## Styling

Inline Styles  
`< style="trait:value;"></ >`

`<style></style>`

External Styles  
`<link rel="stylesheet or text/css" href="">`

## Scripting

External Scripts  
`<script src=""></script>`

## W3Schools

### **Basic**

```markup
Attributes

alt    Specifies an alternative text for an image, when the image cannot be displayed
disabled    Specifies that an input element should be disabled
href    Specifies the URL (web address) for a link
id    Specifies a unique id for an element
src    Specifies the URL (web address) for an image
style    Specifies an inline CSS style for an element
title    Specifies extra information about an element (displayed as a tool tip)

Headings

<html>    Defines the root of an HTML document
<body>    Defines the document's body
<head>    A container for all the head elements (title, scripts, styles, meta information, and more)
<h1> to <h6>    Defines HTML headings
<hr>    Defines a thematic change in the content

Paragraphs

<p>    Defines a paragraph
<br>    Inserts a single line break
<pre>    Defines pre-formatted text

Formatting

<b> - Bold text
<strong> - Important text
<i> - Italic text
<em> - Emphasized text
<mark> - Marked text
<small> - Small text
<del> - Deleted text
<ins> - Inserted text
<sub> - Subscript text
<sup> - Superscript text

Quotations

<abbr>    Defines an abbreviation or acronym
<address>    Defines contact information for the author/owner of a document
<bdo>    Defines the text direction
<blockquote>    Defines a section that is quoted from another source
<cite>    Defines the title of a work
<q>    Defines a short inline quotation

Links

Use the <a> element to define a link
Use the href attribute to define the link address
Use the target attribute to define where to open the linked document
Use the <img> element (inside <a>) to use an image as a link
Use the id attribute (id="value") to define bookmarks in a page
Use the href attribute (href="#value") to link to the bookmark

The target attribute specifies where to open the linked document.
The target attribute can have one of the following values:

_blank - Opens the linked document in a new window or tab
_self - Opens the linked document in the same window/tab as it was clicked (this is default)
_parent - Opens the linked document in the parent frame
_top - Opens the linked document in the full body of the window
framename - Opens the linked document in a named frame

Images

Use the HTML <img> element to define an image
Use the HTML src attribute to define the URL of the image
Use the HTML alt attribute to define an alternate text for an image, if it cannot be displayed
Use the HTML width and height attributes to define the size of the image
Use the CSS width and height properties to define the size of the image (alternatively)
Use the CSS float property to let the image float
Use the HTML <map> element to define an image-map
Use the HTML <area> element to define the clickable areas in the image-map
Use the HTML <img>'s element usemap attribute to point to an image-map
Use the HTML <picture> element to show different images for different devices

Tables

Use the HTML <table> element to define a table
Use the HTML <tr> element to define a table row
Use the HTML <td> element to define a table data
Use the HTML <th> element to define a table heading
Use the HTML <caption> element to define a table caption
Use the CSS border property to define a border
Use the CSS border-collapse property to collapse cell borders
Use the CSS padding property to add padding to cells
Use the CSS text-align property to align cell text
Use the CSS border-spacing property to set the spacing between cells
Use the colspan attribute to make a cell span many columns
Use the rowspan attribute to make a cell span many rows
Use the id attribute to uniquely define one table

Lists

Use the HTML <ul> element to define an unordered list
Use the CSS list-style-type property to define the list item marker
Use the HTML <ol> element to define an ordered list
Use the HTML type attribute to define the numbering type
Use the HTML <li> element to define a list item
Use the HTML <dl> element to define a description list
Use the HTML <dt> element to define the description term
Use the HTML <dd> element to describe the term in a description list
Lists can be nested inside lists
List items can contain other HTML elements
Use the CSS property float:left or display:inline to display a list horizontally

Blocks

<div>    Defines a section in a document (block-level)
<span>    Defines a section in a document (inline)

IFrame

<iframe>    Defines an inline frame

Scripts

<script>    Defines a client-side script
<noscript>    Defines an alternate content for users that do not support client-side scripts

Head

<head>    Defines information about the document
<title>    Defines the title of a document
<base>    Defines a default address or a default target for all links on a page
<link>    Defines the relationship between a document and an external resource
<meta>    Defines metadata about an HTML document
<script>    Defines a client-side script
<style>    Defines style information for a document

Responsive

<meta name="viewport" content="width=device-width, initial-scale=1.0">

Computer Code

<code>    Defines programming code
<kbd>    Defines keyboard input 
<samp>    Defines computer output
<var>    Defines a variable
<pre>    Defines preformatted text

Entities

    non-breaking space    &nbsp;    &#160;
<    less than    &lt;    &#60;
>    greater than    &gt;    &#62;
&    ampersand    &amp;    &#38;
"    double quotation mark    &quot;    &#34;
'    single quotation mark (apostrophe)    &apos;    &#39;
¢    cent    &cent;    &#162;
£    pound    &pound;    &#163;
¥    yen    &yen;    &#165;
€    euro    &euro;    &#8364;
©    copyright    &copy;    &#169;
®    registered trademark    &reg;    &#174;

 ̀    a    a&#768;    à
 ́    a    a&#769;    á
̂    a    a&#770;    â
 ̃    a    a&#771;    ã
 ̀    O    O&#768;    Ò
 ́    O    O&#769;    Ó
̂    O    O&#770;    Ô
 ̃    O    O&#771;    Õ

 Symbols

 ∀    &#8704;    &forall;    FOR ALL
∂    &#8706;    &part;    PARTIAL DIFFERENTIAL
∃    &#8707;    &exist;    THERE EXISTS
∅    &#8709;    &empty;    EMPTY SETS
∇    &#8711;    &nabla;    NABLA
∈    &#8712;    &isin;    ELEMENT OF
∉    &#8713;    &notin;    NOT AN ELEMENT OF
∋    &#8715;    &ni;    CONTAINS AS MEMBER
∏    &#8719;    &prod;    N-ARY PRODUCT
∑    &#8721;    &sum;    N-ARY SUMMATION

Α    &#913;    &Alpha;    GREEK CAPITAL LETTER ALPHA
Β    &#914;    &Beta;    GREEK CAPITAL LETTER BETA
Γ    &#915;    &Gamma;    GREEK CAPITAL LETTER GAMMA
Δ    &#916;    &Delta;    GREEK CAPITAL LETTER DELTA
Ε    &#917;    &Epsilon;    GREEK CAPITAL LETTER EPSILON
Ζ    &#918;    &Zeta;    GREEK CAPITAL LETTER ZETA

©    &#169;    &copy;    COPYRIGHT SIGN
®    &#174;    &reg;    REGISTERED SIGN
€    &#8364;    &euro;    EURO SIGN
™    &#8482;    &trade;    TRADEMARK
←    &#8592;    &larr;    LEFTWARDS ARROW
↑    &#8593;    &uarr;    UPWARDS ARROW
→    &#8594;    &rarr;    RIGHTWARDS ARROW
↓    &#8595;    &darr;    DOWNWARDS ARROW
♠    &#9824;    &spades;    BLACK SPADE SUIT
♣    &#9827;    &clubs;    BLACK CLUB SUIT
♥    &#9829;    &hearts;    BLACK HEART SUIT
♦    &#9830;    &diams;    BLACK DIAMOND SUIT
```

### **Forms**

```markup
accept-charset    Specifies the charset used in the submitted form (default: the page charset).
action    Specifies an address (url) where to submit the form (default: the submitting page).
autocomplete    Specifies if the browser should autocomplete the form (default: on).
enctype    Specifies the encoding of the submitted data (default: is url-encoded).
method    Specifies the HTTP method used when submitting the form (default: GET).
name    Specifies a name used to identify the form (for DOM usage: document.forms.name).
novalidate    Specifies that the browser should not validate the form.
target    Specifies the target of the address in the action attribute (default: _self).

Elements

<form>    Defines an HTML form for user input
<input>    Defines an input control
<textarea>    Defines a multiline input control (text area)
<label>    Defines a label for an <input> element
<fieldset>    Groups related elements in a form
<legend>    Defines a caption for a <fieldset> element
<select>    Defines a drop-down list
<optgroup>    Defines a group of related options in a drop-down list
<option>    Defines an option in a drop-down list
<button>    Defines a clickable button
<datalist>    Specifies a list of pre-defined options for input controls
<output>    Defines the result of a calculation

Input Types

<input type="button">
<input type="checkbox">
<input type="color">
<input type="date">
<input type="datetime-local">
<input type="email">
<input type="file">
<input type="hidden">
<input type="image">
<input type="month">
<input type="number">
<input type="password">
<input type="radio">
<input type="range">
<input type="reset">
<input type="search">
<input type="submit">
<input type="tel">
<input type="text">
<input type="time">
<input type="url">
<input type="week">

Input Restrictions

disabled    Specifies that an input field should be disabled
max    Specifies the maximum value for an input field
maxlength    Specifies the maximum number of character for an input field
min    Specifies the minimum value for an input field
pattern    Specifies a regular expression to check the input value against
readonly    Specifies that an input field is read only (cannot be changed)
required    Specifies that an input field is required (must be filled out)
size    Specifies the width (in characters) of an input field
step    Specifies the legal number intervals for an input field
value    Specifies the default value for an input field
```

