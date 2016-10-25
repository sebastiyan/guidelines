# Introduction
- keep stylesheets maintainable;
- keep code transparent, sane, and readable;
- keep stylesheets scalable.


# HTML
### Syntax
- Use soft tabs with two spaces—they're the only way to guarantee code renders the same in any environment.
- Nested elements should be indented once (two spaces).
- Always use double quotes, never single quotes, on attributes.
- Paragraphs of text should always be placed in a <p> tag. Never use multiple <br> tags.
- Don't include a trailing slash in self-closing elements—the HTML5 spec says they're optional.
- Don’t omit optional closing tags (e.g. </li> or </body>).


### Boolean
Many attributes don’t require a value to be set, like disabled or checked, so don’t set them.
```
<input type="text" required>
```

### Names & Capitalization
- ID names should be in lowerCamelCase
```
#pageContainer {
```
- Class names should be in lowercase. If you don't use BEM-CSS methodology, dont't use underscores in class names (_)
```
.my-class-name {
```
- HTML elements should be in lowercase
- 


# CSS

### Reset.css or Normalize.css

### Divide and conquer your code

### Define your colors and typography
```
$blue: #6bc7dd;
$dark-blue: #0f5364;
$light-blue: #6fd6e4;
```

### Whitespace
Never mix spaces and tabs for indentation
Use soft tabs with two spaces

### Box-sizing
We reset box-sizing to border-box for every element. This allows us to more easily assign widths to elements that also have padding and borders.
```
* {
    box-sizing: border-box;
}
```

Where allowed, avoid specifying units for zero-values, e.g., margin: 0.
```
.foo {
    margin: 0;
    border: 0;
    padding: 0;
    border-radius: 0;
    font-size: 0;
}
```

# Links
- https://google.github.io/styleguide/htmlcssguide.xml
- https://www.smashingmagazine.com/2008/05/improving-code-readability-with-css-styleguides/
- http://primercss.io/guidelines/
- http://getbem.com/introduction/
- http://brettjankord.com/2013/03/06/more-thoughts-on-html-class-naming-conventions/
- https://www.sitepoint.com/title-css-simple-approach-css-class-naming/
