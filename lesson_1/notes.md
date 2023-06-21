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


      





