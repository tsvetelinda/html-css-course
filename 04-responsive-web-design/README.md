# Responsive Web Design

In this folder, you'll find the notes I've taken while studying the topic (primarily based on SoftUni lectures). I've enriched the content and organized it in a simple yet clear manner for easy understanding. You'll also find a collection of exercises related to each lecture topic. The solutions are my own, while the exercise descriptions remain the property of SoftUni.

Each folder contains:

* HTML and CSS files with the solution to the exercises.
* A screenshot of the expected result for visual reference.
* A .txt file with the text used in the exercises, in case you'd like to try them out yourself.

Feel free to explore the material, whether for learning or practicing!

<hr>

## What is Responsive Web Design?

* an approach to make web pages render well on all screen sizes and resolutions, while ensuring good usability
* it is a way to design for a multi-device web

## Media Queries
* they allow us to run a series of tests, and apply CSS selectively to style the page appropriately for the user's needs.
* In order to apply media queries, we need to include this line of code in our HTML: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
```
/* For screens larger than 600px (e.g., tablets) */
@media screen and (min-width: 600px) {
  body {
    font-size: 18px;
  }
}

/* For screens smaller than 600px (e.g., smartphones) */
@media screen and (max-width: 600px) {
  body {
    font-size: 16px;
  }
}
```

## Media Types
* describe the general category of a given device
    * all
    * print
    * screen

## Media Features
* describe a specific characteristic of the user agent, otuput device or environment.
    * min-width
    * max-width
    * width
    * orientation
    * hover
    * pointer
* `Logical operators` can be used to compose a complex media query:
    * `and` - combines multiple conditions
    * `not` - excludes a specific media type or feature
    * `only` - applies the styles only if the media query matches exactly
* Media queries can also be combined into a single rule by separating them with commas (they work as OR).
* Media queries are inherited.

## Additional Insights Gained from Completing the Lab & Exercises
* `<code></code>` - a tag, used for inserting a piece of code in the HTML structure.
* `<pre></pre>` - a tag, used for preserving white-space; typically used with the `<code>` tag, so it preserves the code structure.
* We can apply padding directly to the `<a>` element, so that the user can select easily. 
* We can position pseudo elements in an easier way if their parents have `display: flex;` property. For example, we can make use of the gap attribute.