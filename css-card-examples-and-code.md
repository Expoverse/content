---
title: CSS Cards
taxonomy:
    category: CSS
---

This article demonstrates CSS card designs, definitions, walk-throughs, code examples, FAQs, and other card-related developer information.

You must be familiar with CSS to make your website look appealing. CSS (also referred to as Cascading Style Sheets) is a style sheet language for styling web content. Cards are often used in modern web design.

The cards appear sleek and similar to the Android Material design. Using the box-shadow property, we can generate both Text and Picture cards.

These cards can display article excerpts, with an image on top and the article title at the bottom, user profiles, or anything else. Picture cards can be used for several different things. This lesson will teach CSS fundamentals by creating card components from scratch. Let’s get started if you’re ready.

## What is a Card?
## Parts of a Card
## How are Cards Used?
## Example 1

We need some content to work with before we begin working with CSS. In this step, we will start by creating the HTML markups. If you are unfamiliar with HTML, you can start with some of our HTML tutorials.

```HTML
<!-- A div with container id to hold the card -->
<div id="container">
  <!-- A div with card class for the card  -->
  <div class="card">
    <img src="https://images.unsplash.com/photo-1672357867403-0b36f4334de7?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80">
    <!-- A div with card__details class to hold the details in the card  -->
    <div class="card__details">
      <!-- Span with tag class for the tag -->
      <span class="tag">When nature calls</span>
      <span class="tag">By Unsplash</span>
      <!-- A div with name class for the name of the card -->
      <div class="name">Jim Carrey</div>
      <p>
        Pride is an abomination. One must forego the self to obtain total spiritual creaminess and avoid the chewy chunks of degradation.
      </p>
      <button>Read more</button>
    </div>
  </div>
</div>
```

If you are coding externally, you must wrap these lines of code in the basic HTML markups. This means you ought to start by creating something like this:

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Creating Cards using CSS</title>
    </head>
    <body>
    <!-- Website Content Here -->
    </body>
</html>
```

Alright, with the HMTL elements out of the way, let’s see what we’ve achieved so far with the lines of codes we’ve created thus far:

```HTML
Image Placeholder
```

It doesn’t look like much, but that’s because we are yet to style it. However, what we’ve done here with HTML is to create the “skeleton” or “frame” for our design. With this, styling can exist. But it’s like trying to place a fleshy one in thin air – nothing will hold it!

Remember, our task is to create a card component with an image, tags, a name, a description, and a button.

The component must then be styled. This is the tutorial’s central point. This section will explain several concepts as I create the card component.

### CSS Recap – CSS Application in HTML
First, let’s look at three approaches to adding CSS to HTML. These approaches are:

External stylesheets
The most popular and useful method is to use an external stylesheet. CSS is contained in a separate file with the extension.css.
Create a new file, style.css, in the same folder as index.html to add an external stylesheet. You may also import the stylesheet within the element by doing this:

```HTML
<link rel="stylesheet" href="style.css">
```

Internal stylesheets
You can include an internal stylesheet by putting CSS in the

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Creating Cards using CSS</title>

  <style>
    /* your style */
  </style>

</head>
<body>
  
</body>
</html>
```

Inline styles (Not recommended)
You should avoid this style as much as you can. However, the style attribute can also add style directly to an element.

This method is frequently used when working with lines of code that do not allow you to alter the external or internal stylesheets.

Adding inline styling to your page is not a good practice. Why? That’s because it makes it tough to read and understand; therefore, avoid it wherever possible.

```HTML
<div style="color:red;">paragraph</div>
```

Styling the HTML elements
With this out of the way, let’s go back to our tutorial and style it using CSS.

```CSS
body {
  background-color: #eaeff1;
  font-family: sans-serif;
}

#container {
  max-width: 300px;

  /* This will center the container in the middle on the horizontal axis */
  margin: 0 auto;

  /* Add space above the container (20% of the view height) */
  margin-top: 20vh;
}

img {
  width: 100%;
  border-radius: 12px;
  height: 214px;
  object-fit: cover;
}

.card {
  /* Change background color */
  background-color: white;

  /* Add border */
  border: 1px solid #bacdd8;

  /* Add space between the border and the content */
  padding: 8px;
  border-radius: 12px;
}
```

Now you should have a responsive image with a height of 214px. So let’s move on. We’ve also fixed the distorted image by adding the object-fit: cover;

But we still need to finish.

```CSS
.tag {
  padding: 4px 8px;
  border: 1px solid #e5eaed;
  border-radius: 50px;
  font-size: 12px;
  font-weight: 600;
  color: #788697;
}

.name {
  font-size: 24px;
  font-weight: 600;
  margin-top: 16px;
}

p {
  font-size: 14px;
  color: #7f8c9b;
  line height: 150%;
}

button {
  border: none;
  padding: 12px 24px;
  border-radius: 50px;
  font-weight: 600;
  color: #0077ff;
  background-color: #e0efff;  
  margin: 0 auto;
  display: block;
  cursor: pointer;
  padding: 16px 8px 8px 8px;
}

button: focus,
button: hover {
  background-color: red;
  color: #e0efff;
}
```

