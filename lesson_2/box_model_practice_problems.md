# Practice Problems: Box Model

1. Given the code below, what is the minimum width and height (in pixels) that the div needs to entirely contain the img element (including its margins)?

```html
<div>
  <img src="#" alt="test">
</div>
```

```css
div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

img {
  border: 4px solid red; /* all four sides */
  box-sizing: content-box;
  display: inline-block;
  height: 300px;
  margin: 20px 19px 10px 11px; /*top, right, bottom, left*/
  padding: 10px 20px; /* top/bottom, left/right */
  width: 500px;
}
```

**Answer**

Since the `box-sizing` property is set to `content-box`, we need to add the border, margin, and padding values to the height and width values of the element to determine the minimum box size. 

*Height*

img element:
- Height: 300px + 
- Border: top (4px), bottom (4px) +
- Margin: top (20px), bottom (10px) +
- Padding: top (10px), bottom (10px) =

300 + 4 + 4 + 20 + 10 + 10 + 10 = 358px 

358px + `div` element `border` top(1px), bottom(1px) =

Total Minimum Height = 360px


*Width*

img element:
- Width: 500px + 
- Border: right (4px), left (4px) +
- Margin: right (19px), left (11px) + 
- Padding: right (20px), left (20px)

- `+` div element border: right (1px), left (1px) = 

500 + 4 + 4 + 19 + 11 + 20 + 20 + 1 + 1 = 

Total Minimum Width = 580 px

*Final Answer*: 580px x 360px 

*While we don't typically count margins in determining an element's height and width, we need to include them here when calculating how much space we need in the div.*

#
#

2. Given the code below, what is the minimum width and height (in pixels) that the div needs to entirely contain the section element (including its margins)? 

How does this differ from the result of the previous practice problem?

```html
<div>
  <section>content</section>
</div>
```

```css
div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

section {
  border: 4px solid red;
  box-sizing: content-box;
  display: block;
  height: 300px;
  margin: 20px 19px 10px 11px;
  padding: 10px 20px;
  width: 500px;
}
```

- Same as previous: 580px x 360px

- Main difference is since the `section` element is a `block` element, it will be on a line by itself within the `div` element regardless of width. In the first problem the `img` element was an `inline-block` element, which would allow for adjacent elements on the same line if space permitted. 

#
#

3. Given the code below, what is the minimum width and height (in pixels) that the div needs to entirely contain the em element (including its margins)?

```html
<div>
  <em>content</em>
</div>
```

```css
div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

em {
  border: 4px solid red;
  box-sizing: content-box;
  display: inline;
  height: 300px;
  margin: 20px 19px 10px 11px;
  padding: 10px 20px;
  width: 500px;
}
```

Since `em` is `inline` element, browser ignores width, height, top, and bottom margins specified in CSS. 

If assume `em` requires 50px width then: 130 px horizontally
  - 50px assumed width
  - 8px for left/right borders
  - 40 px left/right padding
  - 11 px left margin
  - 19px right margin
  - 2 px left/right borders of `div`

If assume `em` requires 20px height then: 50 px vertically
  - 20px assumed height
  - 8 px top/bottom borders
  - 20px top/bottom padding
  - 0px top/bottom margins (ignored bc inline)
  - 2px left/right border of `div`

  Total = 130px x 50px

  *note: top and bottom padding and borders may intersect with content above and below `em` element.*

#
#

4. Given the code below, what is the minimum width and height (in pixels) that the div needs to be to entirely contain the article element (including its margins)?


```html
<div>
  <article>content</article>
<div>
```

```css
div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: border-box;
  display: inline-block;
  margin: 0;
  padding: 0;
}

article {
  border: 4px solid red;
  box-sizing: border-box;
  display: inline-block;
  height: 300px;
  margin: 20px 19px 10px 11px;
  padding: 10px 20px;
  width: 500px;
}
```

Since `box-sizing` property set to `border-box` we ignore the padding and border of the `article` element to calculate actual dimensions. 

