# Select and Textarea 

## `textarea` element
  - allows user to input multiple lines of text
  - retains carriage returns, newlines, whitespace chars to format text into lines and paragraphs
  - does not use `value` attribute to provide value for the element. 

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Comment
      <textarea name="tweet">Content of text</textarea>
    </label>
  </fieldset>
</form>
```

*Since textarea preserves whitespace, its common practice to code the open and close tags on the same line unless the initial text content contains newlines.*

### Rows and Columns
  - `textarea` uses `rows` and `cols` attributes to control height and width of text box. 
    - `rows` is height in lines
      - not max, but number of visible lines
      - enables vertical scrolling when content exceeds rows count
    - `cols` is width in characters
    - CSS will override with `height` and `width`

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Comment
      <textarea name="tweet" rows="5" cols="40">I got 20% off my first purchase at joesburgers.com! You can too!</textarea>
    </label>
  </fieldset>
</form>
```

#

## `select` element
  - creates drop down list of options
  - user can select zero or more options
  - two possible child elements
    - `option`
    - `optgroup`
  
  `select` uses `name` attribute like other form elements, but uses `option` elements within it to describe the values shown to user and sent to server (may be different).

  ### `option` element
  - defines one of the choices a user can make in `select` tag.
  - `select` element useless without `option` elements
  - each `option` is possible value for the select, and uses the `value` attribute as value sent to server with teh `select` element's name.
    - if `option` does not have `value` attribute, browser uses text contained by `option` element instead.

  
  `select` elements often have placeholder `option` saying something like `Choose One` and has a `value` of empty string, as well as a `disabled` and `selected` attribute.

  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        Colors
        <select name="color">
          <option value="" disabled selected>Choose one</option>
          <option value="#f00">Red</option>
          <option value="#0f0">Green</option>
          <option value="#00f">Blue</option>
        </select>
      </label>
    </fieldset>
    </form>
  ```

  *By default, select lets the user choose precisely one option or leave the option unselected if it contains a disabled selected option as shown above*

  - If you add the multiple attribute, the user can select more than one option.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Choose Your Favorite Movies
      <select name="favorites" multiple size="4">
        <option value="" disabled selected>Select One or More</option>
        <option>2001: A Space Odyssey</option>
        <option>Arrival</option>
        <option>Close Encounters of the Third Kind</option>
        <option>District 9</option>
        <option>Guardians of the Galaxy</option>
        <option>Interstellar</option>
        <option>Serenity</option>
        <option>Silent Running</option>
      </select>
    </label>
  </fieldset>
</form>
```

#
