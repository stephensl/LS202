# Forms Overview

HTML forms allow you to gather information from users. 

Forms are the point where front-end and back-end concerns converge. 

Forms DO: 
- displays information to the user
- solicits updates
- performs some optional rudimentary validation
- sends form data to the server


Forms DO NOT: 
- update information on the server
- anything else


#

## The `form` Tag

The `form` tag is the parent for all form-related tags. 
  - tells the browser where and how to send the data. 
  - most important attributes are `action` and `method`

A form should contain: 
  - at least one `input`, `text-area`, or `select` tag (otherwise form is useless)
    - these elements collectively referred to as **controls**, **widgets**, or **input**. 

#

### `method` attribute
- tells browser whether it should use the HTTP GET or HTTP POST method when sending data to the server. 
  - these are the only two methods that HTML supports. 
  - must use JavaScript or a backend application to use other methods. 


### `action` and `formaction` attributes
  - `action` provides URL to which browser sends requests
  - individual action items (`button` and `input type="submit` elements) can override the forms `action` value by using the `formaction` attribute

#

### `fieldset` tag
- optional tag
- groups together form content as a set of related data
- most browsers draw border around the content (though commonly removed with CSS)
- provides useful semantic data to the browser, and can be referenced in CSS for layout/styling

- Forms may have multiple `fieldset` tags:
```html
<form action="/login" method="post">
  <fieldset>
    <input type="text" name="username">
    <input type="password" name="password">
  </fieldset>
  
  <fieldset>
    <input type="submit" value="save">
    <input type="submit" value="Forgot Password" formaction="/forgot">
  </fieldset>
</form>
```

#

### `input` tag

The `input` tag describes a control or widget (mechanism that lets user supply info or request to the application on the server).

Each `input` requires:
  - `type` attribute
  - indicates type of widget required
  - Example
    - `type="text"`
      - provides space for user to enter some text
    - `type="submit"`
      - provides a button that submits the form to the server.

Most `input` controls require a `name` attribute to specify the name of each item.
  - browser uses names to identify each data item in the form
  - back-end application looks for that name to find the appropriate value.

```html
<input type="text" name="city">
<input type="password" name ="password">
<input type="submit" value="Save">
```
*`input` is a self-closing tag*

#

### `label` tag

Provides way to associate some identifying text with an input field. 

For example, to associate the label `Phone` with the field named `phone_number`:

```html
<label for="phone">Phone</label>
<input type="text" id="phone" name="phone_number">
```

- Browser uses the `for` attribute in the `label` tag and the `id` attribute in the `input` tag to associate the two items. 
  - allows user to click on the label and make cursor jump to the desired field. 

#### `label` tags as containers
```html
<label>
  Phone
  <input type="text" name="phone">
</label>
```
Container syntax eliminates need for `for` and `id` attributes, but may make styling more difficult. 

#


## Form Example HTML

```html
<form action="#" method="post">
  <fieldset>
    <h1>Log In</h1>
    <label for="username">Username</label>
    <input type="text" name="username" id="username">

    <label for="password">Password</label>
    <input type="password" name="password" id="password">

    <input type="submit" value="Log In">
    <input type="submit" value="Delete Account"
            formaction="/account/delete">   
    <input type="submit" value="Forgot Password"
            formaction="/account/password">
    <input type="reset" value="Reset">
  </fieldset>
</form>
```

This will display all the inputs together on one line. 

We can use additional `fieldset` tags to arrange them more attractively. 

```html
<form action="#" method="post">
  <fieldset>
    <h1>Log In</h1>
  
  <fieldset>
    <label for="username">Username</label>
    <input type="text" name="username" id="username">
  </fieldset>

  <fieldset>
    <label for="password">Password</label>
    <input type="password" name="password" id="password">
  </fieldset>

  <fieldset>
    <input type="submit" value="Log In">
    <input type="submit" value="Delete Account"
            formaction="/account/delete">   
    <input type="submit" value="Forgot Password"
            formaction="/account/password">
    <input type="reset" value="Reset">
  </fieldset>
</form>
```

```css
fieldset {
  border: none;
}
```