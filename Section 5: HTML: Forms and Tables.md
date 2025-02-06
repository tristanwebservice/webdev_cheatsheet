# HTML: Forms and Tables

## HTML Tables
HTML tables are used to display data in a structured format, consisting of rows and columns. They are created using the `<table>` element, which contains various child elements to define the structure of the table.

## Tables: TR, TD, and TH Elements
- **`<tr>`**: Represents a table row. Each row can contain one or more cells.
- **`<td>`**: Represents a table data cell, which holds the actual data.
- **`<th>`**: Represents a table header cell, typically used for headings. Header cells are bold and centered by default.

Example:
```html
<table>
  <tr>
    <th>Name</th> <!-- Header cell -->
    <th>Age</th>  <!-- Header cell -->
  </tr>
  <tr>
    <td>John</td> <!-- Data cell -->
    <td>30</td    <!-- Data cell -->
  </tr>
</table>
```

## Tables: Thead, Tbody, Tfoot Elements
- **`<thead>`**: Groups the header content in a table, making it easier to manage and style.
- **`<tbody>`**: Groups the main body content of the table.
- **`<tfoot>`**: Groups the footer content, often used for summary information.

Example:
```html
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John</td>
      <td>30</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2">End of Table</td> <!-- Footer cell spanning two columns -->
    </tr>
  </tfoot>
</table>
```

## Tables: Colspan and Rowspan
- **`colspan`**: Allows a cell to span multiple columns.
- **`rowspan`**: Allows a cell to span multiple rows.

Example:
```html
<table>
  <tr>
    <td colspan="2">Merged Cell</td> <!-- Cell spans two columns -->
  </tr>
  <tr>
    <td rowspan="2">Merged Row</td> <!-- Cell spans two rows -->
    <td>Cell 1</td>
  </tr>
  <tr>
    <td>Cell 2</td>
  </tr>
</table>
```

## The Form Element
The `<form>` element is used to collect user input. It can contain various input elements and is defined with attributes like `action` (where to send the form data) and `method` (how to send the data).

Example:
```html
<form action="/submit" method="POST">
  <!-- Form elements go here -->
</form>
```

## Common Input Types
HTML provides various input types for forms, including:
- **Text**: `<input type="text">`
- **Password**: `<input type="password">`
- **Email**: `<input type="email">`
- **Number**: `<input type="number">`
- **Date**: `<input type="date">`

## The All Important Label
The `<label>` element is crucial for accessibility, as it associates a text description with a form control. It improves usability by allowing users to click the label to focus on the corresponding input.

Example:
```html
<label for="username">Username:</label>
<input type="text" id="username" name="username">
```

## HTML Buttons
Buttons can be created using the `<button>` element or `<input type="button">`. They can trigger actions when clicked.

Example:
```html
<button type="submit">Submit</button> <!-- Submits the form -->
```

## The Name Attribute
The `name` attribute is essential for form elements, as it defines the key for the data sent to the server. Each input should have a unique name.

Example:
```html
<input type="text" name="username"> <!-- Data sent as 'username' -->
```

## Hijacking Google's Search Query
To create a search form that uses Google, set the `action` attribute to Google's search URL and use the `name` attribute as `q`.

Example:
```html
<form action="https://www.google.com/search" method="GET">
  <input type="text" name="q" placeholder="Search Google">
  <button type="submit">Search</button>
</form>
```

## Radio Buttons, Checkboxes, and Selects
- **Radio Buttons**: Allow users to select one option from a set. Use the same `name` for related buttons.
- **Checkboxes**: Allow users to select multiple options.
- **Select**: Creates a dropdown list for users to choose from.

Example:
```html
<label>
  <input type="radio" name="gender" value="male"> Male
</label>
<label>
  <input type="radio" name="gender" value="female"> Female
</label>

<label>
  <input type="checkbox" name="subscribe"> Subscribe to newsletter
</label>

<select name="options">
  <option value="option1">Option 1</option>
  <option value="option2">Option 2</option>
</select>
```

## Range and Text Area
- **Range**: Creates a slider for selecting a numeric value within a specified range.
- **Text Area**: Allows for multi-line text input.

Example:
```html
<label for="volume">Volume:</label>
<input type="range" id="volume" name="volume" min="0" max="100">

<label for="comments">Comments:</label>
<textarea id="comments" name="comments" rows="4" cols="50"></textarea>
```

## HTML5 Form Validations
HTML5 provides built-in form validation features, such as `required`, `minlength`, `maxlength`, `pattern`, and more. These attributes help ensure that users provide valid input before submitting the form.

Example:
```html
<input type="email" name="email" required> <!-- Required email input -->
<input type="text" name="username" minlength="3" maxlength="15"> <!-- Length constraints -->
```

---
