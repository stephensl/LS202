# Practice Problems: Dimensions and Spacing

#

1. Use CSS to set a fixed width on the image of 800 pixels, and center it in the window horizontally.

Answer: 

```css
img {
    display: block;
    width: 800px;
    margin: 0 auto; /* 0: top/bottom, auto: left/right */
  }
```

#

2. Using the code from the previous problem, change the width property for img to 100%, and set the max-width property to 800px. The image should expand to fit any container width up to 800 pixels. Resize your browser width and watch how that affects the photograph.

Answer: 

```css
img {
    display: block;
    max-width: 800px;
    width: 100%;
    margin: 0 auto;
  }
```

#

3. Using the code from the previous problem, set a fixed height on the image of 533 pixels. Resize the browser window and watch how the image dimensions change.

Answer: 

```css
img {
  display: block;
  max-width: 800px;
  width: 100%;
  height: 533px;
  margin: 0 auto;
}
```

#

4. As you can see, having a variable size for one dimension and fixed for the other makes for a container with strange behavior: this one stretches horizontally but remains fixed vertically. Remove the height and update the CSS to ensure the width does not get smaller than 500 pixels.

Answer: 
```css
img {
    display: block;
    min-width: 500px;
    max-width: 800px;
    width: 100%;
    margin: 0 auto;
  }
```

#

5. Create a new HTML page with two consecutive div elements. Make each a fixed width and height of 300 pixels. Set the background color on the first div to "#fcc" (red) and the second to "#ccf" (blue).

Answer: 

```html
<div class="red"></div>
<div class="blue"></div>
```

```css
div {
  width: 300px;
  height: 300px;
}

.red {
  background-color: #fcc;
}

.blue {
  background-color: #ccf;
}
```

#

6. Add a 5-pixel solid black border to the blue div. Compare the widths of the two boxes. Why is the blue box a different size?

Answer: 

```css
.blue {
  background-color: #ccf;
  border: 5px solid black;
}
```
The blue box is a bit wider to accommodate for the addition of a border. If we wanted to ensure that the boxes remained the same size, we would need to alter the box-sizing property with the value `border-box` to include the border within the set width. By default, the CSS box model uses a value of `content-box` for all elements. 

#

7. Add 20 pixels padding to all four sides of the red div. Notice the different widths again. Add a CSS property to both elements to ensure the total width for each is 300px rather than 300px and then some.

Answer: 

```css
div {
  width: 300px;
  height: 300px;
  box-sizing: border-box; /* added */
}

.red {
  background-color: #fcc;
  padding: 20px;         /* added */
}

.blue {
  background-color: #ccf;
  border: 5px solid black;
}
```


#


8. Change both boxes to place them side by side instead of stacked vertically. If necessary, increase the width of your browser window.

Answer: 

```css
div {
  box-sizing: border-box;
  display: inline-block; /* added */
  width: 300px;
  height: 300px;
}
```

#


9. Add 20px of space between the red and blue boxes.

```css
.red {
  background-color: #fcc;
  padding: 20px;
  margin-right: 20px;  /* added */
}
```

#

10. Create a new HTML file with the following CSS and HTML:

```html
<body>
  <ul>
    <li>Item 1</li><!--
    --><li>Item 2</li><!--
    --><li>Item 3</li><!--
    --><li>Item 4</li>
  </ul>
</body>
```

```css
body {
  margin: 50px;
}

ul {
  background-color: #a7ceff;
  border: 10px solid blue;
  list-style: none;
  padding: 0;
}

li {
  background-color: #ffc;
  border: 10px solid red;
  box-sizing: border-box;
  line-height: 120px;
  min-height: 120px;
  text-align: center;
}
```
Don't overlook the oddly-formatted comments between the list items above! They're a necessary part of this problem.

Add the CSS needed to list all four items side by side in one row. Each list item should use the same amount of space as the other elements, and together they should hide the blue background entirely (but not the blue border).


Answer: 

```css
li {
  background-color: #ffc;
  border: 10px solid red;
  box-sizing: border-box;
  display: inline-block;
  line-height: 120px;
  min-height: 120px;
  text-align: center;
  width: 25%;
}
```

LS Comments: To understand the comments, review the challenge exercise at the end of the practice problems for the box model. In that example, we ensured that there was no space between consecutive items by making their tags adjacent. The comments here are a variation on this theme: the browser ignores them entirely, so we end up with adjacent elements.

Annoying, right? Yes, but a necessary evil you must learn to manage. Breaking this behavior would cause other problems, so we're stuck with it for now. Try removing the comments from the above code temporarily to see for yourself how that extra whitespace makes a difference.


Article: https://css-tricks.com/fighting-the-space-between-inline-block-elements/

Fixes: 

```html
<h1>Inline-block / white-space bug</h1>
original...
<ul>
  <li>one</li>
  <li>two</li>
  <li>three</li>
</ul>

fixed by funky code formatting...
<ul>
  <li>
   one</li><li>
   two</li><li>
   three</li>
</ul>

fixed by adding html comments...
<ul>
  <li>one</li><!--
  --><li>two</li><!--
  --><li>three</li>
</ul>

fixed by CSS margin-right: -4px;  (breaks in IE6&7)...
<ul class="white-space-fix">
  <li>one</li>
  <li>two</li>
  <li>three</li>
</ul>

fixed by omitting the &lt;/li&gt;
<ul>
  <li>one
  <li>two
  <li>three
</ul>

fixed with font-size: 0 via: https://twitter.com/#!/garand/status/183253526313566208
<br><br>
<ul class="zero-size">
  <li>one</li>
  <li>two</li>
  <li>three</li>
</ul>

  <br>
flexbox
    <br>
<ul class="flexbox">
  <li>one</li>
  <li>two</li>
  <li>three</li>
  </ul>
```


#


11. Using the code from the previous problem solution, set the left and right margin on each li element to 1%, but do not let the inner boxes wrap around - they must all continue to fit on the same line with no change in the outer box's size.

Answer: 

```css
li {
  background-color: #ffc;
  border: 10px solid red;
  box-sizing: border-box;
  display: inline-block;
  line-height: 120px;
  margin: 0 1%;
  min-height: 120px;
  text-align: center;
  width: 23%;
}
```

We need to remove 2% from each element's width to account for the 1% margin. (100% - 4 * ( 1% + 1% ) ==> 92%, 92% / 4 => 23%)

#