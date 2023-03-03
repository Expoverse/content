---
title: How To Remove the Calendar on HTML Input Type Date
taxonomy:
    category: CSS
post_date: 2021-11-23 01:17:22 
---

This tutorial demonstrates how to remove the calendar on the [HTML input type date](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date). Included is a walkthrough example, code, and a live demo.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="278" src="https://appcode.app/wp-content/uploads/2021/11/Remove-Arrows-on-HTML-Input-Type-Date-1024x278.png" alt="Remove Arrows on HTML Input Type Date" class="wp-image-6295" srcset="https://appcode.app/wp-content/uploads/2021/11/Remove-Arrows-on-HTML-Input-Type-Date-1024x278.png 1024w, https://appcode.app/wp-content/uploads/2021/11/Remove-Arrows-on-HTML-Input-Type-Date-300x81.png 300w, https://appcode.app/wp-content/uploads/2021/11/Remove-Arrows-on-HTML-Input-Type-Date-768x208.png 768w, https://appcode.app/wp-content/uploads/2021/11/Remove-Arrows-on-HTML-Input-Type-Date-1536x417.png 1536w, https://appcode.app/wp-content/uploads/2021/11/Remove-Arrows-on-HTML-Input-Type-Date.png 1920w" sizes="(max-width: 1024px) 100vw, 1024px">
  <figcaption>Remove Arrows on HTML Input Type Date</figcaption>
</figure>

## How To Remove the Icon From a Date Input?
A calendar icon on an HTML input type date **(input[type=”date”])** can be removed using CSS selectors and properties that target the input element calendar-picker-indicator. When removing a calendar icon, we need to use a **::-webkit-calendar-picker-indicator** pseudo-element, as the calendar icon cannot be selected using standard CSS selectors.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="845" height="447" src="https://appcode.app/wp-content/uploads/2022/11/Diagram-of-Hiding-the-Calendar-Icon-on-an-Input-Type-Date.jpg" alt="Diagram of Hiding the Calendar Icon on an Input Type Date" class="wp-image-15370" srcset="https://appcode.app/wp-content/uploads/2022/11/Diagram-of-Hiding-the-Calendar-Icon-on-an-Input-Type-Date.jpg 845w, https://appcode.app/wp-content/uploads/2022/11/Diagram-of-Hiding-the-Calendar-Icon-on-an-Input-Type-Date-300x159.jpg 300w, https://appcode.app/wp-content/uploads/2022/11/Diagram-of-Hiding-the-Calendar-Icon-on-an-Input-Type-Date-768x406.jpg 768w" sizes="(max-width: 845px) 100vw, 845px">
  <figcaption>Diagram of Hiding the Calendar Icon on an Input Type Date</figcaption>
</figure>

## Creating an Input Type Date
This section creates a styled date picker before we move on to removing the icon. This helps to spice up the example to be more visually helpful, so adding the extra HTML and CSS isn’t necessary, but it helps with the demonstration.