Here’s the final result:

```HTML
Image Placeholder
```

Caption: News-like card using CSS

## Example 2

n this example, we will use CSS to design a simple card. We will not use any frameworks or libraries because there will be occasions when you want to make things as basic as possible, which is exactly what this example is intended for. Let’s begin:

```HTML
<div class="tutorial">
  <div class="theheader">
    <p>Paragraph</p>
  </div>
  <div class="container">
    <p>Let me just place this here</p>
    <p>Yep, we’ve got another text here!</p>
    <p>Placeholder Texts</p>
    <p>How about a dumb text? That should work. </p>
  </div>
</div>
```

We’ll start by making a div called “tutorial.” Then we will build another div called header and wrap it around the text “theheader .”It will be the content’s header, as the name suggests.
Styling With CSS

We’ll set the card width to 30% in the “tutorial” class and utilize the percentage ‘%’ to make the card mobile responsive. Then, we’ll use the flexbox to rearrange the header and the container so that the title fits appropriately on the card.

To utilize flexbox, set the display to flex, which will stack the header and container into a row by default, and we’ll remedy that by changing the flex-direction to a column.

```CSS
.tutorial {
    width: 30%;
    display: flex;
    flex-direction: column;
    border: 1px red solid;
}

.theheader {
    height: 35%;
    background: red;
    color: white;
    text-align: center;
}

.container {
    padding: 3px 18px;
}
```

The header has also been styled. We’ll make the header 35% taller, alter the background color to red, and change the text color to white.

Finally, we’ll add the padding 3px 18px shorthand (similar to padding-top: 3 and padding-right: 18) to the container class to create some gap between the contents and the card, making the card look more professional.

```HTML
Image Placeholder
```

## Conclusion

So that brings us to the end of the tutorial. There are plenty of additional crucial CSS concepts to understand. However, using this guide, you should be able to use CSS to make your next project appear excellent.

These cards can be used on your website’s sidebars, blog entries, etc. I hope you enjoyed this guide, and thank you for taking the time to read it.

## Frequently Asked Questions
Mising Text

## Other Examples

This high-quality and hand-picked collection shows CSS cards from across the web. Included are links with examples and code for use on your website.

<article class="super-container"><figure><img loading="lazy" src="https://appcode.app/wp-content/uploads/2022/02/Three-Black-Product-CSS-Cards.png" alt="Three Black Product CSS Cards" title="Three Black Product CSS Cards"></figure><br><h2>Three Black Product CSS Cards</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Tristan White</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/triss90/pen/bpZzzN" rel="nofollow">Demo and Code</a></li></ul></div></div></article>

## CSS Cards With Drop-Shadow Effect

### About Project

#### Author

- Jaroslaw Hubert
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/jhkepa/pen/vddwYE)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/vddwYE/1645655638729/css-cards-with-drop-shadow-effect.zip)

![Modern CSS Cards Design](https://appcode.app/wp-content/uploads/2022/02/Modern-CSS-Cards-Design.png "Modern CSS Cards Design")

  

## Modern CSS Cards Design

### About Project

#### Author

- FlorinCornea
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/FlorinCornea/pen/KKwMeqd)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/KKwMeqd/1645655760667/modern-css-cards-design.zip)

![Pure CSS Cards and Deal Offer Cards](https://appcode.app/wp-content/uploads/2022/02/Pure-CSS-Cards-and-Deal-Offer-Cards.png "Pure CSS Cards and Deal Offer Cards")

  

## Pure CSS Cards and Deal Offer Cards

### About Project

#### Author

- Nishant Dogra
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/mrdogra007/pen/dZGbay)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/dZGbay/1645656026185/pure-css-cards-deal-and-offer-cards-widget.zip)

![Multi-Colored CSS Cards With Buttons](https://appcode.app/wp-content/uploads/2022/02/Multi-Colored-CSS-Cards-With-Buttons.png "Multi-Colored CSS Cards With Buttons")

  

## Multi-Colored CSS Cards With Buttons

### About Project

#### Author

- Yana Mitrofanova
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/Raina97/pen/qQdzOV)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/qQdzOV/1645656699977/css-cards-1.zip)

![Beautiful Collection of CSS Cards](https://appcode.app/wp-content/uploads/2022/02/Beautiful-Collection-of-CSS-Cards.png "Beautiful Collection of CSS Cards")

  

## Beautiful Collection of CSS Cards

### About Project

#### Author

- CodingTuting
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/codingtuting/pen/XWrBgQz)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/XWrBgQz/1645656880265/beautiful-css-cards.zip)

![Three Small CSS Cards](https://appcode.app/wp-content/uploads/2022/02/Three-Small-CSS-Cards.png "Three Small CSS Cards")

  

## Three Small CSS Cards

### About Project

#### Author

- Kelvyn Costa
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/kelvyncosta/pen/bgLwrw)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/bgLwrw/1645657031403/cards-css.zip)

