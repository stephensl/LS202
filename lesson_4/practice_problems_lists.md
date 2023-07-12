# Practice Problems: Lists

1. Using the "Raw Text" shown below, create a Web page that looks like the image pictured below it.

**Raw Text**:

The Next Reckoning: Capitalism and Climate Change
By NATHANIEL RICH
The world’s most difficult problem has a solution so simple that it can be
expressed in four words: Stop burning greenhouse gases. How exactly to pull
this off is somewhat more complicated — just not as complicated as most
Americans have been led to believe.

Related articles
What Survival Looks Like After the Oceans Rise
How Big Business is Hedging Against the Apocalypse
Climate Chaos is Coming–and the Pinkertons Are Ready


Answer: 
```html
<header>
  <h1>The Next Reckoning: Capitalism and Climate Change</h1>
  <p>By NATHANIEL RICH</p>
</header>

<p>
  The world’s most difficult problem has a solution so simple that it can be
  expressed in four words: Stop burning greenhouse gases. How exactly to
  pull this off is somewhat more complicated — just not as complicated as
  most Americans have been led to believe.
</p>

<h2>Related articles</h2>
<ul>
  <li>What Survival Looks Like After the Oceans Rise</li>
  <li>How Big Business is Hedging Against the Apocalypse</li>
  <li>Climate Chaos is Coming–and the Pinkertons Are Ready</li>
</ul>
```

- `header` provides semantic meaning. 
  - shows `h1` and `p` tags are part of page header
  - use `header` with any part of page that is a page or section header.

#

2. Add CSS to your solution for the previous problem to remove the bullet character before each list item.

Answer: 

```css
ul {
  list-style-type: none;
}
```

#

3. Using the "Raw Text" shown below, create a Web page that looks like the image pictured below it.

**Raw Text**
```
5 Reasons to Use jQuery
Open Source
Endless Tutorials
Huge Library
Cross-browser Compatibility
Large Variety of Plugins
```

Answer: 

```html
<header>
  <h1>5 Reasons to Use jQuery</h1>
</header>

<ol>
  <li>Open Source</li>
  <li>Endless Tutorials</li>
  <li>Huge Library</li>
  <li>Cross-browser Compatibility</li> 
  <li>Large Variety of Plugins</li>
</ol>
```

#

4. Add CSS to your solution for the previous problem to change the numbers from decimal to uppercase Roman digits (I, II, III, IV, V).


```css
<style>
  ol {
    list-style-type: upper-roman;
  }
</style>
```

#

5. Update your solution from the previous problem to number the items in descending order (V, IV, III, II, I).

Answer: 

`<ol reversed>`
- Uses boolean attribute

#

6. Using the "Raw Text" shown below, create a Web page that looks like the image pictured below it.

**Raw Text**
```
HTML
Hypertext Markup Language, a standardized system for tagging text files to
achieve font, color, graphic, and hyperlink effects on World Wide Web pages.

Semantic
Relating to meaning in language or logic.

CSS
A style sheet language used for describing the presentation of a document
written in a markup language.
```

Answer: 

```html
<dl>
  <dt>HTML</dt>
    <dd>
      Hypertext Markup Language, a standardized system for tagging text files to achieve font, color, graphic, and hyperlink effects on World Wide Web pages.
    </dd>
  <dt>Semantic</dt>
    <dd>Relating to meaning in language or logic.</dd> 
  <dt>CSS</dt>
    <dd>
      A style sheet language used for describing the presentation of a document written in a markup language.
    </dd>
</dl>
```

#

7. The following code is an attempt to create a vertical navigation list on a web page:

```html
<nav>
  <ul>
    <li>Home</li>
    <li>Projects</li>
    <li>Team</li>
    <li>Help</li>
  </ul>
</nav>
```

```css
html {
  font-size: 20px;
}

nav ul {
  background-color: yellow;
  width: 200px;
}

nav li {
  color: blue;
}

nav a {
  box-sizing: border-box;
  line-height: 2.5;
  padding: 0 10px;
  text-decoration: none;
  width: 100%;
}
```

Answer: 
```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Projects</a></li>
    <li><a href="#">Team</a></li>
    <li><a href="#">Help</a></li>
  </ul>
</nav>
```

```css
<style>
  html {
    font-size: 20px;
  }

  nav ul {
    background-color: yellow;
    width: 200px;
    list-style-type: none; /* removes bullets */
    padding-left: 0;       /* removes padding */
  }

  nav li {
    color: blue;
  }

  nav a {
    box-sizing: border-box;
    display: inline-block;  /* added */
    line-height: 2.5;
    padding-left: 10px;
    text-decoration: none;
    width: 100%;
  }

  nav a:hover,
  nav a:focus {
    background-color: green;
    color: yellow;
  }
</style>
```

#

8. Convert the solution from the last problem to a horizontal navigation bar that takes up the full width of the page. Again, try not to peek at the previous assignment. 

Answer: 

```css
<style>
  html {
    font-size: 20px;
  }

  nav ul {
    background-color: yellow;
    width: 100%;
    list-style-type: none;
    padding-left: 0;
    font-size: 0;
  }

  nav li {
    display: inline-block;
    font-size: 1rem;
    text-align: center;
    color: blue;
    width: 25%;
  }

  nav a {
    box-sizing: border-box;
    display: inline-block;
    line-height: 2.5;
    padding-left: 10px;
    text-decoration: none;
    width: 100%;
  }

  nav a:hover,
  nav a:focus {
    background-color: green;
    color: yellow;
  }
</style>
```

#
