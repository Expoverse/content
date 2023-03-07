---
title: How To Align an HTML List Side by Side
taxonomy:
    category: CSS
post_date: 2021-11-28 01:41:34
---

## Contents

This article demonstrates how to align an HTML list side by side with several methods and walk-throughs to create a horizontal row with [CSS](https://www.w3schools.com/cssref/index.php).

**Contents**

-   [Setting Up a Demonstration](https://appcode.app/how-to-align-an-html-list-side-by-side/#setting-up-a-demonstration)
-   [Methods](https://appcode.app/how-to-align-an-html-list-side-by-side/#methods)
    -   [Using Float Method](https://appcode.app/how-to-align-an-html-list-side-by-side/#using-the-float-method)
    -   [Using Grid Method](https://appcode.app/how-to-align-an-html-list-side-by-side/#using-grid-method)
    -   [Using Flexbox Method](https://appcode.app/how-to-align-an-html-list-side-by-side/#using-flexbox-method)
    -   [Using display: inline Method](https://appcode.app/how-to-align-an-html-list-side-by-side/#using-display-inline-method)
-   [Summary](https://appcode.app/how-to-align-an-html-list-side-by-side/#summary)

## Setting Up a Demonstration {#setting-up-a-demonstration}

Before we go walk-through setting up an example project for demonstrating methods of creating a horizontal list, we should review a frequently asked question that developers may ask when developing a website with list items:

**How do I make a list horizontally in HTML?**

In HTML, `<ul>` and `<ol>` elements are usually rendered vertically, with each list item stacked on top of another. This stacking creates a column, and each list item typically uses the entire width of its container. When you need to create an HTML list that expands horizontally or side-by-side, several methods, such as grid, flex, inline, and float, can achieve this effect.

<figure class="wp-block-image size-large is-resized">
  <img loading="lazy" src="https://appcode.app/wp-content/uploads/2022/11/Diagram-of-an-HTML-List-Transformed-From-Vertical-to-Horizonal.jpg" alt="Diagram of an HTML List Transformed From Vertical to Horizonal" class="wp-image-15424" width="750" height="431" srcset="https://appcode.app/wp-content/uploads/2022/11/Diagram-of-an-HTML-List-Transformed-From-Vertical-to-Horizonal.jpg 943w, https://appcode.app/wp-content/uploads/2022/11/Diagram-of-an-HTML-List-Transformed-From-Vertical-to-Horizonal-300x172.jpg 300w, https://appcode.app/wp-content/uploads/2022/11/Diagram-of-an-HTML-List-Transformed-From-Vertical-to-Horizonal-768x441.jpg 768w" sizes="(max-width: 750px) 100vw, 750px">
  <figcaption>Diagram of an HTML List Transformed From Vertical to Horizonal</figcaption>
</figure>

An [HTML unordered list](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) will naturally display its list item elements vertically, like in both images. The above image contains a vertical purple section, while the bottom photo has a vertical native HTML list.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="265" src="https://appcode.app/wp-content/uploads/2021/11/HTML-Vertical-Unordered-List-1024x265.png" alt="HTML Vertical Unordered List" class="wp-image-6347" srcset="https://appcode.app/wp-content/uploads/2021/11/HTML-Vertical-Unordered-List-1024x265.png 1024w, https://appcode.app/wp-content/uploads/2021/11/HTML-Vertical-Unordered-List-300x78.png 300w, https://appcode.app/wp-content/uploads/2021/11/HTML-Vertical-Unordered-List-768x199.png 768w, https://appcode.app/wp-content/uploads/2021/11/HTML-Vertical-Unordered-List-1536x398.png 1536w, https://appcode.app/wp-content/uploads/2021/11/HTML-Vertical-Unordered-List.png 1920w" sizes="(max-width: 1024px) 100vw, 1024px">
  <figcaption>HTML Vertical Unordered List</figcaption>
</figure>

If we want to change an HTML list direction from vertical (above) to horizontal, we need to understand and learn the various methods to change the layout to flat, as seen in the image below.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="249" src="https://appcode.app/wp-content/uploads/2021/11/HTML-List-Side-by-Side-1024x249.png" alt="HTML List Side by Side" class="wp-image-6334" srcset="https://appcode.app/wp-content/uploads/2021/11/HTML-List-Side-by-Side-1024x249.png 1024w, https://appcode.app/wp-content/uploads/2021/11/HTML-List-Side-by-Side-300x73.png 300w, https://appcode.app/wp-content/uploads/2021/11/HTML-List-Side-by-Side-768x186.png 768w, https://appcode.app/wp-content/uploads/2021/11/HTML-List-Side-by-Side-1536x373.png 1536w, https://appcode.app/wp-content/uploads/2021/11/HTML-List-Side-by-Side.png 1920w" sizes="(max-width: 1024px) 100vw, 1024px">
  <figcaption>HTML List Side by Side</figcaption>
</figure>

Let’s create an example project to demonstrate the different methods of changing the direction of an ordered or unordered list.

We need to create an HTML code snippet that contains an unordered list element `<ul>` and [list item elements](https://www.htmlhelp.com/reference/html40/lists/li.html) `<li>` as the children. Once the list is created, we will wrap the unordered list within a [`<div>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) that contains a class called `.container`. A `<div>` element centers the list on a web page for easy demonstration when iterating over each method.

Here is the HTML code to create our list structure.

```HTML
<div class="container">
  <ul>
    <li>List Item One</li>
    <li>List Item Two</li>
    <li>List Item Three</li>
  </ul>
</div>
```

Now that we have added an HTML structure to a page, we must explain how we target the list elements using CSS selectors and how to remove the list item bullets with properties.

To change a direction of a list, we can target the unordered list element using a `ul` [CSS selector](https://blog.hubspot.com/website/css-selectors).

```CSS
ul {
  /* CSS Properties Here */
}
```

Or we can target a child list elements of the unordered list with the `ul li` selector, which [selects list elements that are only children](https://www.dottedsquirrel.com/the-ultimate-visual-guide-to-css-selectors/) of a parent `ul` element. Which selector we use depends on the method implemented.

```CSS
ul li {
  /* CSS Properties Here */
}
```

We add the [CSS list-style property](https://www.techonthenet.com/css/properties/list_style.php) for visual aid in the demonstration and set the value to none. This effectily removes the bullet circles on the list items. Now we can move on to the various methods to create a horizontal list.

```CSS
ul {
  list-style: none;
}
```

## Methods {#methods}

There are several methods to consider if you want to transform a direction of an unordered or ordered list in HTML. In the following four sections, we will review the different methods using a float, grid, flexbox, and inline.

### Using the Float Method {#using-the-float-method}

We can use a [CSS float property](https://www.javatpoint.com/css-float) to force `li` elements to be horizontal. The float property is a positioning and formatting rule for content layout. We can set a value of `left` for the float property, which floats all the `li` elements left, next to each other. Optionally, a float value can be set to `right`, and all the elements will float to the right.

```CSS
ul li {
  float: left; //or right
}
```

### Using Grid Method {#using-grid-method}

The grid method also achieves making a list horizontal. We can use a CSS `display` with a `grid` value to turn an unordered list into a grid where its list element children are placed into three columns.

```CSS
ul {
  display: grid;
  grid-template-columns: auto auto auto;
  /* Other CSS Properties Here */
}
```

Let’s explain how grid achieves a side-by-side list. A `grid-template-columns` property defines a template column layout of grid. So by giving `grid-template-columns` three auto values since there are three list items, it instructs grid to create three columns that automatically set their width to the width of the contents in each column.

<p class="note-dark"><strong>Note:</strong> In another article, we expand upon using <a href="https://appcode.app/a-guide-on-how-to-use-css-grids-for-layouts/">CSS grid property to create different layouts</a> on a web page. This might be helpful because other properties related to the grid can be applied to HTML lists, such as changing column width, defining gap spacing, sizing rows, and more. You can check out the grid article here. <a href="https://appcode.app/a-guide-on-how-to-use-css-grids-for-layouts/">Direct Link →</a></p>

### Using Flexbox Method {#using-flexbox-method}

Another method to align an unordered or ordered list horizontally would be to use a `display: flex` property on a list container element, `<ol>` or `<ul>`. Flex converts a container into a flexbox, each child element becoming a flex item. These flex item act like a grid which is similar to using CSS grid.

```CSS
ul {
  display: flex;
}
```

<p class="note-dark"><strong>Note:</strong> Two other articles can expand information on using the display flexbox property. The first article demonstrates&nbsp;<a href="https://appcode.app/how-to-create-a-responsive-flexbox-grid/" target="_blank" rel="noreferrer noopener">creating a responsive flexbox grid</a>, which can be implemented into your own horizontal list. In a second article, we turn an&nbsp;<a href="https://appcode.app/css-flexbox-navigation-menus-tutorial-and-examples/" target="_blank" rel="noreferrer noopener">unordered list into a horizontal menu</a>, with each list element containing a link anchor to navigate. This could be useful if you create a menu using HTML lists.&nbsp;<a href="https://appcode.app/css-flexbox-navigation-menus-tutorial-and-examples/" target="_blank" rel="noreferrer noopener">Direct Link →</a></p>

### Using display: inline Method {#using-display-inline-method}

A frequently used method to make a horizontal list is to use a `display: inline` property on the children list elements of a `<ul>` or `<ol>` (unordered or ordered list). By default, a list element is a block element and expands to the entire width of a parent element. When a list element is changed to inline, they no longer act like full-width blocks; instead, they take the smallest height and width possible if not declared, and they float to the left like text.

```CSS
ul li {
  display: inline;
}
```

Each of the `inline-block`, `inline-flex`, `inline-grid`, `inline-table`, `-webkit-inline-box` values also produce the same horizontal effect when set as the value of display.

## Summary {#summary}

<p class="note-dark"><strong>Note:</strong> a unique feature of this project is the background gradient. We used a&nbsp;<a target="_blank" href="https://www.kirupa.com/css/circles_radial_gradient.htm" rel="noreferrer noopener">CSS background radial gradient</a> for the body and a container that wraps the unordered list. The position of a circular gradient is set by using the value <code>circle at 17% 98%</code>. We have an article that dives into conic and radial gradients here. <a href="https://appcode.app/diving-into-conic-and-radial-color-gradients-in-css/">Direct Link →</a></p>

All the CSS styles used in this example to create the whole project are here. You can switch out the CSS properties and use the different methods above.

```HTML
html,
body {
  height: 100%;
  overflow: hidden;
  margin: 0;
  background: radial-gradient(circle at 17% 98%, #29061f, #4b2020);
  color: white;
  font-family: Roboto, arial, sans-serif;
}

ul {
  list-style: none;
  background: #fff;
  padding: 20px 40px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgb(0 0 0 / 50%);
  background: radial-gradient(circle at 17% 98%, #90166c, #ec6969);
  font-size: 20px;
}

ul li {
  float: left;
  margin: 10px;
}

.container {
  -webkit-box-align: center !important;
  -ms-flex-align: center !important;
  align-items: center !important;
  -webkit-box-pack: center !important;
  -ms-flex-pack: center !important;
  justify-content: center !important;
  display: -webkit-box !important;
  display: -ms-flexbox !important;
  display: flex !important;
  height: 100%;
}
```

To tinker with this example, here is a link to the [live demo hosted on codepen.io.](https://codepen.io/tyler-chipman/pen/jOLgReZ)

## Recommended Articles

-   [How To Create a Black and White Image Using CSS Grayscale](https://appcode.app/how-to-create-a-black-and-white-image-using-css-grayscale/)
-   [Quickly Search and Filter a List With JavaScript](https://appcode.app/quickly-search-and-filter-a-list-with-javascript/)
-   [Create a Three Column Layout Using Pure CSS and Background Image](https://appcode.app/create-a-three-column-layout-using-pure-css-and-background-image/)
-   [How To Build Web Layouts for Dual-Screen](https://appcode.app/how-to-build-web-layouts-for-dual-screen/)
