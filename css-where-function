---
title: CSS :where() Function
taxonomy:
    category: CSS
post_date: 2022-10-16 00:40:52
---

This article demonstrates how to use the CSS `:where()` function within CSS style sheets. Included are code, definitions, and examples.

## Contents

## What is CSS :where()?

The `:where()` function is a functional pseudo-class that takes a list of selectors as its argument and applies the styles to the selected HTML elements in the list.

It allows developers to specify conditions that must be met before a particular style is applied to an element. The syntax for the `where()` function is as follows:

```CSS
selector where(condition) {
  /* Styles to apply */
}
```

In this syntax, the `selector` is any valid CSS selector, and `condition` is a boolean expression that must be true for the styles to be applied. If the condition is `false`, the styles will be ignored.

## Syntax

```CSS
:where( <complex-selector-list> )
```

The `:where()` function parameter is a `<complex-selector-list>` data type and should be replaced with an example value such as: `:where(:not(:hover))`.

## Examples

The examples below use selectors and selector list values for the parameter of the `:where()` function.

```CSS
:where(:not(:hover))
:where(ol, ul, menu:unsupported)
:where(section, aside, footer) a
:where(header, main, footer) a:hover
:where(header, footer) > p
:where(button, a)
:where(.light-theme, .bright-theme)
:where(ol[class])
:where(:valid, :unsupported)
:where(#section) h2
```

For example, suppose we want to apply a different background color to paragraphs that contain the word "important". We could use the following CSS:

```CSS
p where(:contains("important")) {
  background-color: yellow;
}
```

In this CSS, the `where()` function is used to apply the `background-color` property only to paragraphs that contain the word "important". The `:contains()` pseudo-class is used to match any element that contains the specified text.

## Usage
You can apply the `:where()` function to any element by using CSS selectors and adding styles.

```CSS
:where(ol, ul) :where(ol, ul) ol {
    list-style-type: lower-greek;
    color: green;
}

:where(section) a:hover {
  color: blue;
  text-decoration: underline;
}

article :where(footer, aside) > p {
  color: orange;
}

:where(button, a) {
  color: purple;
}

main :where(h1, h2, h3) {
  color: orange;
}
```

## Use Cases of :where()

- **Overriding Styles** – `:where()` is helpful for creating filters in a selector while keeping associate selectors easy to override.
- **Shorting Selector Lists** – `:where()` can shorten CSS style selectors by reducing redundancy and is very useful in shortening CSS code.

```CSS
header a:hover,
main a:hover,
aside:hover,
footer a:hover {
  color: blue;
  text-decoration: underline;
}
```

The above CSS selectors can be reduced by using the `:where()` function because the selectors can be turned into a list. The example below reduced the characters from **100** to **89**, an 11% reduction.

```CSS
:where(header, main, aside, footer) a:hover {
  color: blue;
  text-decoration: underline;
}
```

Using the `:where()` function gives us the advantage of creating shorter and more readily understandable lists.

## Specificity

CSS `:where()` function is similar to :is() syntax and functionality. However, the difference between `:is()` and `:where()` is that :where() is their specificity.

The CSS `:where()` function always has a specificity of zero. This means that the `:where()` pseudo-class or its argument list does not contribute to the specificity of the selector.

An example of specificity failing.

```CSS
a:not(:hover) {
  text-decoration: none;
  color: blue;
}

nav a {
  /* Has no effect */
  text-decoration: underline;
  color: orange;
}
```

However, by using `:where()` you can explicitly declare selector intent:

```CSS
a:where(:not(:hover)) {
  text-decoration: none;

  color: blue;
}

nav a {
  /* Works now! */
  text-decoration: underline;

  color: orange;
}
```

## Forgiving Selectors Lists

The `:where()` function is forgiving in that each selector within the comma-separated list `:where(x, y, z)` is ignored if it is an invalid selector. With `:where()` being forgiving, this means invalid selectors within the pseudo-class don’t disable the entire selector like they normally do.

