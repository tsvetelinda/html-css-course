# Introduction to HTML & CSS

## General Facts
* The first version of HTML was created in 1992.
* Since 2008, we are using HTML5.
* You can include literal tags inbetween tags like this: &lt;time&gt; -> `<time>`

## `<header></header>`
* represents introductory content
* it may contain:
    * headings
    * logo
    * search form

## `<nav></nav>`
* defines a set of navigation links
* holds an unordered set of elements

## `<main></main>`
* holds the main content of a document
* helps crawlers (= automated programs or scripts, used by search engines to browse the web and index its content)
* there should only be one `<main>` element in a document
* wrap the most important information in the `<body>`

## `<aside></aside>`
* sidebars (left or right)

## `<footer></footer>`
* a document/section footer
* it typically contains navigation links and copyright data

## `<section></section>`
* represents a standalone section
* sections may have a header, a couple of articles and a footer

## `<article></article>`
* represents a self-contained composition in a document, page, application or site
* intended to be independently distributable or reusable
* examples: forum post, magazine, newspaper article, blog entry

## `<figure></figure>`
* used for any type of media 
```
<figure>
    <img src="pic_trulli.jpg" alt="Trulli">
    <figcaption>
        Fig.1 Trulli, Puglia, Italy.
    </figcaption>
</figure>
```

## `<details> + <summary>`
* additional details that the user can view or hide
* the summary defines a visible heading for the details
* something like accordion
```
<details>
    <summary>Some details</summary>
    <p>More info about the details.</p>
</details>
```

## `<time> + <address>`
* `<time>` represents human-readable time. 
    * Search engines can produce smarter results.
    * There is no visual representation for the user.
    * The exact date can be defined in the `datetime` attribute in a format: `YYYY-MM-DD HH:mm:ss TZ`
    * You can define only hours too: `<time datetime="13:45">13:45 (1:45 PM)</time>`
    * `<time datetime="2023-01-01 13:45">January 1, 2023, at 13:45</time>.`
* `<address>` represents the contact information for site author/owner

## Main HTML tags

### Headings `<h1>` to `<h6>`
* goes from biggest to smallest
* it is recommended to have only one `<h1>` tag on our page, because the main heading is only one.

### Paragraphs `<p>`
* used for text content

### Hyperlinks `<a>`
* external: `<a href="https://softuni.bg">SoftUni</a>`
* local: `<a href=#exercises>Exercises</a>` - take me to the element with ID 'exercises' on this same page
* relative: `<a href="../presentations/myPresentation.pptx">Presentation</a>`
* `target=_blank` - the link will be opened in a new tab in the browser
* `href=` - this is where we set the link

### Images `<img>`
* external files, inserted via the `<img>` tag
* we are not closing this tag!
* they have `src`, `alt` attributes (alt = alternative)

### Ordered Lists `<ol>`

### Unordered Lists `<ul>`
* available bullet types are:
    <li type="disc">disc</li>
    <li type="circle">circle</li>
    <li type="square">square</li>
    <li type="none">none</li>

### Definition Lists `<dl>`
* `<dl>` is used for creating the definition list
* `<dt>` is used for creating the definition term
* `<dd>` is used for creating the definition

```
<dl>
    <dt>HTML</dt>
    <dd>is a markup language</dd>
</dl>
```

### `<span>`
* a generic container used to group inline elements and apply styles or scripts to them
* does not create a new block on the page but rather allows you to apply CSS styles or JavaScript functionality to a section of text or other inline content within a block-level element (like `<div>`, for example).

### Other tags
* `</br>` - inserts a new line
* `<abbr></abbr>` - used to insert a hint for an abbreviature. For example: `<abbr title="World Wide Web">www</abbr>` -> `World Wide Web` (displayed on hover)
* `<em></em>` - used for emphasising on text. Makes it italic.
* `<strong></strong>` - used for bolding the text.
* `<blockquote></blockquote>` - used for inserting quoted text.
    * `<blockquote cite="linkToTheQuote">A quote here.</blockquote>`

## HTML Attributes
* `href`
* `src`

## How to link an HTML file with a CSS file?
* `<link rel="stylesheet" type="text/css" href="styles.css"`
* rel = relation
* Note that there is no closing link tag!

## CSS Styling
* `a.login { color: red; }` - only the `<a>` tags with class = 'login' will have this coloring.
* `input[type="text"]` - attribute selector, that will affect the elements, that have a tag 'input' and a type='text' attribute, attached to it.
* `* {background-color: red;}` - universal selector, that matches elements of any type.

### Combined Selectors
* `#news > h1` - targets the direct h1 children. (first line children) = `child selector`
* `#news article > h1` - targets the direct h1 children, that have a parent article. The article should be a child of the element with ID 'news'.
* `#news article p` - targets the p children with an article parent. The article should be a child of the element with ID 'news'. = `descendant selector`
* `#news p > b.red` - targets the direct child of a p with a tag b and class 'red'. The p should be a child of the element with ID 'news'.
* `#news span.date` - targets the span children of the element with ID 'news', that have a class 'date'.
* `article > p, section > p` - targets the direct p children of an article and a section at once.
* `div + p` - targets the `<p>` element that is directly after a `<div>` element.
* `div ~ p` - targets all `<p>` elements that are next siblings to a `<div>` element.

* `Inline styling` overrides any other formatting!

### Basic CSS Selectors
* `font-size` - defines the text size 
    * px / pt values: 1px = 0.75pt = 1/96 inch
    * em values - relative to the current size of the parent, multiplied by a scale factor. (Example: We have a parent container, where the font size is set to 18px. A child container, whose font-size is defined as 1.2em = 18px * 1.2 = 21.6px. Then if we have another child nested with font-size 1.2em, this will result in 25.92px);
    * rem values = relative to the HTML root size (the html element)
    * Summary: `em` is related to the current size of the parent, whereas `rem` is related to the font-size of the root ancestor.

* `font-weight` 
    * thin, normal, bold
    * value [100...900]
    * not all fonts support ths variety of the font's weight

* `font-style`
    * normal
    * italic
    * oblique (the letters are more slanted than italic)

* `text-align` - defines the horizontal alignment
    * left, right, center, justify (aligns it on both sides).

* `line-height` - defines the height of a single line of text
    * measures: unitless / pt / px / em / rem
    * usually the height of the line is 120% of the size of the font.

* `letter-spacing` - defines the spacing betweens the characters of a block of text
    * normal
    * define it via pixels

* `text-decoration` - defines how the text content of the element is decorated
    * overline
    * underline
    * line-through
    * none

* `text-indent` - defines the indentation of the element's first line of text
    * 0 -> the text is not indented
    * 40px -> the text is indented

* `text-overflow` - defines how the hidden text content behaves if it is overflowing
    * ellipsis - the overflowing content is replaced by '...'

* `text=transform` - specifies how to capitalize text
    * capitalize - turns the first letter of each word into a capital letter
    * uppercase - turns all characters to uppercase
    * lowercase - turns all characters to lowercase

* `word-break` - defines how words should break when reaching the end of line.
    * normal - words with no space will NOT break
    * break-all - words with no space will break as soon as they reach the end of a line.

* `text-shadow` - defines the shadow of the text content
    * none
    * {horizontal} {vertical} {blur} {color}

* `color`

* `background-color`

* `mouse-cursor` - defines the mouse cursor when hovering the element
    * pointer
    * move
    * none, etc.

* `outline` - surround our element with some styling. Should not be congused with `border`.
    * `outline-width`
    * `outline-style`
    * `outline-color`



