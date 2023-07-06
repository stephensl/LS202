# Focus Areas

## Vocabulary 
  - element and tag 
  - self-closing tag 
  - document type definition
    - (DOCTYPE, DTD)
  - attribute 
  - selector 
  - property
  - id, class, and name

## HTML vs CSS
  - HTML 
    - Provides structure and content of a web page. 
  - CSS
    - Describes the appearance or presentation of the page.
  - Overlap
    - CSS can dictate apparent structure, and HTML can inform the browser of some presentation elements. 

## Structure of Web Page
  - All pages start with routine code that defines basic layout: 
    - DOCTYPE
    - `<html>`, `<head>`, and `<body>` element
    - Additional tags in `<head>` section
  - Understand this boilerplate code and what it does. 

## Basic HTML Elements
  - `<p>` paragraph 
    - primary organizational construct

  - `<a>` anchor 
    - represent links to other pages

  - `<h1>`-`<h6>` header elements
    - headers occur on most pages


  - Additional elements 
    - `<em>`, `<strong>`
    - `<header>`, `<main>`
    - `<article>`, `<section>`, `<aside>`
    - `<div>` and `<span>`


## Using CSS in HTML Document
  - inline
  - internal
  - external 
  
  - use of `<style>` tag to provide internal CSS


## CSS Selectors 
  - `<tag>`
  - `<id>`
  - `<class>`

  - Used to select elements based on tag name, id attribute, or class attribute. 

## Key CSS Properties for now
  - `color`
  - `background-color`
  - `font-family`
  - `font-size`




# Shay Howe Course: HTML/CSS

## Lesson 1

### HTML vs CSS
  - Hypertext Markup Language (HTML)
    - Provides structure and meaning by defining the content as headings, paragraphs, images, etc. 
  
  - Cascading Style Sheets (CSS)
    - Presentation language to style the appearance of content using fonts, colors, etc. 

  *HTML represents the content, while CSS represents the appearance of that content.*


### HTML Terms
  
  - Elements 
    - Designators defining structure and content of objects within a page. 
    - Identified by use of `<` and `>` surrounding the element name.
      - Examples: 
        - multiple levels of headings
          - `<h1>` - `<h6>`
        - paragraphs 
          - `<p>`
        - `<a>`, `<div>`, `<span>`, `<strong>`, `<em>`, etc. 


  - Tags
    - The use of `<` and `>` surrouding an element creates a *tag*.
    - Tags occur in paris of opening and closing tags. 
      - Opening tag 
        - marks beginning of element
          - `<element_name>`
      - Closing tag 
       - marks end of element 
        - `</element_name>`
    - Content between opening and closing tags is content of that element. 
      - Example: 
        - `<a>` *content of the anchor link* `</a>`


  - Attributes
    - Properties providing additional information about an element.
    - Defined within the opening tag, after the element's name and value. 
      
    - Format consists of attribute name, equals sign, quoted attribute value. 
      - Example: `<a>` element including an `href` attribute
        - `<a href="http://google.com">Google</a>` 
      - The example code will display the text "Google" on the page and take users to the link. 
    
    - Most Common Attributes
      - `id` 
        - identifies an element
      - `class` 
        - classifies an element
      - `src` 
        - specifies source for embedded content
      - `href`
        - provides hyperlink reference to linked resource

  ### HTML Document Structure
  
  - Plain text documents saved with `.html` file extension. 
    
  - All HTML documents have required structure including the following declaration and elements: 
      
    - `<!DOCTYPE html>`
      - document type declaration informs browser which version of HTML used (latest). 
    
    - `<html>`
      - element signifies beginning of the document. 
    
    - `<head>` 
      - inside `<html>` element
      - identifies top of the document including any metadata.
      - content not displayed on page
        - may include document title displayed on the title bar in browser window, links to external files, other metadata.
    
    - `<body>`
      - all visible content within the page falls within the `<body>` element. 

