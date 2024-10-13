# Working with Forms
In this folder, you'll find the notes I've taken while studying the topic (primarily based on SoftUni lectures). I've enriched the content and organized it in a simple yet clear manner for easy understanding. You'll also find a collection of exercises related to each lecture topic. The solutions are my own, while the exercise descriptions remain the property of SoftUni.

Each folder contains:

* HTML and CSS files with the solution to the exercises.
* A screenshot of the expected result for visual reference.
* A .txt file with the text used in the exercises, in case you'd like to try them out yourself.

Feel free to explore the material, whether for learning or practicing!
<hr>

## HTML Forms
* the HTML form element represents a document section that contains interactive controls for submitting information to a web server.

## Form Attributes

### Method
* the HTTP method that the browser uses to submit the form.
    * `POST`
        * corresponds to the HTTP POST method
        * form data is included in the `body` of the form and sent to the server
    * `GET`
        * corresponds to the HTTP GET method.
        * form data is included in the URI with a '?' as a separator, and the resulting URI is sent to the server.
        * this method can be used when the form has no side-effects and the contains only ASCII characters.

### Label
* the caption for an item in a user interface.
```
<label for='full-name'>Name</label>
<input id='full-name' name='full-name' type='text'/>
```
* the label text is programatically and visually associated with its corresponding text input.


## Additional Insights Gained from Completing the Lab & Exercises
* Use `<button>` for actions that involve interactions (such as triggering JavaScript functions), and `<a>` for navigation purposes, in order to maintain correct semantics throughout the page.
