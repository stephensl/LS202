# Everything is a box

## How browser renders HTML pages
  - displays "words" horizontally until it encounters a "word" that does not fit and starts a new line. 
    - "words" in this case means elements (may be text, image, media, containers, etc.)
  - browser processes one element at a time, and determines how much horizontal and vertical space is needed (rectangle or box) it needs to draw them. 
    - uses browser defaults and CSS to calculate required dimensions
    - if enough space remaining on current line, element is placed there, if not, new line.

### Summary of rendering
  - Every element requires a box-shaped segment of the page. 
  - Every character of text content also needs a boxed portion of the page.
  - Browser calculates dimensions of that box by using the browser defaults and CSS. 

**Box Model used to describe how the browser calculates the box size for any given element.**


## Widths and Heights
  - `inline-block` elements laid out side by side up to the page width. If one does not fit, starts new line.

## Box Properties
  - width and height
    - define how much vertical and horizontal space is needed for the content area of the box.
      - may or may not include padding and borders
      - usually automatically determined by browser. 
  - padding
    - area surrounding teh content area of the box
    - separates content from its border
    - typically opaque and hides anything that it overlays
  - border
    - boundary surrounding the padding 
  - margin
    - transparent area outside the border
    - provides separation between elements
  - display 
    - determines how browser lays out an element relative to its neighbors
![Example](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/chrome_box_model.png)
  - Above picture shows: 
    - element with content area 928px/168px
    - 10 px top/bottom padding, 20px left/right padding
    - 1px border 
    - 28px bottom margin
      - left, right, top margins are 0.
    
  