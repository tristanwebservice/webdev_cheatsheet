# The World of CSS Selectors

## Universal and Element Selectors

- **Universal Selector (`*`)**: Selects all elements on the page. Useful for applying global styles.

    ```css
    /* Resets margin and padding for all elements */
    * {
      margin: 0;
      padding: 0;
    }
    ```

- **Element Selector**: Targets specific HTML elements by their tag name.

    ```css
    /* Styles all <h1> elements */
    h1 {
      font-size: 2em;
      color: navy;
    }
    ```

## The ID Selector

- **ID Selector (`#id`)**: Selects a unique element based on its `id` attribute. IDs must be unique within a document.

    ```html
    <div id="header">Header Content</div>
    ```

    ```css
    /* Styles the element with id="header" */
    #header {
      background-color: lightgray;
      padding: 10px;
    }
    ```

## The Class Selector

- **Class Selector (`.class`)**: Selects all elements with a specific class attribute. Multiple elements can share the same class.

    ```html
    <p class="highlight">Highlighted text</p>
    ```

    ```css
    /* Styles all elements with class="highlight" */
    .highlight {
      background-color: yellow;
      font-weight: bold;
    }
    ```

## The Descendant Selector

- **Descendant Selector (`ancestor descendant`)**: Selects elements that are descendants of a specified ancestor.

    ```html
    <div class="container">
      <p>Paragraph inside container</p>
    </div>
    ```

    ```css
    /* Styles all <p> elements inside .container */
    .container p {
      color: green;
    }
    ```

## Adjacent and Direct Descendant Selectors

- **Adjacent Sibling Selector (`element + element`)**: Selects the element that is immediately following another specified element.

    ```html
    <h2>Title</h2>
    <p>First paragraph.</p>
    ```

    ```css
    /* Styles the paragraph immediately following an <h2> */
    h2 + p {
      margin-top: 0;
    }
    ```

- **Direct Descendant Selector (`parent > child`)**: Selects elements that are direct children of a specified parent.

    ```html
    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
    </ul>
    ```

    ```css
    /* Styles only the direct <li> children of <ul> */
    ul > li {
      list-style-type: square;
    }
    ```

## The Attribute Selector

- **Attribute Selector (`[attribute]`)**: Selects elements based on the presence or value of an attribute.

    ```html
    <input type="text" placeholder="Enter text">
    ```

    ```css
    /* Styles all input elements with a placeholder */
    input[placeholder] {
      border: 1px solid #ccc;
    }
    ```

## Pseudo-classes

- **Pseudo-classes**: Select elements based on their state or position.

    ```html
    <a href="#">Link</a>
    ```

    ```css
    /* Styles the link when hovered */
    a:hover {
      color: red;
    }
    ```

## Pseudo-elements

- **Pseudo-elements**: Style specific parts of an element.

    ```html
    <p>This is a paragraph.</p>
    ```

    ```css
    /* Styles the first line of a paragraph */
    p::first-line {
      font-weight: bold;
    }
    ```

## The CSS Cascade

- **CSS Cascade**: The process that determines which CSS rules apply when multiple rules target the same element. It considers:
    1. **Importance**: `!important` rules override normal rules.
    2. **Specificity**: More specific selectors take precedence.
    3. **Source Order**: Later rules override earlier ones.

## What is Specificity

- **Specificity**: A measure of how specific a selector is. It is calculated based on the types of selectors used:
    - Inline styles have the highest specificity.
    - IDs are more specific than classes.
    - Classes are more specific than element selectors.
    - The universal selector has no specificity.

## Tip: Chrome DevTools and CSS

- **Chrome DevTools**: A powerful tool for inspecting and debugging CSS. It allows you to view applied styles, modify them in real-time, and understand the cascade and specificity.

## Inline Styles and !important

- **Inline Styles**: Styles applied directly to an element using the `style` attribute. They have high specificity.

    ```html
    <p style="color: blue;">This is a blue paragraph.</p>
    ```

- **`!important`**: A declaration that overrides all other declarations, regardless of specificity. Use sparingly.

    ```css
    /* Forces the color to be red, overriding other styles */
    p {
      color: red !important;
    }
    ```

## CSS Inheritance

- **CSS Inheritance**: Some properties are inherited by default from parent elements to their children (e.g., `color`, `font-family`). The `inherit` keyword can be used to force inheritance.

    ```css
    body {
      font-family: Arial, sans-serif; /* Inherited by child elements */
    }

    p {
      color: inherit; /* Inherits color from parent */
    }
    ```
