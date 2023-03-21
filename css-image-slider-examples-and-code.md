---
title: CSS Image Sliders
taxonomy:
    category: CSS
post_date: 2021-09-12 21:18:00
---

This article demonstrates how to create several CSS image sliders for your webpage. Included are code walkthroughs and other slider examples.

A CSS image slider is a crucial part of any website or app. Sliders allow you to compact graphical information in a fun interactive way. The majority of the time, sliders are helpful to websites because they can be used to showcase different products or other relevant content to the visitor.

## Contents

## What Is an Image Slider in CSS?

An image slider is an animated HTML fragment used to display images, text, and videos as a slide show. The slider is typically made of frames that can be viewed independently. It is like a small viewport or screen that contains all the slides. Sometimes slides are on an automatic timer that changes to the next slide after some time. Other times there are controls that allow a user to adjust the content manually.

## Creating an Image Slider With Bullet Points

<figure class="wp-block-image size-large"><
  img loading="lazy" width="783" height="390" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Bullet-Points.png?resize=783%2C390&amp;ssl=1" alt="CSS Image Slider With Bullet Points" class="wp-image-15159" srcset="https://i2.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Bullet-Points.png?w=783&amp;ssl=1 783w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Bullet-Points.png?resize=300%2C149&amp;ssl=1 300w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Bullet-Points.png?resize=768%2C383&amp;ssl=1 768w" sizes="(max-width: 783px) 100vw, 783px" data-recalc-dims="1">
  <figcaption>CSS Image Slider With Bullet Points</figcaption>
</figure>

Let’s start by creating a basic image slider using only CSS. This slider will have bullet points to toggle between the three images.

First, we want to create the HTML outline. This outline includes `<span>`, `<img>`, and `<a>` elements.

```HTML
<div class="slider">
  <span id="slide-1"></span>
  <span id="slide-2"></span>
  <span id="slide-3"></span>
  <div class="image-container">
    <img src="https://images.unsplash.com/photo-1440342359743-84fcb8c21f21?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80" class="slide" width="500" height="300" />
    <img src="https://images.unsplash.com/photo-1473448912268-2022ce9509d8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1141&q=80" class="slide" width="500" height="300" />
    <img src="https://images.unsplash.com/photo-1511497584788-876760111969?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1332&q=80" class="slide" width="500" height="300" />
  </div>
  <div class="buttons">
    <a href="#slide-1"></a>
    <a href="#slide-2"></a>
    <a href="#slide-3"></a>
  </div>
</div>
```

The second step is applying styles to the `<a>` navigation links and setting the animation transition for each slide as it moves into view.

```CSS
.slider {
  width: 500px;
  height: 300px;
  background-color: yellow;
  margin-left: auto;
  margin-right: auto;
  margin-top: 0px;
  text-align: center;
  overflow: hidden;
  border-radius: 10px;
}

.image-container {
  width: 1500px;
  background-color: pink;
  height: 300px;
  clear: both;
  position: relative;
  -webkit-transition: left 2s;
  -moz-transition: left 2s;
  -o-transition: left 2s;
  transition: left 2s;
}

.slide {
  float: left;
  margin: 0px;
  padding: 0px;
  position: relative;
}

#slide-1:target ~ .image-container {
  left: 0px;
}

#slide-2:target ~ .image-container {
  left: -500px;
}

#slide-3:target ~ .image-container {
  left: -1000px;
}

.buttons {
  position: relative;
  top: -3rem;
}

.buttons a {
  display: inline-block;
  height: 15px;
  width: 15px;
  border-radius: 50px;
  background-color: white;
  box-shadow: 0px 0px 6px #00000087, inset 0px 0px 1px black;
  margin: 10px;
}
```

## Creating an Automatic Image Slider

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1017" height="455" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Automatic-Image-Slider.jpg?resize=1017%2C455&amp;ssl=1" alt="CSS Automatic Image Slider" class="wp-image-15161" srcset="https://i1.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Automatic-Image-Slider.jpg?w=1017&amp;ssl=1 1017w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Automatic-Image-Slider.jpg?resize=300%2C134&amp;ssl=1 300w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Automatic-Image-Slider.jpg?resize=768%2C344&amp;ssl=1 768w" sizes="(max-width: 1017px) 100vw, 1017px" data-recalc-dims="1">
  <figcaption>CSS Automatic Image Slider</figcaption>
</figure>

Sometimes we want to create an image slider that doesn’t have controls. We can achieve this by using CSS `@keyframe` animations to create a timer that controls each slide. The keyframes will use the `background-position` property to move a single image from left to right.

