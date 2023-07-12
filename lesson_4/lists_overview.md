# Lists Overview

## Unordered Lists
- No visual numbering or naming system for the items. 
- browser displays a bullet 
  - default render is vertical 
- HTML uses `<ul>` and `<li>` tags to construct unordered lists. 
```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  ...
```

#

## Ordered Lists
- Sequence that is a visual component of the list
- Default most browsers render a vertical list of numbered items
- HTML uses `<ol>` and `<li>` to construct ordered lists. 
```html
<ol>
  <li>Item 1</li>
  <li>Item 2</li>
  ...
```

#

## Description Lists
- Previously called definition lists
- Contain a list of terms and definitions
- Each item includes one or more terms and one or more definitions.
- Html uses `<dl>`, `<dt>`, and `<dd>` tags to construct description lists. 
```html
<dl>
  <dt>Unordered</dt> <!-- description term -->
  <dd>A simple list with bullets</dd> <!-- description -->
  <dd>A plain list with no bullets or sequence nums</dd>
<dl>
```

#

## Nested Lists
Can nest any list within another list regardless of type.

#

## Navigation Menus
Unordered lists to construct navigation menus that may be vertical or horizontal.

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Projects</a></li>
  </ul>
</nav>
```

```css
nav ul {
  background-color: powderblue;
  list-style-type: none;
  padding-left: 0;
  width: 200px;
}

nav li {
  font-size: 1.25rem;
}

nav a {
  box-sizing: border-box;
  color: blue;
  display: inline-block;
  line-height: 2.5;
  padding: 0 10px;
  text-decoration: none;
  width: 100%;
}

nav a:hover,
nav a:focus {
  background-color: blue;
  color: white;
}
```

If we wanted the list to be horizontal...
```css
nav ul {
  font-size: 0;
  width: 100%;
}

nav li {
  display: inline-block;
  font-size: 1.25rem;
  text-align: center;
  width: 25%;
}
```

Our CSS removes list bullets with the `list-style-type` property, and uses `:hover` and `:focus` pseudo-classes to draw a highlight bar on the menu at appropriate times. 

**Note on pseudo-classes**
- CSS provides more than 30 pseudo-classes that may be used as selectors.
- `:hover`
  - determines whether the mouse is above one of our links
  - applies style to an element when user's mouse is over that element
    - provides visual feedback to user that the element is interactive or to highlight the element. 
- `:focus`
  - determine if the link has the current keyboard focus.
  - applies style to an element when it has focus
    - focus means that the user clicks, taps, navigates to it using the keyboard
  - highlights which element will receive keyboard input. 
    - ex: border around text input field indicating that user can start typing into that field. 