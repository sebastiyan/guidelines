# Introduction
- keep stylesheets maintainable;
- keep code transparent, sane, and readable;
- keep stylesheets scalable.

# General Formatting Rules
### Indentation
Use **soft tabs with two spaces** — they're the only way to guarantee code renders the same in any environment. Don’t use tabs or mix tabs and spaces for indentation.

### Capitalization
All code has to be lowercase: This applies to HTML element names, attributes, attribute values (unless text/CDATA), CSS selectors, properties, and property values (with the exception of strings).
```
color: #e5e5e5;
```
```
<img src="rails-reactor.png" alt="Rails Reactor logo">
```

### Images
- Photos have to be in **.jpg**
- Icons, vector elements - **.svg**
- Other - **.png**

# HTML
### Syntax
- always use double quotes, never single quotes, on attributes;
- paragraphs of text should always be placed in a `<p>` tag. Never use multiple `<br>` tags;
- don't include a trailing slash in self-closing elements—the HTML5 spec says they're optional;
- don't omit optional closing tags (e.g. `</li>` or `</body>`).

### Lean Markup
Whenever possible, avoid superfluous parent elements when writing HTML. Many times this requires iteration and refactoring, but produces less HTML. For example:
```
<!-- Not so great -->
<span class="avatar">
  <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
```

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
- Name your classes with a logical structure. The solution is to use BEM css methodology for naming classes. http://getbem.com/introduction/


# CSS

### Reset.css or Normalize.css
Resets essentially eliminate browser inconsistencies such as heights, font sizes, margins, headings, etc. The reset allows your layout look consistent in **all browsers**.

### Divide and Conquer your code
Organization within the stylesheets is very important, too – the naming system, styles, and specificity of your components should be consistent across your entire project. They should also be organized in a way that mitigates conflicts and prevents leaked styles between selectors.

### Formating
- use hex color codes `#000` unless using `rgba()` in raw CSS (SCSS' `rgba()` function is overloaded to accept hex colors as a param, e.g., `rgba(#000, .5)`);
- use `//` for comment blocks (instead of `/* */`);
```
<!-- Not so great -->
/*
$blue: #6bc7dd
$dark-blue: #0f5364
*/

<!-- Better -->
// $blue: #6bc7dd
// $dark-blue: #0f5364
```
- where allowed, avoid specifying units for zero-values, e.g., `margin: 0`;
```
.foo {
  margin: 0;
  border: 0;
  padding: 0;
  border-radius: 0;
  font-size: 0;
}
```

### Define your Colors and Typography
```
$blue: #6bc7dd;
$dark-blue: #0f5364;
$light-blue: #6fd6e4;
```

### Use Shorthand
You can shrink your code considerably by using shorthand when crafting your CSS. For elements like **padding, margin, font and some others**, you can combine styles in one line. 
```
<!-- Not so great -->
.btn {
  margin-left: 5px;
  margin-right: 7px;
  margin-top: 8px;
}
<!-- Better -->
.btn {
  margin: 8px 7px 0 5px;
}
```

### Avoid Extra Selectors
```
<!-- Very bad -->
body .home-page .form .btn.submit-form {...}

<!-- Better -->
.form .btn.submit-form{...}

<!-- The BEST -->
.btn {
  ...
  &--submit{...}
}
```

### Box-sizing
Reset **box-sizing** to **border-box** for every element. This allows us to more easily assign widths to elements that also have padding and borders.
```
* {
  box-sizing: border-box;
}
```

### Clearfix
Instead of **.clear** it better to use **clearfix mixin**.
```
@mixin clearfix {
  &:after {
    content: "";
    display: table;
    clear: both;
  }
}
```
Then include it wherever necessary:
```
.wrap {
  ...
  @include clearfix;
}
```

# Links
- https://google.github.io/styleguide/htmlcssguide.xml
- https://www.smashingmagazine.com/2008/05/improving-code-readability-with-css-styleguides/
- http://primercss.io/guidelines/
- http://getbem.com/introduction/
- http://brettjankord.com/2013/03/06/more-thoughts-on-html-class-naming-conventions/
- https://www.sitepoint.com/title-css-simple-approach-css-class-naming/