To begin, we’ll create a single HTML div element.

```HTML
<div class="simple"></div>
```

The next step is to add the CSS styles and the `@keyframe` animations to animate the single-frame slider.

```CSS
.simple {
  width: 800px;
  height: 350px;
  background-color: #eeeeee;
  margin: auto;
  background: url("https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2400&q=80");
  animation-name: slide;
  animation-duration: 10s;
  animation-direction: normal;
  animation-timing-function: ease;
  animation-iteration-count: infinite;
}

@keyframes slide {
  0% {
    background-position: 0 0;
  }
  16.66% {
    background-position: 0 0;
  }
  33.32% {
    background-position: -800px 0;
  }
  49.98% {
    background-position: -800px 0;
  }
  66.64% {
    background-position: -1600px 0;
  }
  83.30% {
    background-position: -1600px 0;
  }
  100% {
    background-position: 0 0;
  }
}
```

## Creating an Image Slider With Links

<figure class="wp-block-image size-large">
  <img loading="lazy" width="700" height="448" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Jump-Links.png?resize=700%2C448&amp;ssl=1" alt="CSS Image Slider With Jump Links" class="wp-image-15162" srcset="https://i2.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Jump-Links.png?w=700&amp;ssl=1 700w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Jump-Links.png?resize=300%2C192&amp;ssl=1 300w" sizes="(max-width: 700px) 100vw, 700px" data-recalc-dims="1">
  <figcaption>CSS Image Slider With Jump Links</figcaption>
</figure>

Sometimes it is necessary to create a slider with links to jump to individual slides. The links can be made with `<a>` elements (anchor links) to jump to the correct slide. The link elements are then styled up to create buttons with numbers.

The slides are boxes and use CSS `flexbox` to create a row and `overflow` to control how many boxes are visible.

For the transition effect between slides, use the CSS scroll-snap-type and then scroll-behavior with its value set to `smooth`. The smooth value results in a smooth animation that jumps to the next slide whenever clicking any of the links.

Additionally, we can style up a scroll bar as an optional control and add the `overscroll-behavior` property to make it swipeable.

Now let’s create the links and slides semantically.

```HTML
<div class="slider">
  <a href="#slide-1">1</a>
  <a href="#slide-2">2</a>
  <a href="#slide-3">3</a>
  <a href="#slide-4">4</a>
  <a href="#slide-5">5</a>
  <div class="slides">
    <div id="slide-1">1</div>
    <div id="slide-2">2</div>
    <div id="slide-3">3</div>
    <div id="slide-4">4</div>
    <div id="slide-5">5</div>
  </div>
</div>
```

Next, we will need the buttons, positioning, slides, and scrollbar styles.

```CSS
.slider {
  width: 500px;
  text-align: center;
  overflow: hidden;
}

.slides {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: x mandatory;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
}

.slides::-webkit-scrollbar {
  width: 10px;
  height: 10px;
}

.slides::-webkit-scrollbar-thumb {
  background: #666;
  border-radius: 10px;
}

.slides::-webkit-scrollbar-track {
  background: transparent;
}

.slides > div {
  scroll-snap-align: start;
  flex-shrink: 0;
  width: 500px;
  height: 300px;
  margin-right: 50px;
  border-radius: 10px;
  background: #eee;
  transform-origin: center center;
  transform: scale(1);
  transition: transform 0.5s;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 100px;
}

.slider > a {
  display: inline-flex;
  width: 1.5rem;
  height: 1.5rem;
  background: white;
  text-decoration: none;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  margin: 0 0 0.5rem 0;
  position: relative;
}

.slider > a:active {
  color: #1c87c9;
}

.slider > a {
  color: black;
}

.slider > a:focus {
  background: #eee;
}

body {
  height: 100%;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(to right, #1c87c9, #ffcc00);
  font-family: "Ropa Sans", sans-serif;
}
```

## Creating an Image Slider with Nav Buttons

<figure class="wp-block-image size-large">
  <img loading="lazy" width="777" height="424" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Autoplay-and-Navigation-Buttons.png?resize=777%2C424&amp;ssl=1" alt="CSS Image Slider With Autoplay and Navigation Buttons" class="wp-image-15164" srcset="https://i0.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Autoplay-and-Navigation-Buttons.png?w=777&amp;ssl=1 777w, https://i0.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Autoplay-and-Navigation-Buttons.png?resize=300%2C164&amp;ssl=1 300w, https://i0.wp.com/appcode.app/wp-content/uploads/2022/10/CSS-Image-Slider-With-Autoplay-and-Navigation-Buttons.png?resize=768%2C419&amp;ssl=1 768w" sizes="(max-width: 777px) 100vw, 777px" data-recalc-dims="1">
  <figcaption>CSS Image Slider With Autoplay and Navigation Buttons</figcaption>