![UI Profile CSS Card](https://appcode.app/wp-content/uploads/2022/02/UI-Profile-CSS-Card.png "UI Profile CSS Card")

  

## UI Profile CSS Card

### About Project

#### Author

- Muhammad Arsallan
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/marsallan/pen/jRYGVQ)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/jRYGVQ/1645657153948/ui-css-cards.zip)

![Flipping CSS Cards](https://appcode.app/wp-content/uploads/2022/02/Flipping-CSS-Cards.png "Flipping CSS Cards")

  

## Flipping CSS Cards

### About Project

#### Author

- Tom the Dev
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/thomasfaller/pen/EWOyRY)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/EWOyRY/1645657308449/flipping-css-cards.zip)

![CSS Cards Animation and Product Card](https://appcode.app/wp-content/uploads/2022/02/CSS-Cards-Animation-and-Product-Card.png "CSS Cards Animation and Product Card")

  

## CSS Cards Animation and Product Card

### About Project

#### Author

- Pratham
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/ps173/pen/yLJpWwy)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/yLJpWwy/1645657460083/css-cards-animationproduct-card.zip)

![Blue Flat CSS Cards](https://appcode.app/wp-content/uploads/2022/02/Blue-Flat-CSS-Cards.png "Blue Flat CSS Cards")

  

## Blue Flat CSS Cards

### About Project

#### Author

- Console.log
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/console_logs/pen/oqXRNK)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/oqXRNK/1645657740639/flat-css-cards.zip)

![Responsive Column CSS Cards](https://appcode.app/wp-content/uploads/2022/02/Responsive-Column-CSS-Cards.png "Responsive Column CSS Cards")

  

## Responsive Column CSS Cards

### About Project

#### Author

- Haneen Krimly
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/hkrimly/pen/mdbwKPR)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/mdbwKPR/1645657909070/responsive-css-cards.zip)

![Recipe Flipping CSS Cards](https://appcode.app/wp-content/uploads/2022/02/Recipe-Flipping-CSS-Cards.png "Recipe Flipping CSS Cards")

  

## Recipe Flipping CSS Cards

### About Project

#### Author

- Maja Kulpa-Malecka
- codepen.io

#### Links

- [Demo and Code](https://cdpn.io/maja127/fullpage/abbWKBV)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/abbWKBV/1645658221696/css-flipping-cards.zip)

![Tailwind CSS Cards](https://appcode.app/wp-content/uploads/2022/02/Tailwind-CSS-Cards.png "Tailwind CSS Cards")

  

## Tailwind CSS Cards

### About Project

#### Author

- Ross Orthwein
- codepen.io

#### Links

- [Demo and Code](https://cdpn.io/rossorthwein/fullpage/rZbwaq)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/rZbwaq/1645658449611/tailwind-css-cards-and-button.zip)

![Generic Responsive CSS Cards](https://appcode.app/wp-content/uploads/2022/02/Generic-Responsive-CSS-Cards.png "Generic Responsive CSS Cards")

  

## Generic Responsive CSS Cards

### About Project

#### Author

- Nick Kelly
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/nickresearch/pen/mdPNNOJ)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/mdPNNOJ/1645658583403/responsive-cards-generic.zip)

![Basic CSS Cards](https://appcode.app/wp-content/uploads/2022/02/Basic-CSS-Cards.png "Basic CSS Cards")

  

## Basic CSS Cards

### About Project

#### Author

- Haneen Krimly
- codepen.io

#### Links

- [Demo and Code](https://codepen.io/hkrimly/pen/ExYZedV)
- [Download](https://codepen-api-export-production.s3.us-west-2.amazonaws.com/zip/PEN/ExYZedV/1645658709315/basic-css-cards.zip)

## Recommended Articles

- [15 Text Outline CSS Examples and Code](https://appcode.app/15-text-outline-css-examples-and-code/)
- [15 Flexbox CSS Examples and Code](https://appcode.app/15-flexbox-css-examples-and-code/)
- [32 CSS Menu Examples and Code](https://appcode.app/css-menu-examples-and-code/)
- [16 CSS Image Gallery Examples and Code](https://appcode.app/css-image-gallery-examples-and-code/)
- [15 CSS Spinner Animation Examples and Code](https://appcode.app/css-spinner-animation-examples-and-code/)
- [15 CSS Chat Box Examples and Code](https://appcode.app/css-chat-box-examples-and-code/)
- [15 Awesome Keyframe CSS Animation Examples and Code](https://appcode.app/awesome-keyframe-css-animation-examples-and-code/)

## Other Articles

- [The CSS justify-self Property](https://appcode.app/the-css-justify-self-property/)
- [Explaining the Scale Property in CSS](https://appcode.app/explaining-the-scale-property-in-css/)
- [The Awesome CSS Transform Property and Scale Function](https://appcode.app/the-awesome-css-transform-property-and-scale-function/)

