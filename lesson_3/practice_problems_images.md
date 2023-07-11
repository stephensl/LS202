# Practice Problems: Images and Figures

These practice problems use this image: https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg.

#

1. Write HTML to display the image. Don't use a `<figure>` or `<figcaption>` right now.

Answer: 

```html
<img src="cats.jpg" alt="two mustachioed feline friends">
```

#

2. Use CSS to set the width of the image to 250 pixels.

Answer: 

```css
img {
  width: 250px;
}
```

#

3. Update the CSS width from the previous problem with a height of 350 pixels.

Answer: 

```css
img {
  width: 250px;
  height: 350px;
}
```

4. Set the width of the image to 400 pixels, but keep the height at 350px.

Answer: 

```css
img {
  width: 400px;
  height: 350px;
}
```

#

5. Remove the CSS for the img element, and wrap the `<img>` in a `<figure>` tag with a yellow background.

Answer: 

```html
<figure>
  <img src="cats.jpg" alt="two mustachioed feline friends">
</figure>
```

```css
figure {
  background-color: yellow;
}
```
Background color stretches most of the way across the window since `<figure>` is a `block` element. 

#

6. Add caption below the image

Answer: 

```html
<figure>
  <img src="cats.jpg" alt="two mustachioed feline friends">
  <figcaption>
    Two very aristoCATic felines!
  </figcaption>
</figure>
```

#

7. Move the caption above the image

Answer: 
```html
<figure>
  <figcaption>
    Two very aristoCATic felines!
  </figcaption>
  <img src="cats.jpg" alt="two mustachioed feline friends">
</figure>
```

#