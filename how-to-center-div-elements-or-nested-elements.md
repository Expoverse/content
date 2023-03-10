---
title: How to Center DIV Elements or Nested Elements
taxonomy:
    category: CSS
post_date: 2022-01-07 06:47:12
---

## Contents

-   [Overview](#overview)
-   [Methods for Centering DIVs and Elements](#methods-for-centering-divs-and-elements)
    -   [Using margin Property](#using-margin-property)
    -   [Using flex Property](#using-flex-property)
    -   [Using text-align Property](#using-text-align-property)
    -   [Using transform Property](#using-transform-property)
    -   [Using grid Property](#using-grid-property)
-   [Summary](#summary)
-   [See Also](#see-also)

## Overview

CSS is one of the three core technologies of the World Wide Web, along with HTML and JavaScript. No modern website is complete without CSS because CSS defines the presentation of the user interface.

Though it seems easy, [CSS is quite tough to implement in real-time](https://medium.com/@Cryptacular/why-is-css-so-hard-for-programmers-a10d7e282620). The reason is that CSS is huge and has many concepts. Moreover, every challenge has more than one solution, sometimes several. Even experienced developers sometimes struggle while implementing CSS.

One of the common challenges in CSS is to center an element. If you have ever worked with CSS, you likely faced a situation where a div element or a heading needs to be centered. And many developers struggle in doing this simple task. One of the primary reasons for this is that developers do not give enough time to learn the tricks for centering elements using CSS. So in this article, we will provide different ways of centering a div or centering other elements inside a div using CSS.

## Methods for Centering DIVs and Elements

There are different ways to center a div or center elements inside a div. This can include centering a div on the screen or center elements such as paragraphs, headings, or images inside a div. We can do it horizontally, vertically, or both horizontally or vertically. So let’s discuss each of these ways one by one.

### Using margin Property

One of the easiest ways to center a div horizontally is by [using the margin property](https://www.w3schools.com/css/css_margin.asp). Observe the following div element.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="714" height="158" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/A-simple-green-circle-DIV-element-1024x226.png?resize=1024%2C226&amp;ssl=1" alt="A simple green circle DIV element" class="wp-image-7484" srcset="https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-simple-green-circle-DIV-element.png?resize=1024%2C226&amp;ssl=1 1024w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-simple-green-circle-DIV-element.png?resize=300%2C66&amp;ssl=1 300w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-simple-green-circle-DIV-element.png?resize=768%2C170&amp;ssl=1 768w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-simple-green-circle-DIV-element.png?resize=1536%2C339&amp;ssl=1 1536w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-simple-green-circle-DIV-element.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px">
  <figcaption>A simple green circle DIV element</figcaption>
</figure>

[The green circle is the div element](https://www.freecodecamp.org/news/css-shapes-explained-how-to-draw-a-circle-triangle-and-more-using-pure-css/) and currently, it is not centered. Following is the HTML for the above.

```HTML
<html>
  <body class="body-css">
    <div class="div-css"></div>
  </body>
</html>
```

And following is the CSS.

```CSS
.body-css {
  border: 2px solid black;
  padding: 60px;
}

.div-css {
  width: 200px;
  height: 200px;
  background-color: green;
  border-radius: 50%;
}
```

To center this div horizontally, we can use the margin property and set `auto` as its value.

```CSS
.body-css {
  border: 2px solid black;
  padding: 60px;
}

.div-css {
  width: 200px;
  height: 200px;
  background-color: green;
  border-radius: 50%;

  margin: auto;
}
```

With margin as `auto`, the div will be centered with respect to its parent element, i.e. body.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="226" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-margin-auto.png?resize=1024%2C226&amp;ssl=1" alt="A centered DIV element using margin auto" class="wp-image-7485" srcset="https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-margin-auto.png?resize=1024%2C226&amp;ssl=1 1024w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-margin-auto.png?resize=300%2C66&amp;ssl=1 300w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-margin-auto.png?resize=768%2C170&amp;ssl=1 768w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-margin-auto.png?resize=1536%2C339&amp;ssl=1 1536w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-margin-auto.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>A centered DIV element using margin auto</figcaption>
</figure>

### Using flex Property

[Using flex](https://css-tricks.com/snippets/css/a-guide-to-flexbox/), we can align the div horizontally, vertically, or both. We have to apply the `flex` as the value of the display property in the parent element. Then, we have to use the [`justify-content` and `align-items property`](https://stackoverflow.com/questions/35049262/difference-between-justify-content-vs-align-items) in the parent element as well and both of them should have `center` as their values.

```CSS
.body-css {
  border: 2px solid black;
  padding: 60px;
 
  display: flex;
  justify-content: center;
  align-items: center;
}
.div-css {
  width: 200px;
  height: 200px;
  background-color: green;
  border-radius: 50%;
}
```

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="226" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-CSS-flex.png?resize=1024%2C226&amp;ssl=1" alt="A centered DIV element using CSS flex" class="wp-image-7486" srcset="https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-CSS-flex.png?resize=1024%2C226&amp;ssl=1 1024w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-CSS-flex.png?resize=300%2C66&amp;ssl=1 300w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-CSS-flex.png?resize=768%2C169&amp;ssl=1 768w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-CSS-flex.png?resize=1536%2C338&amp;ssl=1 1536w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-element-using-CSS-flex.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>A centered DIV element using CSS flex</figcaption>
</figure>

This way is also useful when we want to center any element inside a div. Observe the following HTML.

```HTML
<html>
  <body class="body-css">
    <div class="div-css">
      <h3>Hello World!</h3>
    </div>
  </body>
</html>
```

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="227" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-using-CSS-flex-with-uncentered-text.png?resize=1024%2C227&amp;ssl=1" alt="A centered DIV using CSS flex with uncentered text" class="wp-image-7489" srcset="https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-using-CSS-flex-with-uncentered-text.png?resize=1024%2C227&amp;ssl=1 1024w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-using-CSS-flex-with-uncentered-text.png?resize=300%2C67&amp;ssl=1 300w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-using-CSS-flex-with-uncentered-text.png?resize=768%2C170&amp;ssl=1 768w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-using-CSS-flex-with-uncentered-text.png?resize=1536%2C341&amp;ssl=1 1536w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/A-centered-DIV-using-CSS-flex-with-uncentered-text.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>A centered DIV using CSS flex with uncentered text</figcaption>
</figure>

To center the h3 element, we have to apply the flex to its parent element i.e. div. Yes, we have already applied flex to the body element and there is no problem in applying the flex again.

```CSS
.body-css {
  border: 2px solid black;
  padding: 60px;

  display: flex;
  justify-content: center;
  align-items: center;
}

.div-css {
  width: 200px;
  height: 200px;
  background-color: green;
  border-radius: 50%;

  display: flex;
  justify-content: center;
  align-items: center;
}
```

Remember, the justify-content property will center the element horizontally while align-items will center vertically.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="226" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-DIV-and-text-using-CSS-Flex.png?resize=1024%2C226&amp;ssl=1" alt="Centered DIV and text using CSS Flex" class="wp-image-7491" srcset="https://i0.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-DIV-and-text-using-CSS-Flex.png?resize=1024%2C226&amp;ssl=1 1024w, https://i0.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-DIV-and-text-using-CSS-Flex.png?resize=300%2C66&amp;ssl=1 300w, https://i0.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-DIV-and-text-using-CSS-Flex.png?resize=768%2C169&amp;ssl=1 768w, https://i0.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-DIV-and-text-using-CSS-Flex.png?resize=1536%2C338&amp;ssl=1 1536w, https://i0.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-DIV-and-text-using-CSS-Flex.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>Centered DIV and text using CSS Flex</figcaption>
</figure>

### Using text-align Property

[Using text-align property](https://www.geeksforgeeks.org/css-text-align-property/) is the most common way to center a text. In the above example, we centered the h3 element inside the div using the flex, which was also used to center the div itself. Instead of using flex to center the h3 element, let’s try the text-align property.

```CSS
.body-css {
  border: 2px solid black;
  padding: 60px;

  display: flex;
  justify-content: center;
  align-items: center;
}

.div-css {
  width: 200px;
  height: 200px;
  background-color: green;
  border-radius: 50%;

  text-align: center;
}
```

But there is one problem. The `text-align` property will only center the element horizontally. 

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="225" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-text-using-the-text-align-property.png?resize=1024%2C225&amp;ssl=1" alt="Centered text using the text-align property" class="wp-image-7493" srcset="https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-text-using-the-text-align-property.png?resize=1024%2C225&amp;ssl=1 1024w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-text-using-the-text-align-property.png?resize=300%2C66&amp;ssl=1 300w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-text-using-the-text-align-property.png?resize=768%2C169&amp;ssl=1 768w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-text-using-the-text-align-property.png?resize=1536%2C338&amp;ssl=1 1536w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centered-text-using-the-text-align-property.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>Centered text using the text-align property</figcaption>
</figure>

So, we can use the `text-align` property, if it is required to center the text horizontally only.

### Using transform Property

Another way to center an element to its nearest parent element is by using the [transform property](https://www.w3schools.com/cssref/css3_pr_transform.asp). In this technique, we give the parent a `relative` position and `absolute` to the child. Then, we provide top, left, and transform properties to the child element with necessary values.

```CSS
.body-css {
  border: 2px solid black;
  padding: 120px;
  position: relative;
}

.div-css {
  width: 200px;
  height: 200px;
  background-color: green;
  border-radius: 50%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

Remember, the top and left property values should always be `50%` while `translate` should be used for the transform property.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="173" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Using-the-transform-property-to-center-a-DIV-element-1024x173.png?resize=1024%2C173&amp;ssl=1" alt="Using the transform property to center a DIV element" class="wp-image-7494" srcset="https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/Using-the-transform-property-to-center-a-DIV-element.png?resize=1024%2C173&amp;ssl=1 1024w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/Using-the-transform-property-to-center-a-DIV-element.png?resize=300%2C51&amp;ssl=1 300w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/Using-the-transform-property-to-center-a-DIV-element.png?resize=768%2C130&amp;ssl=1 768w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/Using-the-transform-property-to-center-a-DIV-element.png?resize=1536%2C259&amp;ssl=1 1536w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/Using-the-transform-property-to-center-a-DIV-element.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>Using the transform property to center a DIV element</figcaption>
</figure>

### Using grid Property

[The grid system is relatively new](https://learncssgrid.com/), and you can use it to center elements in CSS. In this technique, we have to set `grid` as the value of display in the parent element and define rows and columns. Then, we can use `justify-self` and `align-self` properties in the child element and set their values as `center`.

```CSS
.body-css {
  border: 2px solid black;

  display: grid;
  grid-template-rows: 80vh;
  grid-template-columns: 100vw;
}

.div-css {
  width: 200px;
  height: 200px;
  background-color: green;
  border-radius: 50%;

  justify-self: center;
  align-self: center;
}
```

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="164" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-a-DIV-element-using-CSS-Grid.png?resize=1024%2C164&amp;ssl=1" alt="Centering a DIV element using CSS Grid" class="wp-image-7499" srcset="https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-a-DIV-element-using-CSS-Grid.png?resize=1024%2C164&amp;ssl=1 1024w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-a-DIV-element-using-CSS-Grid.png?resize=300%2C48&amp;ssl=1 300w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-a-DIV-element-using-CSS-Grid.png?resize=768%2C123&amp;ssl=1 768w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-a-DIV-element-using-CSS-Grid.png?resize=1536%2C246&amp;ssl=1 1536w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-a-DIV-element-using-CSS-Grid.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>Centering a DIV element using CSS Grid</figcaption>
</figure>

## Summary

So centering elements using CSS is not challenging, and you only need to have the correct understanding of specific CSS properties and their values. In this article, we discussed five ways to center a div or center other elements in a div both horizontally and vertically.

Here is a link to a relatively more [advanced example of a centered nested DIV element on codepen.io](https://codepen.io/tyler-chipman/pen/XWeYPVM).

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="263" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-DIV-Elements-or-Nested-Elements-1024x263.png?resize=1024%2C263&amp;ssl=1" alt="Centering DIV Elements or Nested Elements" class="wp-image-7511" srcset="https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-DIV-Elements-or-Nested-Elements.png?resize=1024%2C263&amp;ssl=1 1024w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-DIV-Elements-or-Nested-Elements.png?resize=300%2C77&amp;ssl=1 300w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-DIV-Elements-or-Nested-Elements.png?resize=768%2C197&amp;ssl=1 768w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-DIV-Elements-or-Nested-Elements.png?resize=1536%2C394&amp;ssl=1 1536w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/01/Centering-DIV-Elements-or-Nested-Elements.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>Centering DIV Elements or Nested Elements</figcaption>
</figure>

## See Also

-   [How to Create a Responsive Flexbox Grid](/how-to-create-a-responsive-flexbox-grid/)
-   [The CSS transform Property](/css-transform-property/)
-   [A Guide on How To Use CSS Grids for Layouts](/a-guide-on-how-to-use-css-grids-for-layouts/)
-   [How To Align an HTML List Side by Side](/how-to-align-an-html-list-side-by-side/)
