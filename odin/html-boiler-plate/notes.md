# The Odin Project





```html
<strong>this will make text bold</strong>
<em>this will make the text italic</em>
<!-- this is a comment -->
```

use `ctrl + /` for commenting a line or uncommenting it

## Ordered and unordered list

### reversed

    This Boolean attribute specifies that the list's items are in reverse order. Items will be numbered from high to low.
### start

    An integer to start counting from for the list items. Always an Arabic numeral (1, 2, 3, etc.), even when the numbering type is letters or Roman numerals. For example, to start numbering elements from the letter "d" or the Roman numeral "iv," use start="4".
### type

    Sets the numbering type:

        a for lowercase letters
        A for uppercase letters

    i for lowercase Roman numerals
    I for uppercase Roman numerals
    1 for numbers (default)

The specified type is used for the entire list unless a different type attribute is used on an enclosed <li> element.</li>

### nesting lists
unordered list inside ordered list
```html
<ol>
  <li>first item</li>
  <li>
    second item
    <!-- closing </li> tag is not here! -->
    <ul>
      <li>second item first subitem</li>
      <li>second item second subitem</li>
      <li>second item third subitem</li>
    </ul>
  </li>
  <!-- Here's the closing </li> tag -->
  <li>third item</li>
</ol>
```