Syntactically the comma list is a [<forgiving-selector-list>](https://www.w3.org/TR/selectors-4/#forgiving-selector) data value which is equivalent to `<any-value>?` The browser then parses the forgiving selector list into valid selectors to obtain its actual value.

Below, the `totally:fake` selector is ignored while the heading selector isn’t.

```CSS
:where(<forgiving-selector-list> | <any-value>?) {
  /* Some element */
}

/* Invalid "totally:fake is ignored */
:where(heading, totally:fake) {
  /* will still select heading */
}
```

## Refactoring Using :where()

When using `:where()`, we can place it at the beginning, middle, or end of a selector. This allows us to use the function to combine selectors in different ways.

Here is an example of multiple styles and selectors.

```CSS
/* first list */
header a:hover,
section: a:hover,
main a:hover,
footer a:hover {
  color: green;
  text-decoration: underline;
}

/* second list */
article header > p,
article section > p,
article footer > p {
  color: blue;
}

/* third list */
.light-theme button,
.light-theme a {
  color: black;
}

```

In the first CSS style block, we set the `green` and `underline` values to be applied to the `header`, `section`, `main`, and `footer` elements whenever the link element is hovered.

In the second list, we specify that the article’s `header`, `section`, and `foote` paragraph elements should be styled with `blue` text. 

The last list uses the `.light-theme` class to apply styles to the link and button elements. The class contains properties to set the text color to `black` for those elements.

Now we can use the `:where()` function to reduce the CSS.

```CSS
/* first list */
/* at the beginning */
:where(header, section, main, footer) a:hover {
  color: green;
  text-decoration: underline;
}

/* second list */
/* in the middle */
article :where(header, section, footer) > p {
  color: blue;
}

/* third list */
/* at the end */
.light-theme :where(button, a) {
  color: black;
}
```

We replaced each selector group with a `:where()` function. This resulted in fewer selectors, as the selector’s redundant parts were removed.

## Using :where() To Target Elements

Using another example, we can use the `:where()` function to target different links within HTML elements such as the header, sections, and footers.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="319" src="https://appcode.app/wp-content/uploads/2022/10/Targeting-Link-Elements-With-CSS-where-1024x319.png" alt="Targeting Link Elements With CSS where()" class="wp-image-14992" srcset="https://appcode.app/wp-content/uploads/2022/10/Targeting-Link-Elements-With-CSS-where-1024x319.png 1024w, https://appcode.app/wp-content/uploads/2022/10/Targeting-Link-Elements-With-CSS-where-300x94.png 300w, https://appcode.app/wp-content/uploads/2022/10/Targeting-Link-Elements-With-CSS-where-768x240.png 768w, https://appcode.app/wp-content/uploads/2022/10/Targeting-Link-Elements-With-CSS-where-1536x479.png 1536w, https://appcode.app/wp-content/uploads/2022/10/Targeting-Link-Elements-With-CSS-where.png 1641w" sizes="(max-width: 1024px) 100vw, 1024px">
  <figcaption>Targeting Link Elements With CSS where()</figcaption>
</figure>

```HTML
<article>
  <h2>:where()-styled links</h2>
  <header class="where-styling">
    <p>
      Here is my header content. This
      <a href="https://appcode.app">contains a link</a>.
    </p>
  </header>

  <section class="where-styling">
    <p>
      Here is my section content. This
      <a href="https://appcode.app">also contains a link</a>.
    </p>
  </section>

  <aside class="where-styling">
    <p>
      Here is my aside content. This
      <a href="https://appcode.app">also contains another link</a>.
    </p>
  </aside>

  <footer class="where-styling">
    <p>
      This is my footer, also containing
      <a href="https://appcode.app">a link</a>.
    </p>
  </footer>
</article>
```

```CSS
html {
  font-family: sans-serif;
  font-size: 150%;
  text-align: center;
  height: 100%;
  margin: 0;
  -webkit-box-align: center !important;
  -ms-flex-align: center !important;
  align-items: center !important;
  -webkit-box-pack: center !important;
  -ms-flex-pack: center !important;
  justify-content: center !important;
  display: -webkit-box !important;
  display: -ms-flexbox !important;
  display: flex !important;
}

:where(header.where-styling) a {
  color: blue;
}

:where(section.where-styling) a {
  color: green;
}

:where(aside.where-styling, footer.where-styling) a {
  color: orange;
}
```

The last CSS selector uses a `:where()` to override the last link element color from its default orange.

## Try It

Below, we show how to use the `:where()` function to style and target different levels of unordered and ordered lists by supplying selectors in the parameter `:where()`.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="360" src="https://appcode.app/wp-content/uploads/2022/10/Using-The-CSS-where-Function-1024x360.png" alt="Using The CSS where() Function" class="wp-image-14988" srcset="https://appcode.app/wp-content/uploads/2022/10/Using-The-CSS-where-Function-1024x360.png 1024w, https://appcode.app/wp-content/uploads/2022/10/Using-The-CSS-where-Function-300x106.png 300w, https://appcode.app/wp-content/uploads/2022/10/Using-The-CSS-where-Function-768x270.png 768w, https://appcode.app/wp-content/uploads/2022/10/Using-The-CSS-where-Function.png 1392w" sizes="(max-width: 1024px) 100vw, 1024px">
  <figcaption>Using The CSS where() Function</figcaption>
</figure>

```HTML
<ol>
  <li>Shapes</li>
  <ul>
    <li>Square</li>
    <li>
      <ul>
        <li>Color</li>
        <li>Size</li>
        <li>
          <ol>
            <li>X</li>
            <li>Y</li>
            <li>Z</li>
          </ol>
        </li>
        <li>Weight</li>
      </ul>
    </li>
    <li>Circle</li>
    <li>
      <ol>
        <li>Color</li>
        <li>Weight</li>
      </ol>
    </li>
  </ul>
</ol>
```

```CSS
html,
body {
  height: 100%;
  margin: 0;
  -webkit-box-align: center !important;
  -ms-flex-align: center !important;
  align-items: center !important;
  -webkit-box-pack: center !important;
  -ms-flex-pack: center !important;
  justify-content: center !important;
  display: -webkit-box !important;
  display: -ms-flexbox !important;
  display: flex !important;
  font-size: 18px;
}

ol {
  list-style-type: number;
  color: darkblue;
}

/* Not applied to ol, because of lower specificity */
:where(ol, ul, menu:unsupported) :where(ol, ul) {
  color: green;
}

:where(ol, ul ul) :where(ol, ul ul) ol {
  list-style-type: lower-greek;
  color: brown;
}

:where(ol, ul ul) :where(ol, ul ul) {
  list-style-type: lower-alpha;
  color: #871f78;
}
```

## Specifications

[W3C CSS Selectors Level 4
#zero-matches](https://www.w3.org/TR/selectors-4/#zero-matches)

## See Also
- [How To Remove Unused CSS](https://appcode.app/how-to-remove-unused-css/)













