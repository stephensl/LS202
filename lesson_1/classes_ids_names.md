# Classes, IDs, and Names

## HTML provides 3 ways to identify certain elements

- Classes
- IDs
- Names 

Any element can use a `class` or `id` attribute, and a variety of elements can use the `name` attribute. 


### `class` Attribute 
- Identifies set of page elements that you wish to style consistently. 
- Used to assign a class or classes to an element. 
- Any number of elements may belong to the same class. 
- Any element can belong to one or more classes.
  - List names separated by spaces in the `class` attribute.
- Use semantic names to provide meaning.
- Use CSS class selectors `.classname` to select elements by class. 
- Class selectors have lower CSS specificity than ID selectors (ID selectors override class selector) 
- Class selectors have higher specificity than tag name selectors. 


### IDs
- applies a unique identification string to a single element. 
- not shared within page
```html
<h1 id="headline">Headline</h1>
```
```css
#headline {
  color: red;
  font-size: 48px;
}
```

- Use CSS ID selectors (`#idname`) to select elements by id. 
- Higher CSS specificity than class selectors. 


### Names
- Ties form elements to data on the server. 
- Used to assign a name to a form data element that the server can use to obtain the value.
- Not all tags accept the `name` attribute. 
- Applies to input control in forms. 
- Each name on a form should be unique to the form except for radio buttons and checkboxes that belong to single group. 
- Descriptive `name` values, not semantic. `name="last-name"` instead of `name="input-field"`.
- Avoid using `name` attribute to select CSS elements. 
