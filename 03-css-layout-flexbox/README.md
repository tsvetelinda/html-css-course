# CSS Layout - Flexbox
In this folder, you'll find the notes I've taken while studying the topic (primarily based on SoftUni lectures). I've enriched the content and organized it in a simple yet clear manner for easy understanding. You'll also find a collection of exercises related to each lecture topic. The solutions are my own, while the exercise descriptions remain the property of SoftUni.

Each folder contains:

* HTML and CSS files with the solution to the exercises.
* A screenshot of the expected result for visual reference.
* A .txt file with the text used in the exercises, in case you'd like to try them out yourself.

Feel free to explore the material, whether for learning or practicing!
<hr>

## Flexbox
* `Flexbox` (short for Flexible Box Layout) is a `CSS layout module` designed to provide an efficient way to align and distribute space among items in a container, even when their size is unknown or dynamic. 
* Flexbox is great for building layouts that are flexible, responsive, and can adapt to different screen sizes.
* Flexbox works along two axes:
    * `Main Axis`: This is the primary axis along which the flex items are laid out. By default, `it runs horizontally` from left to right (when flex-direction is set to row).
    * `Cross Axis`: This is the axis `perpendicular to the main axis`. The alignment and spacing along this axis can be controlled using properties like align-items or align-content.
* What problem does Flexbox solve?
    * Before Flexbox, developers had to rely on floats, inline-blocks, or complicated hacks to create flexible and responsive layouts. These methods were often brittle and didn't provide consistent behavior across different screen sizes or when the content inside the elements varied.
    * **Flexbox solves these issues by**:
        * Aligning Items Easily
        * Equal Space Distribution
        * Flexible Item Sizes (items can grow or shrink, according to the available space)
        * Consistent Layouts (even when content size changes dynamically)

### Properties for the Container
* This is the parent element where flex properties are applied. Once an element is declared as a flex container (`display: flex`), its direct children (flex items) are arranged according to the flexbox rules.

#### Flex Direction
* defines how flexbox items are ordered within a flexbox container
    * by default: `row`
    * `row-reverse`
    * `column`
    * `column-reverse`

#### Flex Wrap
* defines if flexbox items appear on a single line or on multiple lines within a flexbox container
    * `nowrap` - the flexbox items will remain on a single line, no matter what
    * `wrap` - the flexbox items will be distributed among multiple lines if needed
    * `wrap-reverse` - any additional line will appear before the previous one

#### Flex Flow
* a shorthand for `flex-direction` and `flex-wrap`
* the default value is `row nowrap`

#### Justify Content
* defines how `flexbox items` are aligned, according to the `main axis`, within a flexbox container.
    * `flex-start` - the items are pushed towards the start of the container's main axis
    * `flex-end` - the items are pushed towards the end of the container's main axis
    * `center` - the items are centered along the container's main axis
    * `space-between` - the first and last elements are placed in the two ends of the line, whereas **the remaining space** is evenly distributed between the flexbox items
    * `space-around` - the remaining space is distributed around the items - adding space before the first item and after the last one.
    * `space-evenly` - all elements are distributed evenly on the line

#### Align Items
* defines how `flexbox items` are aligned according to the `cross axis`, within a flexbox container.
    * `flex-start`
    * `flex-end`
    * `center`
    * `baseline` - the items are aligned at the baseline of the cross axis - the line where all of the letters will stand on.
    * `stretch` - the items will stretch across the whole cross axis.

#### Align Content
* deals with alignment of multiple lines (with flex items) in a flex container with extra space.
* it controls the spacing between the lines of items when there is extra space in the container.
* only applies if `flex-wrap: wrap` is present and if there are multiple lines of flexbox items.  
    * `flex-start`
    * `flex-end`
    * `center`
    * `space-between`
    * `space-around`

### Properties for the Items
* These are the direct children of the flex container. The flex properties control how these items are laid out inside the container.

#### Order
* defines the order of a flexbox item (by default, it is the order, defined in the HTML code)
* the order is relative to the flexbox items' siblings

#### Flex Grow
* defines how much a flexbox item should grow if there's space available
* the element will not grow if there's space available, in a way that it will only use the space it needs

#### Flex Basis
* defines the initial size of a flexbox item
* the element will wrap it content to avoid any overflow (in case we've defined an exact value)
* `flex-basis: auto;` - the element will be automatically sized based on its content, or on any height or width value if they are defined.

#### Flex
* shorthand for `flex-grow`, `flex-shrink`, `flex-basis`
* the default value is `0 1 auto`

#### Align Self
* works like `align-items`, but applies only to a single flexbox items, instead of all of them.
* `align-self: auto;` - will take the value of `align-items`

## Additional Insights Gained from Completing the Lab & Exercises
* `gap` - adds gap between the flex-items (children of the flex-container). It works top, bottom, left, and right. If we have some margins the `gap` will consider them as the end of the element, and work with the free space between the elements.
* If we apply `display: flex;` to a container, but we want some elements of it to behave like block elements, we can do it as follows:
```
.columns > header, .columns > footer {
    flex: 0 0 100%;
}
```
It is important to apply: `flex-wrap: wrap;` to the parent container, so the elements do not exceed their dedicated space.
* It's good practice to place elements in ordered/unordered lists, if it is convenient, since this will produce smarter results by the search engines.
* `flex: 1 1 auto;` = grow, if there is more space; shrink if there is less space; be as wide as the space provided