</figure>

In this following code walkthrough, we can spice an image slider up with autoplay and navigation buttons. A cool thing about this example is the autoplay animation stops once a user interacts with the slider. When creating this example, we’ll rely on the `scroll-snap-align` property and the `::after` and `::before` pseudo-elements. We’ll also use two SVGs embedded in the `background-image: url(svg)` for the navigation arrows.

Let’s create the elements.

```HTML
<section class="carousel" aria-label="Gallery">
  <ol class="carousel__viewport">
    <li id="carousel__slide1" tabindex="0" class="carousel__slide">
      <div class="carousel__snapper">
        <a href="#carousel__slide4" class="carousel__prev"></a>
        <a href="#carousel__slide2" class="carousel__next"></a>
      </div>
    </li>
    <li id="carousel__slide2" tabindex="0" class="carousel__slide">
      <div class="carousel__snapper"></div>
      <a href="#carousel__slide1" class="carousel__prev"></a>
      <a href="#carousel__slide3" class="carousel__next"></a>
    </li>
    <li id="carousel__slide3" tabindex="0" class="carousel__slide">
      <div class="carousel__snapper"></div>
      <a href="#carousel__slide2" class="carousel__prev"></a>
      <a href="#carousel__slide4" class="carousel__next"></a>
    </li>
    <li id="carousel__slide4" tabindex="0" class="carousel__slide">
      <div class="carousel__snapper"></div>
      <a href="#carousel__slide3" class="carousel__prev"></a>
      <a href="#carousel__slide1" class="carousel__next"></a>
    </li>
  </ol>
  <aside class="carousel__navigation">
    <ol class="carousel__navigation-list">
      <li class="carousel__navigation-item">
        <a href="#carousel__slide1" class="carousel__navigation-button"></a>
      </li>
      <li class="carousel__navigation-item">
        <a href="#carousel__slide2" class="carousel__navigation-button"></a>
      </li>
      <li class="carousel__navigation-item">
        <a href="#carousel__slide3" class="carousel__navigation-button"></a>
      </li>
      <li class="carousel__navigation-item">
        <a href="#carousel__slide4" class="carousel__navigation-button"></a>
      </li>
    </ol>
  </aside>
</section>
```

We must add the element’s styles to get the autoplay animation and navigation arrows working.