To begin creating a webpage with an input type date, we need to create two [div elements](https://www.htmlquick.com/reference/tags/div.html) to move the input element to the center of a web page. First, we will create a div element and a second div as a child. Once we have both div elements, we can create an [HTML input element](https://www.w3schools.com/tags/tag_input.asp) with a type attribute set to date. Something like this: `DIV > DIV > INPUT`. The first DIV element will have a class named `.super-container`, and the second will be `.container`. As you see below, the [HTML code fits](https://www.quackit.com/html/codes/) on a few lines.

```HTML
<div class="super-container">
  <div class="container">
    <input type="date">
  </div>
<div>
```

Rendering this HTML will create a generic HTML date picker element like the one below but without any CSS styling.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="388" src="https://appcode.app/wp-content/uploads/2022/11/Input-Type-Date-Without-Custom-CSS-Styles-1024x388.jpg" alt="Input Type Date Without Custom CSS Styles" class="wp-image-15372" srcset="https://appcode.app/wp-content/uploads/2022/11/Input-Type-Date-Without-Custom-CSS-Styles-1024x388.jpg 1024w, https://appcode.app/wp-content/uploads/2022/11/Input-Type-Date-Without-Custom-CSS-Styles-300x114.jpg 300w, https://appcode.app/wp-content/uploads/2022/11/Input-Type-Date-Without-Custom-CSS-Styles-768x291.jpg 768w, https://appcode.app/wp-content/uploads/2022/11/Input-Type-Date-Without-Custom-CSS-Styles.jpg 1208w" sizes="(max-width: 1024px) 100vw, 1024px">
  <figcaption>Input Type Date Without Custom CSS Styles</figcaption>
</figure>

Suppose we made the date selector a bit more interesting before we removed the calendar icon. In that case, we could render an input element with custom styling, as in the image below.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="339" src="https://appcode.app/wp-content/uploads/2022/11/A-Custom-Styled-HTML-Input-Type-Date-1024x339.jpg" alt="A Custom Styled HTML Input Type Date" class="wp-image-15373" srcset="https://appcode.app/wp-content/uploads/2022/11/A-Custom-Styled-HTML-Input-Type-Date-1024x339.jpg 1024w, https://appcode.app/wp-content/uploads/2022/11/A-Custom-Styled-HTML-Input-Type-Date-300x99.jpg 300w, https://appcode.app/wp-content/uploads/2022/11/A-Custom-Styled-HTML-Input-Type-Date-768x254.jpg 768w, https://appcode.app/wp-content/uploads/2022/11/A-Custom-Styled-HTML-Input-Type-Date-1536x508.jpg 1536w, https://appcode.app/wp-content/uploads/2022/11/A-Custom-Styled-HTML-Input-Type-Date.jpg 1920w" sizes="(max-width: 1024px) 100vw, 1024px">
  <figcaption>A Custom Styled HTML Input Type Date</figcaption>
</figure>

Here is the CSS for a styled date input before we move on to removing the calendar icon.

```CSS
html,
body {
  height: 100%;
  overflow: hidden;
  margin: 0;
}

.super-container {
  background: linear-gradient(60deg, rgb(39 28 86) 0%, rgb(0 85 96) 100%);
  height: 100%;
  width: 100%;
}

input[type="date"]::-webkit-inner-spin-button,
input[type="date"]::-webkit-calendar-picker-indicator {
  filter: invert(1);
}

input {
  background: linear-gradient(
    60deg,
    rgba(84, 58, 183, 1) 0%,
    rgba(0, 172, 193, 1) 100%
  );
  border-radius: 10px;
  border: none;
  line-height: 80px;
  width: 400px;
  padding: 0 20px;
  box-shadow: 0 4px 8px rgb(0 0 0 / 50%);
  outline: none;
  color: white;
  font-size: 22px;
}

input::placeholder {
  color: white;
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

## Removing the Calendar Icon
This section will remove a calendar icon using CSS styles and properties.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="798" height="193" src="https://appcode.app/wp-content/uploads/2021/11/Creating-a-Generic-HTML-Date-Picker-Element.png" alt="Creating a Generic HTML Date Picker Element" class="wp-image-6300" srcset="https://appcode.app/wp-content/uploads/2021/11/Creating-a-Generic-HTML-Date-Picker-Element.png 798w, https://appcode.app/wp-content/uploads/2021/11/Creating-a-Generic-HTML-Date-Picker-Element-300x73.png 300w, https://appcode.app/wp-content/uploads/2021/11/Creating-a-Generic-HTML-Date-Picker-Element-768x186.png 768w" sizes="(max-width: 798px) 100vw, 798px">
  <figcaption>Creating a Generic HTML Date Picker Element</figcaption>
</figure>

We need to remove the calendar icon from the input element above. Below is an image of the input element with the calendar icon removed. To make the icon disappear, we need to utilize a few CSS properties and a unique selector, which is required to achieve this effect.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="928" height="175" src="https://appcode.app/wp-content/uploads/2021/11/Remove-Calendar-From-HTML-Date-Picker.png" alt="Remove Calendar From HTML Date Picker" class="wp-image-6309" srcset="https://appcode.app/wp-content/uploads/2021/11/Remove-Calendar-From-HTML-Date-Picker.png 928w, https://appcode.app/wp-content/uploads/2021/11/Remove-Calendar-From-HTML-Date-Picker-300x57.png 300w, https://appcode.app/wp-content/uploads/2021/11/Remove-Calendar-From-HTML-Date-Picker-768x145.png 768w" sizes="(max-width: 928px) 100vw, 928px">
  <figcaption>Remove Calendar From HTML Date Picker</figcaption>
</figure>

Removing an icon is simple; we will use two WebKit pseudo-element keywords with the CSS display and WebKit Appearance properties. The CSS pseudo-elements we are using are -webkit-inner-spin-button and -webkit-calender-picker-indicator. We combine these keywords with the CSS input[type="date"] selector, targeting the date picker element.

Included within the braces, we use the CSS properties display and -webkit-appearance. Both of these properties will have a value set to none.

Below are the full CSS selector and properties to remove a date picker calendar icon.

```CSS
input[type="date"]::-webkit-inner-spin-button,
input[type="date"]::-webkit-calendar-picker-indicator {
    display: none;
    -webkit-appearance: none;
}
```

## Project Code
Here are the entire CSS stylesheet and HTML used in this project.

```HTML
<div class="super-container">
  <div class="container">
    <input type="date">
  </div>
<div>
```

```CSS
html,
body {
  height: 100%;
  overflow: hidden;
  margin: 0;
}

.super-container {
  background: linear-gradient(60deg, rgb(39 28 86) 0%, rgb(0 85 96) 100%);
  height: 100%;
  width: 100%;
}

input[type="date"]::-webkit-inner-spin-button,
input[type="date"]::-webkit-calendar-picker-indicator {
  display: none;
  -webkit-appearance: none;
}

input {
  background: linear-gradient(
    60deg,
    rgba(84, 58, 183, 1) 0%,
    rgba(0, 172, 193, 1) 100%
  );
  border-radius: 10px;
  border: none;
  line-height: 80px;
  width: 400px;
  padding: 0 20px;
  box-shadow: 0 4px 8px rgb(0 0 0 / 50%);
  outline: none;
  color: white;
  font-size: 22px;
}

input::placeholder {
  color: white;
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

Here is a live demo of this example hosted on codepen.io

## Recommended Articles
- [How to Create CSS Color Palettes](https://appcode.app/how-to-create-css-color-palettes/)
- [How To Remove the Arrows on HTML Input Type Number](https://appcode.app/how-to-remove-the-arrows-on-html-input-type-number/)
- [How To Create HTML and CSS Emoji Icons](https://appcode.app/how-to-create-html-and-css-emoji-icons/)
- [How To Create CSS Gradient Buttons](https://appcode.app/how-to-create-css-gradient-buttons/)
- [How To Create a Black and White Image Using CSS Grayscale](https://appcode.app/how-to-create-a-black-and-white-image-using-css-grayscale/)



