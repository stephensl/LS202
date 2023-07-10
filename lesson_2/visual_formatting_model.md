# Visual Formatting Model 

`display` has more than two dozen values, but most CSS uses the values `block`, `inline`, and `inline-block`. 

## Block Elements
  - Block elements appear on almost all web pages: 
    - headings
    - paragraphs
    - sections
    - tables 
    - forms
    - lists
    - etc
  - most block elements group one or more elements, some of which may be `block`s themselves, into areas of the page. 
    - `header` elements group together elements into a page header. 
    - `block` elements often called *containers*
    - master container (outermost) is the `body`
      - every other element belongs to a container

  **The term "parent" may refer to a container, and "child" to the element contained within a container**

  ### Characteristics of `block` elements
  - occupies all horizontal space available within its container with nothing to the left or right of the block. 
    - if page contains 3 `block` elements directly inside the `body` element and nothing else...
      - all three elements will display one above the other like a stack of blocks.
        - makes `block` elements predictably easy to use

  - `block` elements use box properties (`width`, `height`, `padding`, `border`, `margin`) to determine the size of the element. 
    - browser reserves a box of the right size on the page where it draws the content. 
      - Example: element that is 928px wide, 168px high, with 20px of left/right padding, 10px of top/bottom padding.
        - overall dimensions will be 970 x 218 px

  - What if the `block` element does not take up the whole width of the available space?
    - Example: 
      - 500px wide `blockquote` in 900px wide `section`
        - `blockquote` element uses 500px, and remaining 400px of the `section` left empty. 
  
  ### Common `block` elements
  - Most elements are `block` elements by default: 
    - `section`
    - `article`
    - `aside`
    - `header`
    - `footer`
    - `p`
    - `h1`- `h6`
    - `blockquote`
    - `ul`, `ol`, `dl`
    - `figure`, `figcaption`
    - `form`, `fieldset`

  *You can convert any element to a `block` element with the `display: block` CSS property.*
  - links `a` and images `img` are often rendered as `block` elements. 

#
#

## Inline Elements

`inline` elements provide some semantic meaning to the content, and browsers use this to alter the way they display small sections of text. 
  - example: use boldface text for definitions, use the `b` element, which is an `inline` element by default.

### Common `inline` elements:
  - `span`
  - `b`, `i`, `u`, `strong`, `em`
  - `a`
  - `sub`, `sup`
  - `img`

### `inline` vs `block` dimension properties
- left/right margins and padding same as `block` elements
- other box model properties handled differently.
  - ignore `width` and `height` properties (`img` is exception) but use values computed from the element content. 
  - ignore top and bottom margins
  - Do not ignore borders
  - Do not ignore top/bottom padding

**You can convert any element to an `inline` element with the `display: inline` CSS property.**
  - most common reason for doing so is to override a prior declaration. 


### Borders, Padding, Margins, and Inline Elements

Example: 

```html
<p>
  Deserunt ad eu dolor in nostrud eu. Aliqua ad veniam magna et nostrud. Non ea
  sunt. <em>Magna aliqua nostrud et laboris fugiat.</em> Ea nostrud non laboris.
  Quis sunt dolore esse pariatur velit minim cillum ipsum.
</p>
```

```css
p {
  background-color: #d4f0f8;
  border: 1px solid #2db7e1;
  box-sizing: border-box;
  font-size: 1.5rem;
  padding: 0.5em;
  width: 780px;
}

em {
  background-color: rgba(255, 255, 0, .5);
  border: 30px solid rgba(255, 0, 64, .5);
  margin: 40px;
  padding: 30px;
}
```

*Left/right factors affect the flow, whereas top/bottom do not.*

#
#

## Inline-Block Elements

*Note: `inline-block` visual display model is a legacy model. New model is called `inline flow-root`, but `inline-block` heavily used still, especially in existing pages*

#

`inline-block` elements are mixture of `block` and `inline` elements.
- They act like `block` elements except that `inline-block` elements do not take up an entire row when the `width` property is less than the available width. 
- Instead, they flow the same way that text and `inline` elements flow from one line to the next. 
  - This allows for placement of `inline-block` elements side by side with other `inline` or `inline-block` elements. 

- `inline-block` elements observe the `width` and `height` properties. 
  - padding, borders, and margin work the same as `block` elements. 


### Three available alignments in browser:
  - Browsers perform vertical alignment for adjacent `inline-block` elements as well as ordinary `inline` elements. 

    - vertically align
      - top
      - middle
      - bottom

*You can convert any element to `inline-block` with the `display: inline-block` CSS property.*
  - useful for arranging contents of a list horizontally instead of vertically.
  - horizontal navigation bars often use list elements defined as `inline-block`.

# 
#

## Nesting Elements and Visual Display Model

HTML allows nesting of elements inside other elements with exceptions: 
  - cannot nest `block` and `inline-block` elements within `inline` elements. 
 