```CSS
@keyframes tonext {
  75% {
    left: 0;
  }
  95% {
    left: 100%;
  }
  98% {
    left: 100%;
  }
  99% {
    left: 0;
  }
}

@keyframes tostart {
  75% {
    left: 0;
  }
  95% {
    left: -300%;
  }
  98% {
    left: -300%;
  }
  99% {
    left: 0;
  }
}

@keyframes snap {
  96% {
    scroll-snap-align: center;
  }
  97% {
    scroll-snap-align: none;
  }
  99% {
    scroll-snap-align: none;
  }
  100% {
    scroll-snap-align: center;
  }
}

body {
  max-width: 37.5rem;
  margin: 1rem auto;
  padding: 0 1.25rem;
  font-family: "Lato", sans-serif;
}

* {
  box-sizing: border-box;
  scrollbar-color: transparent transparent; /* thumb and track color */
  scrollbar-width: 0px;
}

*::-webkit-scrollbar {
  width: 0;
}

*::-webkit-scrollbar-track {
  background: transparent;
}

*::-webkit-scrollbar-thumb {
  background: transparent;
  border: none;
}

* {
  -ms-overflow-style: none;
}

ol,
li {
  list-style: none;
  margin: 0;
  padding: 0;
}

.carousel {
  position: relative;
  padding-top: 56.25%;
  filter: drop-shadow(0 0 10px #0003);
  perspective: 100px;
}

.carousel__viewport {
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  display: flex;
  overflow-x: scroll;
  counter-reset: item;
  scroll-behavior: smooth;
  scroll-snap-type: x mandatory;
}

.carousel__slide {
  position: relative;
  flex: 0 0 100%;
  width: 100%;
  background-color: #f99;
  counter-increment: item;
}

#carousel__slide1 {
  background-color: #3dc0e6;
}

#carousel__slide2 {
  background-color: #f89427;
}

#carousel__slide3 {
  background-color: #ec7272;
}

#carousel__slide4 {
  background-color: #5ab196;
}

.carousel__slide:before {
  content: counter(item);
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate3d(-50%, -40%, 70px);
  color: #fff;
  font-size: 2em;
}

.carousel__snapper {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  scroll-snap-align: center;
}

@media (hover: hover) {
  .carousel__snapper {
    animation-name: tonext, snap;
    animation-timing-function: ease;
    animation-duration: 4s;
    animation-iteration-count: infinite;
  }

  .carousel__slide:last-child .carousel__snapper {
    animation-name: tostart, snap;
  }
}

@media (prefers-reduced-motion: reduce) {
  .carousel__snapper {
    animation-name: none;
  }
}

.carousel:hover .carousel__snapper,
.carousel:focus-within .carousel__snapper {
  animation-name: none;
}

.carousel__navigation {
  position: absolute;
  right: 0;
  bottom: 0;
  left: 0;
  text-align: center;
}

.carousel__navigation-list,
.carousel__navigation-item {
  display: inline-block;
}

.carousel__navigation-button {
  display: inline-block;
  width: 1.5rem;
  height: 1.5rem;
  background-color: #333;
  background-clip: content-box;
  border: 0.25rem solid transparent;
  border-radius: 50%;
  font-size: 0;
  transition: transform 0.1s;
}

.carousel::before,
.carousel::after,
.carousel__prev,
.carousel__next {
  position: absolute;
  top: 0;
  margin-top: 27%;
  width: 4rem;
  height: 4rem;
  transform: translateY(-50%);
  border-radius: 50%;
  font-size: 0;
  outline: 0;
}

.carousel::before,
.carousel__prev {
  left: -1rem;
}

.carousel::after,
.carousel__next {
  right: -1rem;
}

.carousel::before,
.carousel::after {
  content: "";
  z-index: 1;
  background-color: #333;
  background-size: 1.5rem 1.5rem;
  background-repeat: no-repeat;
  background-position: center center;
  color: #fff;
  font-size: 2.5rem;
  line-height: 4rem;
  text-align: center;
  pointer-events: none;
}

.carousel::before {
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpolygon points='0,50 80,100 80,0' fill='%23fff'/%3E%3C/svg%3E");
}

.carousel::after {
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpolygon points='100,50 20,100 20,0' fill='%23fff'/%3E%3C/svg%3E");
}
```

## Other Examples

