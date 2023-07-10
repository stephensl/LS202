# Padding and Margins

## What is the difference?

Both padding and margins surround elements with whitespace. 
  - padding lies inside the border
  - margins lie outside the border.
  - if no border defined, defaults to `0` but still present, though invisible. 
  - margins typically transparent
  - padding typically opaque

*Padding is part of the visible and clickable bounds of an element, while margin is spacing between adjacent elements*

  - if you click on the content area or anywhere in the padding or border, the browser will process the click.
  - if you click on the margin, nothing happens.

Example: 
```html
<!--
Don't worry about contents of this <script> tag: it is JavaScript. We need it to
implement the color toggle, but you don't need to understand it right now.
You'll learn all about JavaScript in future courses.
-->
<script>
  var article = {
    toggleColor: function() {
      document.querySelector('article').classList.toggle('toggled');
    }
  };
</script>

<!--
The onclick attribute on the article tag causes the browser to run the
JavaScript above when the user clicks the <article> element. Don't bother
memorizing this right now.
-->
<section>
  <article onclick="article.toggleColor();">
    Click here
  </article>
</section>
```


```css
section {
  background-color: #ffc0c0;
  border: 1px solid black;
  height: 300px;
  margin: 0;
  padding: 0;
  width: 300px;
}

article {
  background-color: #c0c0ff;
  border: 30px solid blue;
  box-sizing: border-box;
  cursor: pointer;
  height: 200px;
  margin: 40px;
  padding: 50px;
  width: 200px;
}

/* The JavaScript code above turns this class on and off in the <article> */
.toggled {
  background-color: #c0ffc0;
  border: 30px solid green;
}
```


### Margins, Padding and Backgrounds
- Background of an element appears in the padding area.
- Background of a container shows through the contained element's margins. 

### Top and Bottom Margins and Padding on Inline Elements
- Browser does not use top and bottom margins and padding for `inline` elements for spacing. 
- No matter how big the top and bottom margins are on an `inline` element, they do not affect the placement of the element's content, nor the content surrounding it. 

### Margin Collapse
- Top and bottom margins collapse between `block` elements. 
- If you position two adjacent `block`s, one above the other, the margin between them isn't the sum of the bottom margin of the first and the top margin of the second. 
- The margin collapses to teh larger of the two margins in question. 

Example: 
```html
<p>This is the first sentence</p>
<p>This is the second sentence</p>
```

```css
p {
  margin-bottom: 15px;
  margin-top: 32px;
}
```
*The spacing between the two paragraphs will be 32 pixels*

**Margin collapse occurs with top/bottom margins, but *NOT* left/right margins. Padding does not collapse.**

#

### Should I use Padding or Margins?
- Use margins for spacing between elements
- Use padding to affect the visible or clickable area of an element. 
- Within a container:
  - use padding for horizontal separation between its edges and content.
  - use margins for the vertical distance. 

**Padding controls the space between an element and its content, while margin controls the space between different elements**


Another approach is to use margins everywhere, except when you need padding. 

Padding is often needed when: 
  - You want ot change the height or width of a border. 
  - You want to adjust how much background is visible around an element. 
  - You want to alter the amount of clickable area. 
  - You want to avoid margin collapse. 
  - You want some horizontal spacing to the left or right of an `inline` element. 
  - Separate left/right sides of a container from its content. Use margins for vertical gaps. 
