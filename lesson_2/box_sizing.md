# Box Sizing

Article: https://css-tricks.com/box-sizing/
  - quirks box model
    - width = actual visible/rendered width of an element's box
    - height = actual visible/rendered height of an element's box
    - border and padding values moved inside the element's box, cutting the width/height of the box rather than expanding it. 

  - box-sizing property
    - introduced in CSS3
    - has three possible values:
      - content-box
      - border-box
      - padding-box (deprecated: do not use!)

  *current browsers use the original width or height + padding + border = actual width or height*

  *quirks model- an element's specified width and height are not affected by padding and borders*
  - May use this model by setting `box-sizing: border box` on all elements. 


## Important Points
  - `content-box` is default setting for `box-sizing` property for all elements in modern browsers. 
    - `width` and `height` properties specify the size of the actual content area. 
    - need to add padding and borders to get the size of visible box
  
  - `border-box` setting causes browser to interpret `width` and `height` properties as total width and height of the box, excluding margins. 

  - `border-box` setting is "best" since it simplifies the math developer must do.
    - example: box with width of 50% and padding of 12px
      - `border-box` ensures that it's precisely 50% of the container width, not 50% + 24px. 

  **To use `border-box` everywhere, you can add to your CSS:**
  ```css
  html {
    box-sizing: border-box;
  }

  *, *::before, *::after {
    box-sizing: inherit;
  }
  ```