Here is a collection of sliders from around the web you can use in your project. The CSS sliders provided will be written in [CSS](https://www.w3.org/Style/CSS/Overview.en.html) and HTML, with sometimes [JavaScript](https://www.javascript.com/) mixed in. Using these examples is relatively easy as long as you have some experience in HTML, CSS, and JavaScript. Included are links with examples and code for use on your website.

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2021/09/HTML-CSS-Driven-Responsive-Image-Slider.png?w=1290&amp;ssl=1" alt="HTML CSS Driven Responsive Image Slider" title="HTML CSS Driven Responsive Image Slider" data-recalc-dims="1"><figcaption>CSS Responisve Image Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>HTML CSS Driven Responsive Image Slider</h4><p>HTML CSS Driven Responsive Image Slider is a project on codepen.io which uses CSS keyframes to generate a sliding animation. This example uses <a href="https://html.com/tags/figure/">HTML figure</a> and figcaption elements to markup the image element. Also, when the screen is resized, the slider resizes to fit the screen horizontally.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Dudley Storey</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/dudleystorey/pen/kFoGw">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2021/09/Responsive-Image-Slider.png?w=1290&amp;ssl=1" alt="Responsive Image Slider" title="Responsive Image Slider" data-recalc-dims="1"><figcaption>Responsive Image Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Responsive Image Slider</h4><p>Responsive Image Slider is a project on codepen.io which uses CSS and <a href="https://jquery.com/">JQuery</a> to animate a solid rectangle slider. You can add your images to fill in the colored backgrounds of each slide. The project uses CSS transitions on the next and previous button’s opacity for a fade-in, fade-out hover effect.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>David Fitas</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/dfitzy/pen/xZqGVo">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2021/09/Pure-CSS-Featured-Image-Slider.png?w=1290&amp;ssl=1" alt="Pure CSS Featured Image Slider" title="Pure CSS Featured Image Slider" data-recalc-dims="1"><figcaption>Responsive Image Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Pure CSS Featured Image Slider</h4><p>Pure CSS Featured Image Slider is a project on codepen.io which uses pure CSS to create an image slider. The image slider has a picture frame border representing a real-world art frame. Addionally, the CSS slider contains round black buttons at the frame’s bottom to navigate the slides. This example only uses 24 lines of HTML.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Joshua Hibbert</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/joshnh/pen/KwilB">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2021/09/GSAP-Slider.png?w=1290&amp;ssl=1" alt="GSAP Slider" title="GSAP Slider" data-recalc-dims="1"><figcaption>GSAP Image Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>GSAP Slider</h4><p>GSAP Slider is a project on codepen.io which uses CSS, GSAP JavaScript library, and JQuery to create an exceptional CSS slider. The slider includes navigation buttons and snippet of text with a read more link. The slider works on multiple screen sizes. This example also uses <a href="https://yoksel.github.io/flex-cheatsheet/">CSS flex to layout the content</a> within each slide and to place each slide in a row.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Goran Vrban</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/gvrban/pen/qjbpaa">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2021/09/Slicebox-3D-Image-Slider.png?w=1290&amp;ssl=1" alt="Slicebox 3D Image Slider" title="Slicebox 3D Image Slider" data-recalc-dims="1"><figcaption>3D Image Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Slicebox 3D Image Slider</h4><p>Slicebox 3D Image Slider is a project on codepen.io which uses CSS, JQuery Slicebox library, and Jquery to create a 3D rotating image slider. This image slider scales to fit the screen as the screen size changes. Also, this project includes buttons to navigate the image slides left or right. Included in the CSS styles is a special transition. <a href="https://webkit.org/blog-files/3d-transforms/transform-style.html">The transition is preserve-3d</a> which makes the child element keep it’s 3D position.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>codefactory</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/codefactory/pen/ozecy">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2021/09/CSS-Only-Image-Slider.png?w=1290&amp;ssl=1" alt="CSS Only Image Slider" title="CSS Only Image Slider" data-recalc-dims="1"><figcaption>CSS Only Image Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>CSS Only Image Slider</h4><p>CSS Only Image Slider is a project on codepen.io which contains two image slides. A slide is loaded in via an animation when a user clicks on one of the buttons. The animation slices two images down the middle and blurs the slide to the next one. This animation is created without the <a href="https://www.quackit.com/css/at-rules/css_keyframes_at-rule.cfm">CSS keyframes at-rule</a>.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Damián Muti</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/damianmuti/pen/OgBWej">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2021/09/Canvas-Image-Slider.png?w=1290&amp;ssl=1" alt="Canvas Image Slider" title="Canvas Image Slider" data-recalc-dims="1"><figcaption>Canvas Image Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Canvas Image Slider</h4><p>Canvas Image Slider is an image slider on codepen.io which uses CSS and the <a href="https://greensock.com/get-started/">GSAP Tweenmax JavaScript library</a> to create a multilayered lens. The slider moves the layers in lens focus as the animation traverses to the next slide. Next, the slider blurs the layers and loads the next image from the opposite direction. Addionally, the lens slider is responsive to different screen sizes.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Dario Fuzinato</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/fuzinato/pen/PwLLjB">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2021/09/Image-Slider-With-Masking-Effect.png?w=1290&amp;ssl=1" alt="Image Slider With Masking Effect" title="Image Slider With Masking Effect" data-recalc-dims="1"><figcaption>Image Slider With Masking</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Image Slider With Masking Effect</h4><p>Image Slider With Masking Effect is a project on codepen.io in which an image slider is designed as a card. The card uses a CSS drop shadow to create a raised effect, as if the slider is floating above the document. You can navigate the different slides when clicking the arrows inside the card. When the slider loads in new text, the text fades into view. This project uses a cool <a href="https://cubic-bezier.com/#.17,.67,.83,.67">CSS transition style called cubic-bezier</a> which is a type of easement when transitioning the slides.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Bhakti Pasaribu</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/balapa/pen/JXrjXK">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2021/09/Flexbox-Image-Slider.png?w=1290&amp;ssl=1" alt="Flexbox Image Slider" title="Flexbox Image Slider" data-recalc-dims="1"><figcaption>Flexbox Image Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Flexbox Image Slider</h4><p>Flexbox Image Slider is a project on codepen.io in which an image slider is created using CSS flexbox. The slider includes navigation buttons outside of the slider frame. When hovering over the navigation buttons, the buttons scale up, which causes the buttons to enlarge as the cursor hovers over the button. The scale animation is made using the <a href="https://tympanus.net/codrops/css_reference/translatex/">CSS transform translateX.</a></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Katherine Kato</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/kathykato/pen/prEmKe">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2021/09/Fullscreen-Image-Slider.png?w=1290&amp;ssl=1" alt="Fullscreen Image Slider" title="Fullscreen Image Slider" data-recalc-dims="1"><figcaption>Fullscreen Image Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Fullscreen Image Slider</h4><p>Fullscreen Image Slider is a project on codepen.io where the author has created a fullscreen image slider. When the slider is resized using the screen or viewed on a different device, the slider resizes the fill the entire screen. The project uses pure JavaScript the give the buttons the ability to control the slider direction. Event listeners are attached to each navigation button and trigger the JavaScript custom slide function.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Brad Traversy</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/bradtraversy/pen/boydaE">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2021/09/Modular-Responsive-Image-Slider.png?w=1290&amp;ssl=1" alt="Modular Responsive Image Slider" title="Modular Responsive Image Slider" data-recalc-dims="1"><figcaption>Modular Responsive Image Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Modular Responsive Image Slider</h4><p>Modular Responsive Image Slider is a project on codepen.io that expands to the full page. The image slider is <a href="https://en.wikipedia.org/wiki/Responsive_web_design">responsive and resizes</a> to fit different screen sizes. This project is modular, which means you can stack the sliders like blocks to build different row lengths or even a grid. When clicking on the navigation dots, the dots pulse with an animation effect to reflect the click. Also, when hovering over the slider, the navigation arrows slide and fade into the viewport to become clickable.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Eric Porter</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/EricPorter/pen/XaOEpP">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2021/09/Auto-Generated-Responsive-CSS-Slider.png?w=1290&amp;ssl=1" alt="Auto Generated Responsive CSS Slider" title="Auto Generated Responsive CSS Slider" data-recalc-dims="1"><figcaption>Auto Generated CSS Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Auto Generated Responsive CSS Slider</h4><p>Auto Generated Responsive CSS Slider is a project on codepen.io which utilizes only images for each slide of the slider. The slider is responsive and resizes to fit different screen sizes. This example uses CSS translate3d and CSS keyframe at-rules to control the slide animations.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Dudley Storey</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/dudleystorey/pen/xDrCw">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2021/09/Image-Slider-CSS-Only.png?w=1290&amp;ssl=1" alt="Image Slider CSS Only" title="Image Slider CSS Only" data-recalc-dims="1"><figcaption>Image Slider CSS Only</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Image Slider CSS Only</h4><p>Image Slider CSS Only is a project on codepen.io, which is built with only HTML and CSS. You can add images to this slider by extending the HTML code and CSS classes that reference a new slide. The user can change the content on the slider by using the white navigation circles in the middle bottom portion of the CSS slider.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Sandra Vos</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/sandra90/pen/xwMGgB">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2021/09/Pure-CSS3-Responsive-Slider.png?w=1290&amp;ssl=1" alt="Pure CSS3 Responsive Slider" title="Pure CSS3 Responsive Slider" data-recalc-dims="1"><figcaption>Pure CSS3 Responsive Slider</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Pure CSS3 Responsive Slider</h4><p>Pure CSS3 Responsive Slider is a project on codepen.io, which is created in pure CSS. This slider includes left and right navigational arrows and navigation dots in the middle bottom portion of the slider. To animate the slider, it uses a CSS keyframe at-rule to fade in the image when the user changes the slide. The fade in effect is made by using the <a href="https://blog.hubspot.com/website/opacity-css">CSS opacity property</a> and mixing in an ease-in-out CSS transition.</p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Mayur Birle</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/mayurbirle/pen/eEevBZ">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2021/09/Image-Slider-With-Mobile-Swipe.png?w=1290&amp;ssl=1" alt="Image Slider With Mobile Swipe" title="Image Slider With Mobile Swipe" data-recalc-dims="1"><figcaption>Image Slider With Mobile Swipe</figcaption></figure><br><h3 class="about-the-item">About Project</h3><h4>Image Slider With Mobile Swipe</h4><p>Image Slider With Mobile Swipe is a project on codepen.io which uses HTML, CSS, and JavaScript. The image slider includes an automatic sliding animation which is triggered every 4 seconds by a JavaScript variable (“let interval = 4000”). The slides can be switched by swiping the screen when using this image slider with a mobile device. This functionality is created by using the <a href="http://tutorials.jenkov.com/responsive-mobile-friendly-web-design/touch-events-in-javascript.html">touchend JavaScript event listener.</a></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Hakeem</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/Akimzzy/pen/JjGKMoX">Examples and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Onboarding-Screens.png?w=1290&amp;ssl=1" title="Onboarding Screens" alt="Onboarding Screens" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Onboarding Screens</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Jebbles</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/jebbles/pen/MKoYya">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Information-Card-Slider.png?w=1290&amp;ssl=1" title="Information Card Slider" alt="Information Card Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Information Card Slider</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Andy Tran</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/andytran/pen/xweoPN/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Image-Comparison-Slider.png?w=1290&amp;ssl=1" title="Image Comparison Slider" alt="Image Comparison Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Image Comparison Slider</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Mario Duarte</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/MarioDesigns/pen/KvXZPK">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Before-After-Image-Slider-Vanilla.png?w=1290&amp;ssl=1" title="Before After Image Slider (Vanilla)" alt="Before After Image Slider (Vanilla)" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Before After Image Slider (Vanilla)</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Huw Llewellyn</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/nosurprisethere/pen/xrXjYV">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Javascriptless-Before_After-Slider.png?w=1290&amp;ssl=1" title="Javascriptless Before_After Slider" alt="Javascriptless Before_After Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Javascriptless Before_After Slider</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Matthew Steele</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/Streetproject/pen/gRNebL">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Split-Screen-UI.png?w=1290&amp;ssl=1" title="Split-Screen UI" alt="Split-Screen UI" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Split-Screen UI</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Envato Tuts+</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/tutsplus/pen/bWKMoK">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Before-After-Slider-Gallery-With-SVG-Masks.png?w=1290&amp;ssl=1" title="Before &amp; After Slider Gallery With SVG Masks" alt="Before &amp; After Slider Gallery With SVG Masks" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Before &amp; After Slider Gallery With SVG Masks</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Craig Roblewsky</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/PointC/pen/LyEqGe">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/HTML5-Before-After-Comparison-Slider.png?w=1290&amp;ssl=1" title="HTML5 Video Before-and-After Comparison Slider" alt="HTML5 Before &amp; After Comparison Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>HTML5 Before &amp; After Comparison Slider</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Dudley Storey</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/dudleystorey/pen/DJqNKP">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/HTML5-Video-Before-and-After-Comparison-Slider.png?w=1290&amp;ssl=1" title="HTML5 Video Before-and-After Comparison Slider" alt="HTML5 Video Before-and-After Comparison Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Linear Slider With SplitText Effect _ Greensock</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Dudley Storey</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/dudleystorey/pen/OJZxJr">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Linear-Slider-With-SplitText-Effect-_-Greensock.png?w=1290&amp;ssl=1" title="Linear Slider With SplitText Effect _ Greensock" alt="Linear Slider With SplitText Effect _ Greensock" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Linear Slider With SplitText Effect _ Greensock</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Arden</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/aderaaij/pen/NxWzgY/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Smooth-3D-Perspective-Slider.png?w=1290&amp;ssl=1" title="Smooth 3D Perspective Slider" alt="Smooth 3D Perspective Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Smooth 3D Perspective Slider</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Alex Nozdriukhin</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/alexnoz/pen/brazWd">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Fullscreen-Hero-Image-Slider-Swipe-Panels-Theme.png?w=1290&amp;ssl=1" title="Fullscreen Hero Image Slider (Swipe Panels Theme)" alt="Fullscreen Hero Image Slider (Swipe Panels Theme)" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Fullscreen Hero Image Slider (Swipe Panels Theme)</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Tobias Bogliolo</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/tobiasdev/pen/MoEodz">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Responsive-Parallax-Drag-slider-With-Transparent-Letters.png?w=1290&amp;ssl=1" title="Responsive Parallax Drag-slider With Transparent Letters" alt="Responsive Parallax Drag-slider With Transparent Letters" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Responsive Parallax Drag-slider With Transparent Letters</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Ruslan Pivovarov</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/mrspok407/pen/bwLwvL/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Popout-Slider.png?w=1290&amp;ssl=1" title="Popout Slider" alt="Popout Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Popout Slider</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Nikolay Talanov</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/nathantaylor/pen/JEXgpj/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Fancy-Slider.png?w=1290&amp;ssl=1" title="Fancy Slider" alt="Fancy Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Gray &amp; White – Skewed Slider With Scrolling</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Nikolay Talanov</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/suez/pen/wMMgXp/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Gray-White-–-Skewed-Slider-With-Scrolling.png?w=1290&amp;ssl=1" title="Gray &amp; White – Skewed Slider With Scrolling" alt="Gray &amp; White – Skewed Slider With Scrolling" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Gray &amp; White – Skewed Slider With Scrolling</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Victor Belozyorov</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/WispProxy/pen/EyLWKg/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Pokemon-Slider.png?w=1290&amp;ssl=1" title="Pokemon Slider" alt="Pokemon Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Pokemon Slider</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Pham Mikun</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/mikun/pen/YWgqEX/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Slider-Parallax-Effect.png?w=1290&amp;ssl=1" title="Slider Parallax Effect" alt="Slider Parallax Effect" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Slider Parallax Effect</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Manuel Madeira</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/mmadeira/pen/jrBxpE/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Slider-with-Ripple-Effect-v1.1.png?w=1290&amp;ssl=1" title="Slider with Ripple Effect v1.1" alt="Slider with Ripple Effect v1.1" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Slider with Ripple Effect v1.1</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Pedro Castro</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/aspeddro/pen/dMxyde">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Clip-Path-Revealing-Slider.png?w=1290&amp;ssl=1" title="Clip-Path Revealing Slider" alt="Clip-Path Revealing Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Clip-Path Revealing Slider</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Nikolay Talanov</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/jjmartucci/pen/JjvwEY">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Full-Page-Slider.png?w=1290&amp;ssl=1" title="Full Page Slider" alt="Full Page Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Full Page Slider</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Joseph Martucci</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/jjmartucci/pen/JjvwEY">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Full-Slider-Prototype.png?w=1290&amp;ssl=1" title="Full Slider Prototype" alt="Full Slider Prototype" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Full Slider Prototype</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Glauber Sampaio</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/glaubersampaio/pen/Qwzjvy/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Greensock-Animated-Slideshow-Wip.png?w=1290&amp;ssl=1" title="Greensock Animated Slideshow [Wip]" alt="Greensock Animated Slideshow [Wip]" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Greensock Animated Slideshow [Wip]</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Arden</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/glaubersampaio/pen/Qwzjvy/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Pure-CSS-Slider-With-Custom-Effects.png?w=1290&amp;ssl=1" title="Pure CSS Slider With Custom Effects" alt="Pure CSS Slider With Custom Effects" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Pure CSS Slider With Custom Effects</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Nikolay Talanov</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/suez/pen/vEZMoa/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Fullscreen-Drag-Slider-With-Parallax.png?w=1290&amp;ssl=1" title="Fullscreen Drag-Slider With Parallax" alt="Fullscreen Drag-Slider With Parallax" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Fullscreen Drag-Slider With Parallax</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Nikolay Talanov</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/suez/pen/ByvKXE/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Actual-Rotating-Slider.png?w=1290&amp;ssl=1" title="Actual Rotating Slider" alt="Actual Rotating Slider" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Actual Rotating Slider</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Tyler Johnson</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/tylernj42/pen/LEKedz/">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/CSS-Carousel-With-Keyboard-Controls.png?w=1290&amp;ssl=1" title="CSS Carousel With Keyboard Controls" alt="CSS Carousel With Keyboard Controls" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>CSS Carousel With Keyboard Controls</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>David Lewis</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/dp_lewis/pen/WNZQzN">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/CSS-Slider-–-Pure-CSS-–-10.png?w=1290&amp;ssl=1" title="CSS Slider – Pure CSS – #10" alt="CSS Slider – Pure CSS – #10" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>CSS Slider – Pure CSS – #10</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Ivan Grozdic</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/ig_design/pen/NWxwBvw">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Pure-CSS-Slideshow.png?w=1290&amp;ssl=1" title="Pure CSS Slideshow" alt="Pure CSS Slideshow" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Pure CSS Slideshow</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Charanjit Chana</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/cchana/pen/xxwgLgY">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Pure-CSS-Carousel.png?w=1290&amp;ssl=1" title="Pure CSS Carousel" alt="Pure CSS Carousel" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Pure CSS Carousel</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Jenning</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/jenning/pen/JjoGKgE">Demo and Code</a></li></ul></div></div></article>

<article class="super-container"><figure><img loading="lazy" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Slider-With-Complex-Animation-and-Half-Collored-Angled-Text.png?w=1290&amp;ssl=1" title="Slider With Complex Animation and Half-Collored Angled Text" alt="Slider With Complex Animation and Half-Collored Angled Text" data-recalc-dims="1"><figcaption></figcaption></figure><br><h2>Slider With Complex Animation and Half-Collored Angled Text</h2><h3 class="about-the-item">About Project</h3><h4></h4><p></p><div class="info-box"><div class="info info-author"><h4>Author</h4><ul><li>Ruslan Pivovarov</li><li>codepen.io</li></ul></div><div class="info info-link"><h4>Links</h4><ul><li><a href="https://codepen.io/mrspok407/pen/YWLqVo/">Demo and Code</a></li></ul></div></div></article>

## See Also

- [CSS Cards](https://appcode.app/css-card-examples-and-code/)
- [CSS Carousels](https://appcode.app/css-carousel-examples-and-code/)
- [CSS Image Galleries](https://appcode.app/css-image-gallery-examples-and-code/)
- [CSS (Cascading Style Sheets)](https://appcode.app/how-to-use-css-cascading-style-sheets-to-style-html/)
