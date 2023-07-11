# Dimensions 

Some CSS properties require lengths as property values to provide the side of some detail on the page. 

These properties such as `12px`, `3rem`, or `50%` are *measurements* or *dimensions*. 

`px`, `rem`, `%`, etc. are *measurement units* or *units*. 

#

## Absolute vs Relative Units


### Absolute Units
- pixel is most significant

**Physical vs Reference Pixels**
- pixel on desktop and pixel on cell phone are not the same size. 
- depends also on resolution of screen

CSS distinguishes between physical pixels (device/display pixel) and the CSS reference pixel (CSS pixel/reference pixel). 

- Reference pixel 
  - size of pixel on a display that has 96 pixels per inch. 
  - defines reference pixel based on the angular diameter of a CSS pixel as viewed from the typical viewing distance (TVD) for the display. 
    - TVD phone approx 14inches
    - TVD of 27in desktop approx 33inches

- Other absolute units
  - inches, mm (not used often) 

#

### Relative Units

#### Ems and Rems 
- proportional to the calculated and root font sizes respectively. 
  - calculated font size
    - height of current font in pixels
  - root font size
    - height of the base font for the document
      - font size designated for `html` element
- Example: 
  - calculated font size: 20px
  - root font size: 16px
  - `1.5em` == `30px` (20 * 1.5)
  - `1.5rem` == `24px` (16 * 1.5)

- In most cases, use pixels to specify the root font size. 
- Typically easier to work with `rem`s as they are consistent based on the root font size, whereas `em`s compound. 
- Some browsers don't recognize `rem` and should use fallback unit.
```css
p {
  font-size: 20px; font-size: 1.25rem;
}
```
This tells browser to use `1.25rem`, and falls back to `20px` if browser does not recognize it. 

**Most browsers use `16px` as default, therefore `1.25rem` would equate to `20px`.**

#

#### Percentages
- Not technically a length value
- Used to define dimensions as a portion of the container's width or height.
- Example: 
  - `block` or `inline-block` element in a container and set width to `50%`, element's width is 50% of width of container. 

***`width` and `height` have no effect on `inline` elements.***

#

#### Auto
- Not a length value
- Used to let browser determine width or height for you. 
- Specific role depends on where used. 
  - When used as `width` or `height` value 
    - tells browser to try to fit entire element (including margins) in its container.
  - as left or right `margin` value on block element
    - tells browser to push the element all the way right or left inside the container
    - center block element by setting both left and right margins to `auto`
  - as top or bottom `margin` value
    - `auto` equivalent to `0`
  - padding does not accept `auto` values

#

## When to use Different Units
- Use absolute units sparingly, and stick with pixels
  - pixels useful for 
    - root font size
    - image widths and heights
    - top and bottom margins and padding
    - width or height of fixed width/fixed height containers such as navigation sidebars
    - border widths

- Use Relative units liberally
  - use rems for fonts, possibly with fallback to ems or pixels.
  - if using ems, try to avoid compounding font sizes
  - use rems, ems, or pixels for left and right margins and padding
  - use % for measurements proportional to the container element's width or height
    - percentages work best for container dimensions
    - useful for growing or shrinking certain areas of the page as the width of the browser window changes
  - use `auto` with `width` and `height` to let browser calculate appropriate value
  - use `auto` with left or right margins to left, center, or right justify a block element within its container. 