`div` element needs:
  - 500px width
  - 0px left/right borders
  - 0px left/right padding
  - 11px left margin
  - 19px right margin
  - 2 px left/right borders of `div`

`div` element needs:
  - 300 px height
  - 0px for top/bottom borders
  - 0px top and bottom padding
  - 20px top margin
  - 10px bottom margin
  - 2px top and bottom margin of `div`


Total needed: 532px x 332px


#
#

5. Given the code below: 

```html
<div>
  <tag1>content</tag1><tag2>content</tag2>
</div>
```

```css
div {
  background-color: lightgray;
  border: 1px solid black;
  box-sizing: content-box;
  display: inline-block;
  margin: 0;
  padding: 0;
  width: 720px;
}

tag1, tag2 {
  box-sizing: border-box;
  height: 240px;
  margin: 0;
  padding: 0;
  width: 360px;
}

tag1 {
  background-color: yellow;
}

tag2 {
  background-color: lime;
}
```

Which of the following element pairs will display side by side in the `<div>`? 

Select all that apply:


- Both elements are block elements.
- Both elements are inline elements.
- Both elements are inline-block elements.
- One element is a block element, and one is an inline element.
- One element is a block element, and one is an inline-block element.
- One element is an inline element, and one is an inline-block element.


You may assume that any `inline` element has a content width of no more than 360 pixels. 

Remember, the `width` property doesn't affect inline elements, so this "content width" is the actual width of the content area as determined by your browser.


Notes: 

- `div` has `box-sizing` property value of `content-box` meaning that we must add border, padding to width. 

- `div` is `inline-block` element- meaning it can be adjacent to other `inline` or `inline-block` elements.

- size of `div` element will be: 
  - width: 720px + 1px left border + 1px right border = 722px
- both `tag1` and `tag2` will have width of 360px
- both will have height of 240px

ANSWER: 

From the above options:

- FALSE: both elements are `block` elements
  - this is false because block elements are displayed on their own line.

- True: both elements are inline elements
  - true because, the total width of `div` element is 722px, so two 360px wide elements can fit side by side.

- True: both elements are `inline-block` elements
  - true because inline block elements can be rendered adjacent to other inline block elements if space permits. 

- False: one block, and one inline
  - block elements take up entire line

- False: one block, one inline-block
  - block elements take up entire line

- True: one `inline` and one `inline-block`
  - can be rendered adjacently if space permits. 


#
#


6. Will the following code display the two article boxes side by side?

If not, why not?

How would you fix it so that it places the boxes side by side?


```html
<section>
  <article>content</article><article>more content</article>
</section>
```

```css
section {
  background-color: yellow;
  border: 1px solid red;
  box-sizing: content-box;
  display: inline-block;
  height: 400px;
  margin: 0;
  padding: 20px;
  width: 900px;
}

article {
  background-color: lime;
  border: 1px solid blue;
  height: 100%;
  margin: 0;
  padding: 10px;
  width: 50%;
}
```

*Answer and Notes*

`article` elements are block-level elements by default, meaning they will be displayed on their own line within the parent element. 

In order to display them side by side, we need to declare in the css the `display` property with a value of `inline-block` or `inline`.

Also, the total width of each article is 50% of the parent element width + 22px for padding and border. This is wider than the parent element, and would not fit side by side. 

To fix this: 

```css
article {
  background-color: lime;
  border: 1px solid blue;
  box-sizing: border-box;
  display: inline-block;
  height: 100%;
  margin: 0;
  padding: 10px;
  width: 50%;
}
```

#
#

7. Challenge: Given our solution to the previous question, what will happen if we put the article tags on separate lines?

```html
<section>
  <article>content</article>
  <article>more content</article>
</section>
```

*Answer*

Putting the `article` elements on separate lines in the HTML, browser ses the whitespace (newline and several spaces in this case). The browser collapses the whitespace into a single space character and uses the result as content between teh elements. 

The two articles take up 900px total (450px each) + a dew more pixels to account for space character.

The section width is 900px total, and the two articles plus the space would exceed this width. 



