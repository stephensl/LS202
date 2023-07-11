# Adding Images to Web Pages

## The `img` element

`<img>` is a self closing tag that tells browser to load and fisplay a foreground image from a separate resource.

### Four Attributes of Interest
  - `src`
    - **required**
    - tells browser where to find image
    - uses same URL format as links in the `<a>` tag
    - URL can be relative, root-relative, or absolute

  - `alt`
    - optional, but almost always utilized
    - describes content of the image for users who cannot view it, or have images disabled
    - screen readers use `alt` attribute to tell user about image content. 
    - search engines use `alt` to index images
      - relevant to search engine optimization (SEO)
    - if omitted, browser can still render image
  
  - `width` and `height`
    - optional
    - provide width and height in pixels 
    - CSS `width` and `height` properties override HTML attributes in rendered version of the page.

    *if you plan to almost always display images with specific width and height, should use the attributes to specify those values in order for browser to optimize rendering speed by allocating room for image before finishes downloading* 

#### Typical Image Tag

```html
<img src="mountain.jpg" alt="The summit of Mount Everest" width="800" height="600">
```

#

## Figure and Figcaption

Designates an item as a representation of information discussed in the content. 
- Tag encloses some media that illustrates the surrounding content
- can supply caption with the optional `<figcaption>` tag:
```html
<figure>
  <img src="masthead.jpg" alt="Sunset over the forest">
  <figcaption>The sun sets over the dense forest</figcaption>
</figure>
```

Not needed unless media is referenced in the text. Therefore, unnecessary for things like logos, background images, fancy bullets, and other decorative items. 

#

## Images as Links

Any non-interactive HTML element can be used as a link. 

To make an image clickable, and link to another page, place `img` tag inside an `a` tag:

```html
<a href="https://realtor.com">
  <img src="house.jpg" alt="craftsman one story home">
</a>
```

#

## Background Images

Background images appear behind the content for the element that requested the background, and its descendants. 

Most background images apply to an entire page, so we use the `body` selector to specify them. However, you can apply backgrounds to any selector, such as a tag, class, or id selector. 

```html
<section>
  There's a great, big, beautiful tomorrow shining at the end of every day...a great, big, beautiful tomorrow...just a dream away!
</section>

<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Work</a></li>
    <li><a href="#">Play</a></li>
  </ul>
</nav>
```

```css
html {
  font-size: 32px;
}

body {
  background-image:
    url("http://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/gradient-background.png");
}

section {
  display: inline-block;
  width: 500px;
}

nav {
  background-image:
    url("http://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/blurry.png");
  display: inline-block;
  height: 200px;
  width: 250px;
}
```

Other background properties you can provide include the size of the image, positioning, repeat counts, etc. 

```css
body {
  background-size: 25%;
}
```

