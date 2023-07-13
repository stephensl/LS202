# Input Attributes

## `value` attribute
  - most controls can use `value` attribute
  - meaning varies with `type`

  ### `value` in text based types:
  - `text`, `email`, `number`, etc.
  - `value` assigns default value for control
    - if do not provide default value, browser uses empty string

  ```html
  <form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" value="503-555-1212">
    </label>
  </fieldset>
</form>
  ```

*should use `value` when already have a value, either loaded from the database or provided by user previously during the session*

#

  ###  `value` in `checkbox` or `radio` types
  - sets the value that the form submits for indicated checkbox or radio group element.

  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        <input type="radio" name="color" value="red">
        Red
      </label>
      <br>

      <label>
        <input type="radio" name="color" value="blue" checked>
        Blue
      </label>
      <br>

      <label>
        <input type="radio" name="color" value="green">
        Green
      </label>
    </fieldset>
  </form>
  ```
  *Technically, radio input types don't require the value attribute. If you omit the value attribute, the browser will send NAME=on to the server, where NAME is the value of the name property.* 

  **Recommended to always yse `value` attribute and use `name` to group related radio buttons together.**

#

  ### `value` in `submit`, `reset`, and `button` types
  - Used for label that appears on the button.

  ```html
  <form action="#" method="post">
    <fieldset>
      <input type="submit" value="Save">
    </fieldset>
  </form>
  ```
  *Note that type="button" is out of favor; consider using the `<button>` element instead.* 

#
#
#

## `size` and `maxlength` attributes
  - apply ot most text-based input types

  ### `size` attribute
  - allows control over size of `input` element in characters
  - can set with CSS width, but does not support character measurements.

  ### `maxlength` attribute
  - limits maximum length of input values
  - can be more or less than `size` value

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" size="10" maxlength="16">
    </label>
    <br>
    <label>
      Cell Phone
      <input type="tel" name="cell-phone" size="20" maxlength="40">
    </label>
  </fieldset>
</form>
```
*CSS width overrides `size` attribute.*

#

## `placeholder` attribute
  - allows display of text when a field is empty to help describe the expected input.
  - applies to most text-based input types
  - most display placeholders in greyed-out format
  - erased as soon as user starts typing

  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        Phone
        <input type="tel" name="phone" placeholder="###-###-####">
      </label>
    </fieldset>
  </form>
  ```
*do NOT use as substitute for labels as will break screen readers* 
- if forced to use placeholders, use labels too and hide them using CSS. 
  - most screen readers can read hidden text.

#

## `disabled` attribute
  - allows disabling of `input` elements
  - browser renders disabled elements, but user cannot interact with them. 
  - often displayed as greyed-out
  - turns on `:disabled` pseudo-class
    - non-disabled elements set the `:enabled` pseudo-class
  
  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        Email
        <input type="email" name="email" value="xyz@example.com" disabled>
      </label>
      <br>
      <input type="submit" value="Save" disabled>
    </fieldset>
  </form>
  ```
#

## `required` attribute
  - marks an `input` as required
  - browser will not allow form submission until user completes required fields
  - turns on `:required` pseudo-class.

  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        Home Phone
        <input type="text" name="home_phone" required>
      </label>
      <br>
      <label>
        Business Phone
        <input type="text" name="business_phone">
      </label>
      <br>
      <input type="submit" value="Save">
    </fieldset>
  </form>
  ```

```css
input:required {
  background-color: yellow;
}
```

#

## `autocomplete` attribute
  - can use on most `input` text-box elements
  - prevents browser from storing data for later resuse by the browser's `autocomplete` features.
  - use values `on` or `off` to explicitly turn is on or off for a given field. 

  ```html
  <input type="tel" value="123-456-7890" name="phone" autocomplete="off">
  ```

  *does not affect `password` input type, obviously*

  #

## `autocapitalize` attribute
  *not part of HTML standard, but provided by some mobile browsers*

  - some browsers recognize to turn on automatic capitalization of the first letter of words or sentences. 
  - browsers default to `sentences`
  - use `autocapitalize="none"` when expecting input that you do not want to capitalize.
  - may specify `autocapitalize="words"` or `autocapitalize="characters"`.

  ```html
  <input type="text" name="full-name" autocapitalize="words">
  ```
#

## `autocorrect` attribute
 *not part of HTML standard, but provided by some mobile browsers*
  - some browsers support autocorrect that turns spelling correction on and off
  - should disable with names, addresses, and elsewhere where applicable. 

  ```html
  <input type="text" name="full-name" autocorrect="off">
  ```
#
#