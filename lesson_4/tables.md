# Tables Overview

Tables should be used for strictly tabular data, *not layout*.

## Tags to construct tables

- `<table>` defines a table
- `<tr>` defines a single row in a table
- `<td>` defines a single cell of content in a table
  - each row includes zero or more cells
- `<th>` defines a single heading
  - first cell in a row or column is typically a heading though not a requirement to be so
- `<thead>`, `<tbody>`, and `<tfoot>` each define a set of one or more rows that comprise the header, body, footer rows of a table. 

Example: 
```html
<table>
  <tr>                      <!-- row 1 -->
    <th>Color Name</th>       <!-- column header 1 -->
    <th>Color Hex</th>        <!-- column header 2 -->
    <th>Color Decimal</th>    <!-- column header 3 -->
  </tr>

  <tr>                      <!-- row 2 -->
    <th>red</th>              <!-- row header (column 1) -->
    <td>#f00</td>             <!-- data cell 1 (column 2) -->
    <td>255, 0, 0</td>        <!-- data cell 2 (column 3) -->
  </tr>

  <tr>                      <!-- row 3 -->
    <th>green</th>            <!-- row header (column 1) -->
    <td>#0f0</td>             <!-- data cell 1 (column 2) -->
    <td>0, 255, 0</td>        <!-- data cell 2 (column 3) -->
  </tr>

  <tr>                      <!-- row 4 -->
    <th>blue</th>             <!-- row header (column 1) -->
    <td>#00f</td>             <!-- data cell 1 (column 2) -->
    <td>0, 0, 255</td>        <!-- data cell 2 (column 3) -->
  </tr>
</table>
```

```css
table {
  font-size: 1.5rem;
}
```

*We use `<th>` to define the column and row headings, and how the browser renders the heading cells differently from the data cells.*

#

## Semantic Table HTML and Heading Scope

Use `<thead>`, `<tfoot>`, and `<tbody>` elements to provide semantic identification of the header, footer, and body rows. 

May also add `scope` attribute to identify the `<th>` elements as a row `scope="row"` or column `scope="col"` headings. 

Addition to previous example: 
```html
<table>
  <thead>                              <!-- heading rows -->
    <tr>                                 <!-- row 1 -->
      <th scope="col">Color Name</th>      <!-- column header 1 -->
      <th scope="col">Color Hex</th>       <!-- column header 2 -->
      <th scope="col">Color Decimal</th>   <!-- column header 3 -->
    </tr>
  </thead>

  <tbody>                              <!-- body rows -->
    <tr>                                 <!-- row 2 -->
      <th scope="row">red</th>             <!-- row header (column 1) -->
      <td>#f00</td>                        <!-- data cell 1 (column 2) -->
      <td>255, 0, 0</td>                   <!-- data cell 2 (column 3) -->
    </tr>

    <tr>                                 <!-- row 3 -->
      <th scope="row">green</th>           <!-- row header (column 1) -->
      <td>#0f0</td>                        <!-- data cell 1 (column 2) -->
      <td>0, 255, 0</td>                   <!-- data cell 2 (column 3) -->
    </tr>

    <tr>                                 <!-- row 4 -->
      <th scope="row">blue</th>            <!-- row header (column 1) -->
      <td>#00f</td>                        <!-- data cell 1 (column 2) -->
      <td>0, 0, 255</td>                   <!-- data cell 2 (column 3) -->
    </tr>
  </tbody>

  <tfoot>                              <!-- footer -->
    <tr>                                 <!-- row 5 -->
      <td>name</td>                        <!-- data cell 1 (column 1) -->
      <td>#rrggbb</td>                     <!-- data cell 2 (column 2) -->
      <td>red, green, blue</td>            <!-- data cell 3 (column 3) -->
    </tr>
  </tfoot>
</table>
```

```css
table {
  font-size: 1.5rem;
}

th {
  font-size: 1.75rem;
}

tbody tr {
  font-style: italic;
}

tbody tr:nth-child(1) {
  color: red;
}

tbody tr:nth-child(2) {
  color: green;
}

tbody tr:nth-child(3) {
  color: blue;
}

tfoot tr {
  font-size: 1rem;
}

tfoot td {
  border-top: 1px solid gray;
}

td {
  text-align: center;
}

[scope="col"] {
  padding: 0 10px;
  text-decoration: underline;
}

[scope="row"] {
  text-transform: uppercase;
}
```
Use `:nth-child()` pseudo-class to select the first, second, and third rows of the `tbody`. 