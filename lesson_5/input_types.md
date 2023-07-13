# Input Types

`input` element is the most versatile and widely used form widget. 

Most controls are `input` elements. 

Some look identical in most browsers, such as:
  - `text`
  - `email`
  - `tel`

Some look very different:
  - `text` input vs `submit` button or `checkbox`

#
#

When creating an `input` element: 
- start with the `type` attribute

## `type`

Most common input types: 

### `type="text"`
  - creates simple text entry field
  - user can enter any text desired in this control
    - developer should almost always validate data
  - use `maxlength` attribute to specify input max length

  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        First Name
        <input type="text" name="first_name" value="Tom">
      </label>
    </fieldset>
  </form>
  ```

#

### `type="password"`
  - creates single-line text field with obscured value
  - used for passwords and other sensitive information
  - use `maxlength` to limit input length

  ```html
  <form action="#" method="post">
    <fieldset>
      <label for="password">Password</label> 
      <input type="password" name="password" id="password"
             value="12345" size="35">
    </fieldset>
  </form>
  ```
  *the `size` attribute in the `input` element is used to specify the size of the text box as it is displayed*

#

### `type="email"`
  - allows entry of email address
  - developer should implement validation as well. 

  ```html
  <form action="#" method="post">
    <fieldset>
      <label for="email">Email</label>
      <input type="email" name="email" placeholder="username@domain">
    </fieldset>
  </form>
  ```

#

### `type="tel"`
  - allows entry of telephone number
  - do not validate due to wide variance of input worldwide

  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        Phone
        <input type="tel" name="phone" placeholder="(###) ###-####">
      </label>
    </fieldset>
  </form>
  ```

#

### `type="checkbox"`
  - allows user choose one or more items from options
  - use `value` attribute to give the value the form sends to the server when the user selects that checkbox
  - use the `checked` attribute to pre-select checkboxes
  - use the `name` attribute to name a set of related checkboxes
  - user can select zero or more items in each set. 

```html
<form action="#" method="post">
  <fieldset>
    <label>
      <input type="checkbox" name="choice" value="search">
      Sort search results
    </label>
    
    <label>
      <input type="checkbox" name="choice" value="google" checked>
      Search on Google
    </label>

    <label>
      <input type="checkbox" name="choice" value="recent" checked>
      Recent results (within last year)
    </label>
  </fieldset>
</form>
```
The boolean `checked` attribute marks a checkbox as selected when supplied in the input tag. 

In the above example, we've selected the 2nd and 3rd elements.

You can select checked elements in CSS with the `:checked` pseudo-class, which lets you change the appearance of checked radio buttons and checkboxes. 

Note that this pseudo-class doesn't look for the actual checked attribute; instead, it selects based on the current state of the checkbox.


#

### `type="radio"`
  - allows user to select zero or one option from list.
  - use the `value` attribute to define the value submitted by the item. 
  - use `checked` attribute to mark default radio button
    - if no default button, use the `required` attribute on all of the buttons in a group to enforce selecting a button. 
  - use the `name` attribute to name a set of related radio buttons. 

  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        <input type="radio" name="color" value="red">
        Red
      </label>

      <label>
        <input type="radio" name="color" value="green" checked>
        Green
      </label>

      <label>
        <input type="radio" name="color" value="blue">
        Blue
      </label>
    </fieldset>
  </form>
  ```
  *radio buttons work well for short lists (5-8 items)*
  
  *use `select` list control when have more than a handful of options to choose from*

#

### `type="submit"`
  - creates a button user can click to submit content of form to the server.
  - `action` attribute on the `form` tag typically provides URL of server, but can override with `formaction` attribute.

  ```html
  <form action="#" method="post">
    <fieldset>
      <input type="submit" value="Save">
    </fieldset>
  </form>
  ```

#

### `type="reset"`
  - creates a button to reset content of a form to default values. 
  - does NOT send request to server. 

  ```html
  <form action="#" method="post">
    <fieldset>
      <input type="reset" value="Clear Form">
    </fieldset>
  </form>
  ```
  
  #
  #