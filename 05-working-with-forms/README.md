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

### Input
* used to create interactive controls for web-based forms in order to accept data from the user.
* a wide variety of types of input data and control widgets are available, depending on the device and user agent.
* we can add an attribute `required` if we want to block the form from submitting, if the fields in question are empty.
* we can add an attribute `placeholder`, if we want to add a hint to the user for what they are supposed to fill in.
* inputs DO NOT have pseudo elements.
* we can add the attribute `minlength` if we want to restrict the number of chars.
* we can add the attribute `pattern`, where we can define a regex for the expected input format.
* If we want to have a fieldset with radio buttons, we should put the same 'name' attribute to all of them, so we can choose one OF them. Otherwise, we will be able to select more than one radio button.

### Textarea
* a multi-line plain-text editing control, useful when you want to allow users to enter a sizeable amount of free-form text.

### Select & Option
* `<select>` represents a control that provides a menu of options.
* `<option>` is used to define an item, contained in the `<select>`

### Button
* interactive element, activated by a user with a mouse, keyboard, finger, voice command, or other assistive technology. Once activated, it then performs an action, such as submitting a form or opening a dialog.

### Fieldset & Legend
* the `fieldset` element is used to group several controls as well as labels within a web form.
* the grouped labels are surrounded by a border and have a title added to them automatically by the web browser, without any additional CSS required.


## Additional Insights Gained from Completing the Lab & Exercises
* Use `<button>` for actions that involve interactions (such as triggering JavaScript functions), and `<a>` for navigation purposes, in order to maintain correct semantics throughout the page.