**Example Structure**

  ```html 
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="utf-8">
      <title>Hello World</title>
    </head>
    <body>
      <h1> Hello World</h1>
      <p>This is a web page.</p>
    </body>
  </html>
  ```
  *Nested elements occur when an element is placed inside another element. heading and paragraph elements are nested within the body element, and thus, are visible on the page.*

  #### Self closing elements

  In the example above, the `<meta>` element had only one tag, and did not include a closing tag. Content is assigned with the use of the `charset` attribute and value. 

  Other self-closing elements: 
    `<br>`,
    `<img>`,
    `<wbr>`,
    `<embed>`,
    `<param>`,
    `<source>`,
    *among others*.


 ### CSS Terms

 - Selectors 
  - designates which element or elements within our HTML to target and apply style. 
  - may be general (every paragraph on a page) or specific (a particular paragraph on the page).
  - generally target an attribute value such as an `id` or `class` value, or the type of element `<h1>` or `<p>`.

  - Selectors are followed with curly brackets which encompass the style to be applied to the selected element.
    - Example: selector targeting all `<p>` elements. 
      - `p { ... }`

  
  - Properties 
    - Once element selected, property determines styles applied to element. 
      - occur after selector within the curly brackets, preceding a colon. 
    
    - Example properties: 
      - `background color`
      - `font size`
      - `height`
      - `width`

    - Example defining `color` and `font-size` properties applied to all `<p>` elements. 

    ```css 
    p {
      color: ...;
      font-size: ...;
    }
    ```

  - Values 
    - Defines behavior of property.
    - text between `:` and `;`

    - Example: selecting all `<p>` elements and setting value of the `color` property to `orange` and the value of the `font-size` property to `16` pixels. 

    ```css
    p {
      color: orange;
      font-size: 16px;
    }
    ```

  **Review Summary CSS**

  In CSS our rule begins with the selector, immediately followed by curly brackets. Within curly brackets are declarations consisting of property and value pairs. Each declaration begins with a property, followed by a colon, the property value, and a semicolon. 


  #### Working with Selectors 

  - Most Common Selectors: 

    - Type Selectors 
      - target by element type
      - Example: 
        - `div { ... }` targets all division elements. 

    - Class Selectors 
      - target based on `class` attribute value. 
      - more specific than type selectors, and allows assignment of style to different element types using the same `class` attribute.
        - example: 
          `.awesome { ... }` 
          - targets in html...
          ```html 
          <div class="awesome">...</div>
          <p class="awesome">...</p>
          ```

    - ID Selectors 
      - further precision 
      - target one unique element at a time. 
      - use element's `id` attribute value as the selector. 

      - `id` attribute values can only be used once per page, and should be reserved for significant elements. 

      - ID selectors defined with leading `#` followed by `id` attribute value. 
        - Example: `#lawton { ... }`
          - targets `<div id="lawton">...</div>`


  ### Referencing CSS file in HTML 

  *best practice is to include all styles in a single external style sheet which is referenced within the `<head>` element of HTML document*

  - Allows for use of same styles across entire site, and quickly making changes site-wide. 

  #### Linking in HTML 
  - Within `<head>` element of HTML document...
    
    - `<link>` element used to define relationship between HTML and CSS file. 
    
    - `<rel>` attribute with value `stylesheet` to specify relationship. 
    
    - `<href>` attribute is used to identify the location, or path of CSS file. 

    - Example:
    ```html 
    <head>
      <link rel="stylesheet" href="main.css">
    </head>
    ```

  ### CSS Resets 
  - Each web browser has default styles for different elements.
    - CSS resets used to ensure cross-browser compatibility.
    - Take every common HTML element with predefined style and provide one unified style for all browsers. 
      - Removing sizing, margins, padding, or additional styles. 
        - Must be at the top of the stylesheet. (renders top to bottom)
          - Eric Meyer's reset is one of most popular. 

    
## Lesson 2: Getting to Know HTML

### Semantics within HTML

- Giving content on the page meaning and structure by using the proper element. 
  - Semantic code describes the *value* of content on a page, regardless of the style or appearance of that content. 
    - tags such as <header>, <footer>, <nav>, <article>, and <section> are semantic tags because they describe the type and purpose of the content they contain.

- Benefits to using semantic elements:
  - enabling computers, screen readers, search engines, etc. to read and understand content on a web page. 
  - easier to manage and work with by showing exactly what each piece of content is about. 


      #### Block vs Inline elements

      - Block-level elements
        - begin on a new line
        - stacked on top of each other
        - occupy any available width
        - may be nested inside one another and may wrap inline-level elements. 

        - Most common appearance in code:
          - larger pieces of content such as paragraphs

      - Inline-level elements
        - do not begin on new line
        - fall into normal flow of document
        - lined up one after another
        - may wrap inline-level elements

          - Most common appearance in code: 
            - smaller pieces of content, such as a few words. 


  ### `<div>` and `<span>`

  **Provide ability to apply targeted styles to a contained set of content**
  
  - `<div>`
    - block-level element
    - used to identify large groupings of content
  - `<span>`
    - inline-level element
    - used to identify smaller groupings of text within a block-level element. 


  ##### Comments in HTML
    - Start with `<!--` and end with `-->`. 

  ##### Comments in CSS 
    - Start with `/*` and end with `*/`.

  
