# CSS: The Very Basics

## What is CSS?

CSS (Cascading Style Sheets) is a language used to describe the presentation of HTML (or XML) documents. It controls the layout, colors, fonts, and other visual aspects of web pages, ensuring content is displayed attractively and consistently across different devices.

## CSS is a Huge Subject

CSS is extensive, covering many properties and techniques for styling web pages. Mastering CSS involves understanding its syntax, various properties, and how to apply them effectively to achieve desired designs.

## Including Styles Correctly

CSS styles can be included in HTML documents in three ways:

1.  **Inline Styles:** Applied directly to HTML elements using the `style` attribute.

    ```html
    <!-- Inline styles -->
    <p style="color: blue; font-size: 16px;">This is a paragraph.</p>
    ```

2.  **Internal Styles:** Defined within the `<style>` tag inside the `<head>` section of an HTML document.

    ```html
    <!-- Internal styles -->
    <head>
      <style>
        p {
          color: blue;
          font-size: 16px;
        }
      </style>
    </head>
    ```

3.  **External Styles:** Stored in separate `.css` files and linked to HTML documents using the `<link>` tag.

    ```html
    <!-- External styles -->
    <head>
      <link rel="stylesheet" type="text/css" href="styles.css" />
    </head>
    ```

    In `styles.css`:

    ```css
    /* External styles */
    p {
      color: blue;
      font-size: 16px;
    }
    ```

## Color and Background Color Properties

-   `color`: Sets the text color of an element.
-   `background-color`: Sets the background color of an element.

    ```css
    body {
      color: black;
      background-color: white;
    }
    ```

## Color Systems: RGB, Named Colors, and Hexadecimal Colors

CSS supports several color systems:

1.  **Named Colors:** Predefined color names like `red`, `blue`, `green`, etc.

    ```css
    p {
      color: red;
    }
    ```

2.  **RGB (Red, Green, Blue):** Specifies colors using the `rgb()` function with values from 0 to 255 for each component.

    ```css
    p {
      color: rgb(255, 0, 0); /* Red */
    }
    ```

3.  **Hexadecimal Colors:** Uses a six-digit hexadecimal code (`#RRGGBB`) to represent colors.

    ```css
    p {
      color: #ff0000; /* Red */
    }
    ```

## Reminder: Semicolons in CSS

Semicolons (`;`) are crucial for separating CSS property-value pairs. Forgetting them can lead to unexpected behavior or broken styles.

```css
p {
  color: blue; /* Correct */
  font-size: 16px; /* Correct */
}

p {
  color: blue font-size: 16px; /* Incorrect */
}
```

## Common Text Properties

-   `font-family`: Specifies the font for the text.
-   `font-size`: Sets the size of the text.
-   `font-weight`: Sets the boldness of the text.
-   `text-align`: Aligns the text within its container.
-   `text-decoration`: Adds or removes decorations like underlines.

    ```css
    p {
      font-family: Arial, sans-serif;
      font-size: 16px;
      font-weight: bold;
      text-align: center;
      text-decoration: underline;
    }
    ```

## Font Size Basics with Pixels

The `font-size` property is commonly set using pixels (`px`). Pixels provide precise control over text size, ensuring consistency across different browsers and devices.

```css
p {
  font-size: 16px; /* Sets the font size to 16 pixels */
}
```

## The Font Family Property

The `font-family` property specifies the font to be used for an element's text. It accepts a list of font names as a fallback mechanism. If the first font is not available, the browser tries the next one, and so on. It's good practice to include a generic font family (e.g., `sans-serif`, `serif`, `monospace`) as the last option.

```css
p {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
```
