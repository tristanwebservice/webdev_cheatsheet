# HTML: Next Steps & Semantics

## What is HTML?
HTML (HyperText Markup Language) is the standard markup language used to create web pages. It structures content on the web by using a series of elements and tags that define the layout and presentation of text, images, links, and other media.

## Block vs Inline Elements
HTML elements can be categorized into two main types: block elements and inline elements.

- **Block Elements**: These elements take up the full width available and start on a new line. Common block elements include:
  - `<div>`: A generic container for grouping content.
  - `<h1>`, `<h2>`, etc.: Headings that define the structure of the document.

- **Inline Elements**: These elements only take up as much width as necessary and do not start on a new line. Examples include:
  - `<span>`: A generic inline container for styling a portion of text.
  - `<a>`: Defines hyperlinks.

## Elements: hr, br, sup & sub
- `<hr>`: Creates a thematic break (horizontal rule) in the content, often used to separate sections.
- `<br>`: Inserts a line break, allowing text to continue on the next line without starting a new paragraph.
- `<sup>`: Renders text as superscript, typically used for footnotes or exponents.
- `<sub>`: Renders text as subscript, often used in chemical formulas or mathematical expressions.

## Entity Codes
Entity codes are used to represent special characters in HTML that may otherwise be interpreted as HTML syntax. For example:
- `&lt;` for `<`
- `&gt;` for `>`
- `&amp;` for `&`
- `&nbsp;` for a non-breaking space

## Intro to Semantic Markup
Semantic markup refers to the use of HTML elements that convey meaning about the content they contain. This enhances accessibility and SEO. Examples of semantic elements include:
- `<header>`: Represents introductory content or navigational links.
- `<article>`: Represents a self-contained composition in a document.
- `<footer>`: Represents the footer of a section or page.

## Playing with Semantic Elements
Using semantic elements improves the structure and readability of HTML documents. For example:
```html
<article>
  <header>
    <h1>Understanding HTML Semantics</h1>
  </header>
  <p>This article explains the importance of semantic markup.</p>
  <footer>
    <p>Published on: <time datetime="2023-10-01">October 1, 2023</time></p>
  </footer>
</article>
```
*Comments in the code help clarify the purpose of each section.*

## Screen Reader
Screen readers are assistive technologies that read aloud the content of web pages to users with visual impairments. Using semantic HTML helps screen readers interpret the structure and meaning of the content, improving accessibility.

## VSCode: Emmet
Emmet is a powerful toolkit integrated into Visual Studio Code (VSCode) that allows for faster HTML and CSS coding. It enables users to write shorthand code that expands into full HTML structures. For example, typing `div.container>ul>li*3` and pressing `Tab` will generate:
```html
<div class="container">
  <ul>
    <li></li>
    <li></li>
    <li></li>
  </ul>
</div>
```
*This feature significantly speeds up the coding process and enhances productivity.*

---