### Text-based Elements 
  - Headings, paragraphs, bold-text 

#### Headings
  - Block level elements
  - Six rankings
    - `<h1>` - `<h6>`
  - Break up content, assist search engines, user experience.

  - Headings should be used in order relevant to content of the page. 

  - Each heading should be semantically valued, and not used ot make text bold or big (better ways to do this.)

  - Example
  ```html
  <h1>Headings Level 1</h1>
  <h2>Headings Level 2</h2>
  <h3>Headings Level 3</h3>
  <h4>Headings Level 4</h4>
  ...
  ```


#### Paragraphs
  - Headings often followed by supporting paragraphs. 
  - Defined by `<p>` block element.

  - Example: 
  ```html 
  <p>Steve Jobs was co-founder and longtime chief executive of Apple.</p>

  <p>In his address, Steve urged graduates to follow their dreams.</p>
  ```


  #### Bold Text with Strong
  - `<strong>` in-line level element. 
    - semantically used to give strong importance to text, and is most popular option for bolding text. 
  - `<b>` element
    - stylistically offset the text
    - not always best for text deserving prominent attention. 

  ```html
  <!-- strong importance -->
  <p><strong>Caution:</strong> Falling rocks.</p>

  <!-- Stylistically offset -->
  <p>This recipe calls for <b>bacon</b> and <b>baconnaise</b>.</p>
  ```

  #### Italicize with Emphasis
  - Use `<em>` inline-level elements.
    - most popular for placing stressed emphasis on the text. 

  - `<i>` elements used semantically to convey alternative voice or tone.

  ```html
  <p>I <em>love</em> Chicago!</p>

  <p>The name <i>Shay</i> means gift.</p>
  ```

### Building Structure 

- Header
  - `<header>` element used to identify top of page, article, section. 
  - may include heading, introductory text, or navigation. 

  #### `<header>` vs `<head>` vs `<h1>`-`<h6>`. 

  - `<header>` is structural element outlines heading of a segment of a page. 
    - falls within the `<body>` element. 

  - `<head>` is not displayed on page and used to outline metadata, including the document title, and links to external files.
    - falls within the `<html>` element. 

  - `<h1>`-`<h6>` used to designate multiple levels of text headings throughout the page.


- Navigation
  - `<nav>` element
    - identifies section of major navigational links on a page. 
    - reserved for primary navigation sections only (table of contents, previous/next links, etc.)

    - Links included within the `<nav>` element will link to other pages within the same website, or parts of the same page. 
    - Misc, one-off links should use the `<a>` anchor element. 


- Article
  - `<article>` element
  - Used to identify section of independent, self-contained content that may be independently distributed/reused. 
    - Often used for blog posts, newspaper articles, user-submitted content, etc. 
  - Must first determine if content within the element could be replicated elsewhere without any confusion. 


- Section
  - `<section>` element
  - Used to identify thematic grouping of content, which generally includes a heading. 
  - Breaks up and provides hierarchy to page.


### Deciding between `<article>`, `<section>`, or `<div>` elements. 

- Determined based on the content.

- `<article>` and `<section>` contribute to document structure and outlines the content. 
  - if content grouped solely for styling purposes and does not provide value ot the outline of a document, use `<div>`.

- If content adds to document outline and can be independently reused, use `<article>` element. 

- If content adds to document outline and represents a thematic group of content, use the `<section>` element. 



- Aside 
  - `<aside>` element holds content such as: 
    - sidebars
    - inserts
    - brief explanations
  - block-level element (occupies the full width of the page, or element they are nested within (parent))
  
- Footer
  - `<footer>` element identifies the end of the page, article, section, or other segment. 
  - usually found at bottom of its parent element. 
  - includes relative content and should not diverge from document or section it is included within. 


### Encodings
- The <h3> element within our <header> element, as well as the <small> element within our <footer> element, has some interesting things going on. Specifically, a few special characters within these elements are being encoded.

- Special characters include various punctuation marks, accented letters, and symbols. When typed directly into HTML, they can be misunderstood or mistaken for the wrong character; thus they need to be encoded.

- Each encoded character will begin with an ampersand, &, and end with a semicolon, ;. What falls between the ampersand and semicolon is a character’s unique encoding, be it a name or numeric encoding.


