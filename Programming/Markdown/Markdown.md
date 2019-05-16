Markdown
=======

# H1
## H2
### H3
#### H4
##### H5
###### H6

## Style

Paragraphs are separated by a blank line.

Two spaces at the end of a line  
produces a line break.

Blank lines:

<br><br>

Horizontal rule:

---

## Emphasis

Text attributes _italic_, *italic*, 
__bold__, **bold**, `monospace`, ~~strikethrough~~.

_Combining **items** **`with`** `different` ~~styles~~_

## Lists

Bullet list:

* fruits
    * peaches
    * oranges
    * pears

+ veggies
    - broccoli
        * green


Numbered list:

  1. wash
  2. rinse
  3. repeat

## Images

![Image](/images/image.png)

![Image](/image.png "image")

## Links

http://example.com - automatic!

[Example link](http://example.com)

[Example link with title](http://example.com "Title")

A <a href="http://www.yahoo.com">link</a> in HTML.

### Reference links

A [reference link][example].

  [example]: http://example.com

A [relative reference to a file](../blob/master/LICENSE)

  A [reference link using numbers][1]

[1]: https://example.com

## Blockquotes

> Markdown uses email-style > characters for block quoting.

## Inline

Inline <abbr title="Hypertext Markup Language">HTML</abbr> is supported.

I think you should use an
`<addr>` element here instead.

## Code
    
    Indenting by four spaces (tab) marks a segment as code

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```
 
```python
s = "Python syntax highlighting"
print s
```

```java
String s = "TEST";
```

```
No language indicated, so no syntax highlighting. 
```

## HTML

<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>

### Embedded videos

<a href="http://www.youtube.com/watch?feature=player_embedded&v=YOUTUBE_VIDEO_ID_HERE
" target="_blank"><img src="http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>

[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)](http://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)

---

## _Additions_

---

## Tables
Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

<br><br>

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3

## Blockquotes

> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **emphasis** into a blockquote.