# HTML

### Resources  
[WebPlatform](webplatform.org)  
[Mozilla](devloper.mozilla.org)  
[w3](w3.org)

### Structure

```html
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
- `nbsp`, `amp`, `copy`...

### Alteration
`<em></em>` or `<i></i>`: emphasis (logical or presentational)  
`<strong></strong>` or `<b></b>`: bold (logical or presentational)  
`<pre></pre>`: monospace, displayed as written  

Image  
`<img src="" width="" height="" alt="">`

### Links

`<a href="" title="" rel=""></a>`
- Point to a file to download
- *Add `download="NAME"` attribute for files that can be opened by a browser*

`<a href="#ID"></a>`: link to a section in the page

### Lists

Unordered List  
`<ul></ul>`
- `<li></li>`

Ordered List  
`<ol start="NUM" reversed type=""></ol>`
- `<li></li>`

Definition/Description List  
`<dl></dl>`
- `<dt></dt>`: term
- `<dd></dd>`: description

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
`<link rel="stylesheet" href="">`

## Scripting

External Scripts  
`<script src=""></script>`