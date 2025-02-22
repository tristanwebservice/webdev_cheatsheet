# CSS: The Very Basics

## What is CSS?

CSS (Cascading Style Sheets) is a stylesheet language used to describe the presentation of HTML (or XML) documents. It allows developers to control the layout, colors, fonts, and overall visual appearance of web pages, ensuring a consistent look across different devices and screen sizes.

## CSS is a Huge Subject

CSS encompasses a wide range of properties and techniques for styling web pages. It includes various selectors, layout models, and responsive design principles. Mastering CSS requires understanding its syntax, properties, and how to apply them effectively to achieve desired designs.

## Including Styles Correctly

CSS styles can be included in HTML documents in three primary ways:

1. **Inline Styles**: Applied directly to HTML elements using the `style` attribute.

    ```html
    <!-- Inline style example -->
    <h1 style="color: blue;">Hello, World!</h1>
    ```

2. **Internal Styles**: Defined within a `<style>` tag in the `<head>` section of an HTML document.

    ```html
    <head>
      <style>
        /* Internal style example */
        h1 {
          color: blue;
        }
      </style>
    </head>
    ```

3. **External Styles**: Stored in separate `.css` files and linked to HTML documents using the `<link>` tag.

    ```html
    <head>
      <link rel="stylesheet" type="text/css" href="styles.css" />
    </head>
    ```

    In `styles.css`:

    ```css
    /* External style example */
    h1 {
      color: blue;
    }
    ```

## Color and Background Color Properties

- **`color`**: Sets the text color of an element.
- **`background-color`**: Sets the background color of an element.

    ```css
    /* Example of color and background-color properties */
    body {
      color: black; /* Text color */
      background-color: white; /* Background color */
    }
    ```

## Color Systems: RGB, Named Colors, and Hexadecimal Colors

CSS supports several color systems:

1. **Named Colors**: Predefined color names like `red`, `blue`, and `green`.

    ```css
    /* Using named colors */
    p {
      color: red; /* Text color */
    }
    ```

2. **RGB (Red, Green, Blue)**: Specifies colors using the `rgb()` function with values ranging from 0 to 255 for each component.

    ```css
    /* Using RGB color model */
    p {
      color: rgb(255, 0, 0); /* Red */
    }
    ```

3. **Hexadecimal Colors**: Uses a six-digit hexadecimal code (`#RRGGBB`) to represent colors.

    ```css
    /* Using hexadecimal color */
    p {
      color: #ff0000; /* Red */
    }
    ```

## Reminder: Semicolons in CSS

Semicolons (`;`) are essential for separating CSS property-value pairs. Omitting them can lead to unexpected behavior or broken styles.

```css
/* Correct usage of semicolons */
p {
  color: blue; /* Correct */
  font-size: 16px; /* Correct */
}

/* Incorrect usage of semicolons */
p {
  color: blue font-size: 16px; /* Incorrect */
}
```

## Common Text Properties

CSS provides several properties for styling text:

- **`font-size`**: Sets the size of the text.
- **`font-weight`**: Defines the boldness of the text.
- **`text-align`**: Aligns the text within its container.
- **`text-decoration`**: Adds decorations like underlines.

    ```css
    /* Example of common text properties */
    p {
      font-size: 16px; /* Font size */
      font-weight: bold; /* Bold text */
      text-align: center; /* Centered text */
      text-decoration: underline; /* Underlined text */
    }
    ```

## Font Size Basics with Pixels

The `font-size` property is commonly set using pixels (`px`). Pixels provide precise control over text size, ensuring consistency across different browsers and devices.

```css
/* Setting font size in pixels */
p {
  font-size: 16px; /* Font size set to 16 pixels */
}
```

## The Font Family Property

The `font-family` property specifies the font to be used for an element's text. It accepts a list of font names as a fallback mechanism. If the first font is unavailable, the browser tries the next one, and so on. It's good practice to include a generic font family (e.g., `sans-serif`, `serif`, `monospace`) as the last option.

```css
/* Example of font-family property */
p {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif; /* Font stack */
}
```
