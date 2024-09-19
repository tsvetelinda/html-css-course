# CSS Box Model and Typography
#### Disclaimer
_Most of the information presented in this document is based on the lectures and materials provided by SoftUni. However, I have enriched and expanded upon the content with additional explanations and insights._

## CSS Basic Box Model
* When laying out a document, the browser's rendering engine represents each element as a `rectangular box`, according to the `standard CSS basic box model`.
* CSS determines the size, position, and properties of these boxes.
* **Box Model Properties**
    * width
    * height
    * padding
    * border
    * margin

## Properties
### Display
* defines the `display type` of an element - how the box participates in the flow layout, and how the children of the box are laid out in it.
#### Display Types
* `display: block;`
    * such elements occupy the entire space of their parent container, thereby creating a 'block'.
    * browsers typically display the block-level element with a **new line both before and after the element**. 
    * **by default** such elements are `main, header, article, section, fieldset, nav, ul, ol, li, form, h1-h6, p, div`.

* `display: inline;`
    * such elements occupy the space bounded by the tags, defining them.
    * they don't start on a new line - they appear on the same line as the content and tags beside them.
    * **by default** such elements are `a, label, map, span, strong, em, i, img, textarea, input, button, select`
    * `margins` and `paddings` can be added only `horizontally` for such elements.

* `display: inline-block;`
    * lets us add `margins` and `paddings` `vertically` as well
    * lets us add **width and height**
    * used mostly for creating navigation links horizontally

### Width
* defines the width of the element.
* **by default**, the width sets `the size of the content area` (excluding padding and border).
* If `box-sizing: border-box;` is applied, **the width includes the padding and border along with the content**, so the total element's width will not exceed the value specified by width.
* `fixed width` -> pixels / em / rem
* `relative width` -> percentage (relative to the parent's width)
* by default, the width will remain 100% and the padding and border will push inwards (if the box has static or relative positioning, and if we haven't declared the width explicitly).
* if you explicitly set the width of the box to be 100%, the padding will push the box outward.
* `auto` = autocalculated width = 100%

### Min-width
* defines the minimum width of the element
* if the element's actual width is less than the min-width value, then the min-width will be applied. Otherwise, the min-width has no effect.

### Max-width
* defines the maximum width of the element
* if the element's actual width is more than the max-width value, then the max-wdith will be applied. Otherwise, the max-width has no effect.
* `max-width: none;` - the element has no limt in terms of width.

### Height
* specifies the height of an element.
* **by default** it defines the height of the `content area`: `auto` = auto-calculated height
* if `box-sizing: border-box;` it defines the height of the border area.

### Min-height
* defines the minimum height of the element
* if the element's actual height is less than the min-height value, then the min-height will be applied. Otherwise, the min-height has no effect.

### Max-height
* defines the maximum height of the element
* if the element's actual height is more than the max-height value, then the max-height will be applied. Otherwise, the max-height has no effect.
* `max-height: none;` - the element has no limt in terms of height.

### Margin
* `margin: top right bottom left` -> **clockwise**
* `margin: top&bottom left&right`
* defines the space `outside` the element
* `margin: 50px;` - defines a margin of 50px on all `four sides` of the element

### Padding
* `padding: top right bottom left` -> **clockwise**
* `padding: top&bottom left&right`
* defines the space `inside` the element
* `padding: 50px;` - defines a padding of 50px on all `four sides` of the element

### Border
* sets an element's border
* `border: border-width border-style border-color;`
* `border-radius` - make the corners of the border rounded
* We can use it like this too: `border-top-left-radius: 30px;`

### Outline
* a line that is drawn around elements, outside the borders.
* it may overlap other content
* not part of the element's dimensions
* the element's total width and height is not affected by the width of the outline.

## The CSS Box Model
* defines how the different parts of a box — margin, border, padding, and content — work together to create a box that you
can see on a page.
* a `Block box` in CSS consists of:
    * `Content box`: the area where your content is displayed
    * `Padding box`: sits around the content as white space
    * `Border box`: wraps the content and any padding
    * `Margin box`: the outermost layer, wrapping the content, padding, border.
### Box-sizing
* sets how the total width and height of an element are calculated.
* **by default**, it is `content-box` (The Standard CSS Box Model). In this case, padding and borders are added to the content size, which may cause the element to exceed the specified width/height.
* `border-box` (The Alternative CSS Box Model) ensures that padding and borders are included within the specified width and height of the element, preventing it from exceeding the specified size. **Margins remain outside and are not affected by the box-sizing property.**
* **Universal Box Sizing with Inheritance**
```
html {
    box-sizing: border-box;
}

*, *:before, *:after {
    box-sizing: inherit;
}
```

## Typography
### Choosing a comfortable measure
* `measure` = the number of characters in a single line of a column of text.
* **satisfactory** length of line = 45 to 75 characters
* **ideal** = 66-character line (counting both letters and spaces)
* for multiple column work - 40-50 characters.
* `line-height` = the property which is used to define the space between the lines.
* `font-family` = a set of fonts, that share common design features.
### Generic Font Families
* `serif`
* `sans-serif`
* `monospace`
* `cursive`
* `fantasy`
<br><br>
* `@font-face` is a CSS rule used to define custom fonts that can be downloaded and used on a webpage. It was initially introduced in CSS1, but became widely supported and popular in CSS3. This technique allows you to reference and automatically download remote fonts for use in web design, even if they are not installed on the user's device.
* When using `Google Fonts`, it's good practice to document their usage, as Google does collect some basic data (like IP addresses) when fonts are downloaded from their servers.
* `Font Awesome` provides vector icons, emojis, etc. 
* Web font libraries provide a link for embedding the desired font.

## Position
* specifies the type of positioning method used for an element
* elements are then positioned using the top, bottom, left, and right properties (These properties will only work if the `position` property is set first. They also behave differently depending on the position value.)

### `position: static;`
* the default state of every element
* puts the element into its normal position in the document layout flow
* it will **NOT** react to the following properties: top, bottom, left, right, z-index

### `position: relative;`
* the element remains in the normal document flow, but its final position can be offset sing the top, bottom, left, right, z-index properties.
* the space it originally occupies in the layout is preserved, even though the element itself is moved

### `position: absolute;`
* the element is removed from the normal document flow, and its final position can be modified, using the top, bottom, left, right, z-index properties.
* the positioning is done, based on the `upper left corner of the parent`
* if there is no such ancestor, it is positioned relative to the initial containing block, which is usually the `<html>` or `<body>` element

### `position: fixed;`
* the element is removed from the normal document flow, and no space is created for the element in the page layout.
* the element is positioned relative to its initial containing block.
* the element's final position can be modified, using the top, bottom, left, right, z-index properties.
* it's fixed throughout the entire page and is not affected by the scrolling.

### `position: sticky;`
* a hybrid of relative and fixed. The element is treated as relative until it reaches a specified point (using top, bottom, left, or right), and then it becomes fixed.
* the element will "stick" to the top, bottom, left, or right of its nearest scrollable ancestor when the user scrolls past it.
* it only works within its containing block (e.g., a parent with overflow properties). The element’s position can be modified using top, bottom, left, and right, but only after it reaches the "sticky" point.

### `z-index`
* sets the z-order of a positioned element and its descendants
* overlapping elements with a larger z-index cover those with a smaller one.
* default value: auto, meaning that it is defined by the order in the HTML code.
* negative values can be used too, and as a result, the target element will be moved behind its siblings