### Creating Hyperlinks 
- Use `<a>` anchor inline-level element along with `<href>` attribute which identifies the destination of the link. 

```html
<a href="http://shayhowe.com">Shay</a>
```

  - The above will display `Shay` on the page, and when clicked, will link to website.

  - Must use relative path for pages on same site. Linking outside of current site must include full domain. 


  #### Linking to email address.
  
  - `<href>` value must start with `mailto:` followed by the email where it should be sent. 

  ```html
  <a href="mailto:lstep@gnail.com">Email Me</a>
  ```

  - Altogether, a link to shay@awesome.com with the subject of “Reaching Out” and body text of “How are you” would require an href attribute value of: 
  ```html 
  <a href="mailto:shay@awesome.com?subject=Reaching%20Out&body=How%20are%20you">Email Me</a>
  ```


  #### Opening links in new window
  - use `<target>` attribute, with value of `_blank` which specifies a new window. 
  ```html
  <a href="http://google.com/" target="_blank">Google</a>
  ```

  #### Links to parts of same page
  - set `id` attribute on the element we wish to link to
  - use value of `id` attribute within an anchor element's `href` attribute.

  - Example: Back to Top
  ```html
  <body id="top">
    ...
    <a href="#top">Back to top</a>
    ...
  </body>
  ```


### Summary for Getting to Know HTML

Once again, in this lesson we covered the following:

  - What semantics are and why they are important
  
  - <div>s and <spans>s, and the difference between block- and inline-level elements
  
  - Which text-based elements best represent the content of a page
  
  - The HTML5 structural elements and how to define the structure and organization of our content and page
  
  - How to use hyperlinks to navigate between web pages or websites




## Getting to Know CSS

### The Cascade 
  - Stylesheet cascades top to bottom.

- Calculating Specificity
  - Every selector has a specificity weight. 
    - Weight, along with placement in the cascade identifies how its styles will be rendered.
  
  - Selectors:
    - `<type>` lowest specificity weight with point value `0-0-1`
    - `<class>` medium specificity weight with point value `0-1-0`
    - `<id>` high specificity weight with point value `1-0-0`

  #### Combining selectors 
  - Used to be more specific about which elements or group of elements we would like to select. 

  - Example: select all paragraph elements that reside within an element with a class attribute of `hotdog` and set their background color to `brown`. However, if one of the paragraphs happens to have class attribute value of `mustard` we want to set its background color to `yellow`. 

  ```html 
  <div class="hotdog">
    <p>...</p>
    <p>...</p>
    <p class="mustard">...</p>
  </div>
  ```

  ```css
  .hotdog p {
    background: brown;
  }
  .hotdog p.mustard {
    background: yellow;
  }
  ```

- Key points in combining selectors:
  - should be read from right to left
    - the selector furthest to the right, directly before the opening `{` is known as the *key* selector.
    - Key selector identifies exactly which element styles will be applied to. 
    - Any selector to the left of the key selector will serve as a pre-qualifier. 

  - Example from above: 
  
  `.hotdog p` includes two selectors, a class and type selector. 
  
  - `p` is key selector targeting paragraph elements
  - `.hotdog` is a pre-qualified class selector 
  - This will select only paragraph elements that reside within an element with a class attribute value of `hotdog`.

#### Three selectors
`.hotdog p.mustard` 

- Key is class selector `mustard` with two pre-qualifiers. 
  - `p` is paragraph type selector
  - `hotdog` is a class selector. 
- This will select paragraphs with a class attribute value of `mustard` that reside within an element with the class attribute value of `hotdog`. 

### Specificity Within Combined Selectors

- When combined, selector specificity weights are as well. 

- Weights calculated by counting each different type of selector within a combined selector. 
  - Examples:
  
  ```css
  .hotdog p
  ```
  Above combined class selector(0-1-0) and type selector(0-0-1) == total of `0-1-1`

  ```css
  .hotdog p.mustard
  ```
  Above combined selector weight: two class selectors and one type selector == `0-2-1`


  **The higher specificity weight takes precedence even if occurs first in the cascade**


### Keeping Weights Low
- Modularity
  - different styles by using multiple classes
  - Elements in HTML can have more than one class attribute value (space separated)


### Common CSS Property Values

- Colors
  - Represented in CSS by:
    - keywords
      - limited options
    - hexadecimal notation
      - first two chars = red channel
      - third and fourth chars = green channel
      - last two chars = blue channel
    - RGB values
    - HSL values
