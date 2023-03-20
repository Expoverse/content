---
title: How To Create Video Overlays With CSS
taxonomy:
    category: CSS
post_date: 2022-02-23 23:36:21  
---

There are many types of different video overlays on the modern web, from ads and video suggestions to skip buttons. In this tutorial, we’ll be creating a three-card video suggestion overlay.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="361" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/CSS-Video-Overlays.png?resize=1024%2C361&amp;ssl=1" alt="CSS Video Overlays" class="wp-image-11320" srcset="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/CSS-Video-Overlays.png?resize=1024%2C361&amp;ssl=1 1024w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/CSS-Video-Overlays.png?resize=300%2C106&amp;ssl=1 300w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/CSS-Video-Overlays.png?resize=768%2C271&amp;ssl=1 768w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/CSS-Video-Overlays.png?resize=1536%2C542&amp;ssl=1 1536w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/CSS-Video-Overlays.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>CSS Video Overlays</figcaption>
</figure>

## Contents

## Creating The Base Video Element

First, we will need to create the base video element, so we have a video to add overlays to.

```HTML
<div class="container">
  <video id="myVideo" preload="none" autoplay loop muted>
    <source src="https://appcode.app/wp-content/uploads/2022/03/Pexels-Videos-1448735.mp4" type="video/mp4">
  </video>

  <div class="overlay-container">
  </div>
  <div class="content">
    <div class="title">
      <h1>Video Background Tutorial</h1>
      <p>We can show our contents on background video.</p>
    </div>
  </div>
</div>
```

We’ll need to style this video element to make it full width, so we have room to insert our overlays.

```CSS
html, body {
  margin: 0;
}

#myVideo {
  position: fixed;
  top: 0;
  left: 0;
  min-width: 100%;
  min-height: 100%;

}
 
.content {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 50px;
}

.title{
  color:white;
}
```

Let’s observe the rendered code.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="576" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-an-HTML-Video-Element-1024x576.png?resize=1024%2C576&amp;ssl=1" alt="Creating an HTML Video Element" class="wp-image-11267" srcset="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-an-HTML-Video-Element.png?resize=1024%2C576&amp;ssl=1 1024w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-an-HTML-Video-Element.png?resize=300%2C169&amp;ssl=1 300w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-an-HTML-Video-Element.png?resize=768%2C432&amp;ssl=1 768w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-an-HTML-Video-Element.png?resize=1536%2C864&amp;ssl=1 1536w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-an-HTML-Video-Element.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>Creating an HTML Video Element</figcaption>
</figure>

We can see above we’ve built a simple video with a header and title.

We’ve added a div section with the class `.overlay-container` in the HTML code, which is our div container where we will be placing our video overlays.

```HTML
<div class="overlay-container">
</div>
```

Now let’s move on to the next step.

## Creating the Card Overlays

Now let’s prepare the three cards by creating the HTML and CSS necessary to render them. The first step is wrapping the three cards in a div container with the `.card` class. This container will include the image, title, user info, and description.

```HTML
<div class="card">
</div>
```

Now we will write the following HTML code to create the first card.

```HTML
<div class="card">
  <div class="card__header">
    <img src="https://source.unsplash.com/600x400/?computer" alt="card__image" class="card__image" width="600">
  </div>
  <div class="card__body">
    <span class="tag tag-blue">Technology</span>
    <h4>What's new in 2022 Tech</h4>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi perferendis molestiae non nemo doloribus. Doloremque, nihil! At ea atque quidem!</p>
  </div>
  <div class="card__footer">
    <div class="user">
      <img src="https://i.pravatar.cc/40?img=1" alt="user__image" class="user__image">
      <div class="user__info">
        <h5>Jane Doe</h5>
        <small>2h ago</small>
      </div>
    </div>
  </div>
</div>
```

We also need to add CSS styles to give the card its visual appearance.

```CSS
url("https://fonts.googleapis.com/css2?family=Quicksand:wght@300..700&display=swap");
 
*,
*::before,
*::after {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

html, body {
  margin: 0;
}

body {
  font-family: "Quicksand", sans-serif;
  display: grid;
  place-items: center;
  height: 100vh;
  background: #7f7fd5;
  background: linear-gradient(to right, #91eae4, #86a8e7, #7f7fd5);
}

.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-block: 2rem;
  gap: 2rem;
}

img {
  max-width: 100%;
  display: block;
  object-fit: cover;
}

.card {
  display: flex;
  flex-direction: column;
  width: clamp(20rem, calc(20rem + 2vw), 22rem);
  overflow: hidden;
  box-shadow: 0 0.1rem 1rem rgba(0, 0, 0, 0.1);
  border-radius: 1em;
  background: #ece9e6;
  background: linear-gradient(to right, #ffffff, #ece9e6);
      box-shadow: 0 2px 4px rgb(0 0 0 / 50%);
}

.card__body {
  padding: 1rem;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.tag {
  align-self: flex-start;
  padding: 0.25em 0.75em;
  border-radius: 1em;
  font-size: 0.75rem;
}

.tag + .tag {
  margin-left: 0.5em;
}

.tag-blue {
  background: #56ccf2;
  background: linear-gradient(to bottom, #2f80ed, #56ccf2);
  color: #fafafa;
}

.tag-brown {
  background: #d1913c;
  background: linear-gradient(to bottom, #ffd194, #d1913c);
  color: #fafafa;
}

.tag-red {
  background: #cb2d3e;
  background: linear-gradient(to bottom, #ef473a, #cb2d3e);
  color: #fafafa;
}

.card__body h4 {
  font-size: 1.5rem;
  text-transform: capitalize;
}

.card__footer {
  display: flex;
  padding: 1rem;
  margin-top: auto;
}

.user {
  display: flex;
  gap: 0.5rem;
}

.user__image {
  border-radius: 50%;
}

.user__info > small {
  color: #666;
}

.overlay-container {
  position: relative;
  display: flex;
  gap: 1.5rem;
}
```

Let’s observe our first overlay card once the HTML and CSS has been added to the `.overlay-container.`

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="576" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-a-Single-Video-Overlay-Card-With-CSS.png?resize=1024%2C576&amp;ssl=1" alt="Creating a Single Video Overlay Card With CSS" class="wp-image-11278" srcset="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-a-Single-Video-Overlay-Card-With-CSS.png?resize=1024%2C576&amp;ssl=1 1024w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-a-Single-Video-Overlay-Card-With-CSS.png?resize=300%2C169&amp;ssl=1 300w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-a-Single-Video-Overlay-Card-With-CSS.png?resize=768%2C432&amp;ssl=1 768w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-a-Single-Video-Overlay-Card-With-CSS.png?resize=1536%2C864&amp;ssl=1 1536w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-a-Single-Video-Overlay-Card-With-CSS.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>Creating a Single Video Overlay Card With CSS</figcaption>
</figure>

Let’s explain how the HTML code works. We will use the class `.card` class three times to create three empty cards.

```HTML
<div class="card">
  <!-- Card Contents -->
</div>
```

Then we use the `.card__header` class when creating the headers of each card.

```HTML
<div class="card">
  <div class="card__header">
     <!-- Card image element -->
  </div>
</div>
```

Next, we add an image from [unsplash.com](unsplash.com) to this header with a width of 600.

```HTML
<div class="card">
  <div class="card__header">
     <img src="https://source.unsplash.com/600x400/?computer" alt="card__image" class="card__image" width="600">
  </div>
</div>
```

Now we move on to the body of the card. We will use the `.card__body` class for the body.

```HTML
<div class="card">
  <div class="card__header">
    <!-- Card image element -->
  </div>
  <div class="card__body">
    <!-- Card body elements --> 
  </div>
</div>
```

The first item in the body is the video tags. We will use a different color for the tags on the backgrounds of each card. The first tag will be blue, and the colors on the other cards will be yellow and red. The colors of the cards use a class called `.tag-$colorname`. As such we’ve used the `.tag-blue` class for the technology tag.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="240" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-Video-Overlay-Cards-With-Tags-Using-CSS.png?resize=1024%2C240&amp;ssl=1" alt="Creating Video Overlay Cards With Tags Using CSS" class="wp-image-11291" srcset="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-Video-Overlay-Cards-With-Tags-Using-CSS.png?resize=1024%2C240&amp;ssl=1 1024w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-Video-Overlay-Cards-With-Tags-Using-CSS.png?resize=300%2C70&amp;ssl=1 300w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-Video-Overlay-Cards-With-Tags-Using-CSS.png?resize=768%2C180&amp;ssl=1 768w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-Video-Overlay-Cards-With-Tags-Using-CSS.png?resize=1536%2C360&amp;ssl=1 1536w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Creating-Video-Overlay-Cards-With-Tags-Using-CSS.png?w=1577&amp;ssl=1 1577w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>Creating Video Overlay Cards With Tags Using CSS</figcaption>
</figure>

```HTML
<div class="card__body">
  <span class="tag tag-blue">Technology</span>
</div>
```

Then under the tag we place a header and a paragraph in the body.

<figure class="wp-block-image size-large">
  <img loading="lazy" width="435" height="196" src="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Adding-a-Header-and-Paragraph-Element-Using-CSS.png?resize=435%2C196&amp;ssl=1" alt="Adding a Header and Paragraph Element Using CSS" class="wp-image-11295" srcset="https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Adding-a-Header-and-Paragraph-Element-Using-CSS.png?w=435&amp;ssl=1 435w, https://i0.wp.com/appcode.app/wp-content/uploads/2022/03/Adding-a-Header-and-Paragraph-Element-Using-CSS.png?resize=300%2C135&amp;ssl=1 300w" sizes="(max-width: 435px) 100vw, 435px" data-recalc-dims="1">
  <figcaption>Adding a Header and Paragraph Element Using CSS</figcaption>
</figure>

```HTML
<div class="card__body">
  <span class="tag tag-blue">Technology</span>
  <h4>What's new in 2022 Tech</h4>
  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi perferendis molestiae non nemo doloribus. Doloremque, nihil! At ea atque quidem!</p>
</div>
```

Next is the footer. We will use the `.card__footer` class to construct a div element. We will use an avatar from [pravatar.cc](pravatar.cc) website and place the image inside the container.

```HTML
<div class="card__footer">
  <div class="user">
    <img src="https://i.pravatar.cc/40?img=1" alt="user__image" class="user__image">

    <!-- User info elements -->
  </div>
</div>
```

Now the last part is adding the user info which consist of a `.user__info container`, the name, and time.

```HTML
<div class="card__footer">
  <div class="user">
    <img src="https://i.pravatar.cc/40?img=1" alt="user__image" class="user__image">
    <div class="user__info">
      <h5>Jane Doe</h5>
      <small>2h ago</small>
    </div>
  </div>
</div>
```

With each part described we now have the first card. Let’s proceed and add the second and third cards.

```HTML
<div class="card">
  <div class="card__header">
    <img src="https://source.unsplash.com/600x400/?food" alt="card__image" class="card__image" width="600">
  </div>
  <div class="card__body">
    <span class="tag tag-brown">Food</span>
    <h4>Delicious Food</h4>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi perferendis molestiae non nemo doloribus. Doloremque, nihil! At ea atque quidem!</p>
  </div>
  <div class="card__footer">
    <div class="user">
      <img src="https://i.pravatar.cc/40?img=2" alt="user__image" class="user__image">
      <div class="user__info">
        <h5>Jony Doe</h5>
        <small>Yesterday</small>
      </div>
    </div>
  </div>
</div>
<div class="card">
  <div class="card__header">
    <img src="https://source.unsplash.com/600x400/?car,automobile" alt="card__image" class="card__image" width="600">
  </div>
  <div class="card__body">
    <span class="tag tag-red">Automobile</span>
    <h4>Race to your heart content</h4>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Sequi perferendis molestiae non nemo doloribus. Doloremque, nihil! At ea atque quidem!</p>
  </div>
  <div class="card__footer">
    <div class="user">
      <img src="https://i.pravatar.cc/40?img=3" alt="user__image" class="user__image">
      <div class="user__info">
        <h5>John Doe</h5>
        <small>2d ago</small>
      </div>
    </div>
  </div>
</div>
```

Now we have three cards. Thanks to this piece of code, our card components are placed horizontally in the video. You can see below the CSS gap property spaces the cards with a gap.

```CSS
.overlay-container {
  position: relative;
  display: flex;
  gap: 1.5rem;
}
```

<figure class="wp-block-image size-large">
  <img loading="lazy" width="1024" height="429" src="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Card-Overlay-Positioning-Using-Flex-With-CSS.png?resize=1024%2C429&amp;ssl=1" alt="Card Overlay Positioning Using Flex With CSS" class="wp-image-11357" srcset="https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Card-Overlay-Positioning-Using-Flex-With-CSS.png?resize=1024%2C429&amp;ssl=1 1024w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Card-Overlay-Positioning-Using-Flex-With-CSS.png?resize=300%2C126&amp;ssl=1 300w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Card-Overlay-Positioning-Using-Flex-With-CSS.png?resize=768%2C322&amp;ssl=1 768w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Card-Overlay-Positioning-Using-Flex-With-CSS.png?resize=1536%2C643&amp;ssl=1 1536w, https://i1.wp.com/appcode.app/wp-content/uploads/2022/03/Card-Overlay-Positioning-Using-Flex-With-CSS.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>Card Overlay Positioning Using Flex With CSS</figcaption>
</figure>

## Project Solution

Here is the entire CSS of the project.

```CSS
url("https://fonts.googleapis.com/css2?family=Quicksand:wght@300..700&display=swap");
 
*,
*::before,
*::after {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

html, body {
  margin: 0;
}

body {
  font-family: "Quicksand", sans-serif;
  display: grid;
  place-items: center;
  height: 100vh;
  background: #7f7fd5;
  background: linear-gradient(to right, #91eae4, #86a8e7, #7f7fd5);
}

.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin-block: 2rem;
  gap: 2rem;
}

img {
  max-width: 100%;
  display: block;
  object-fit: cover;
}

.card {
  display: flex;
  flex-direction: column;
  width: clamp(20rem, calc(20rem + 2vw), 22rem);
  overflow: hidden;
  box-shadow: 0 0.1rem 1rem rgba(0, 0, 0, 0.1);
  border-radius: 1em;
  background: #ece9e6;
  background: linear-gradient(to right, #ffffff, #ece9e6);
      box-shadow: 0 2px 4px rgb(0 0 0 / 50%);
}

.card__body {
  padding: 1rem;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.tag {
  align-self: flex-start;
  padding: 0.25em 0.75em;
  border-radius: 1em;
  font-size: 0.75rem;
}

.tag + .tag {
  margin-left: 0.5em;
}

.tag-blue {
  background: #56ccf2;
  background: linear-gradient(to bottom, #2f80ed, #56ccf2);
  color: #fafafa;
}

.tag-brown {
  background: #d1913c;
  background: linear-gradient(to bottom, #ffd194, #d1913c);
  color: #fafafa;
}

.tag-red {
  background: #cb2d3e;
  background: linear-gradient(to bottom, #ef473a, #cb2d3e);
  color: #fafafa;
}

.card__body h4 {
  font-size: 1.5rem;
  text-transform: capitalize;
}

.card__footer {
  display: flex;
  padding: 1rem;
  margin-top: auto;
}

.user {
  display: flex;
  gap: 0.5rem;
}

.user__image {
  border-radius: 50%;
}

.user__info > small {
  color: #666;
}

.overlay-container {
  position: relative;
  display: flex;
  gap: 1.5rem;
}

html, body {
  margin: 0;
}


#myVideo {
  position: fixed;
  top: 0;
  left: 0;
  min-width: 100%;
  min-height: 100%;

}
 
  /* Add some content at the top of the video/page */
.content {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 50px;
}

.title{
  color:white;
}
```

Now we have a title and three card overlays on our video background. Let’s take a look at the final output of our code.

<figure class="wp-block-image size-large"><img loading="lazy" width="1024" height="576" src="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/A-Video-Element-With-Three-Card-Overlays-Using-CSS.png?resize=1024%2C576&amp;ssl=1" alt="A Video Element With Three Card Overlays Using CSS" class="wp-image-11307" srcset="https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/A-Video-Element-With-Three-Card-Overlays-Using-CSS.png?resize=1024%2C576&amp;ssl=1 1024w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/A-Video-Element-With-Three-Card-Overlays-Using-CSS.png?resize=300%2C169&amp;ssl=1 300w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/A-Video-Element-With-Three-Card-Overlays-Using-CSS.png?resize=768%2C432&amp;ssl=1 768w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/A-Video-Element-With-Three-Card-Overlays-Using-CSS.png?resize=1536%2C864&amp;ssl=1 1536w, https://i2.wp.com/appcode.app/wp-content/uploads/2022/03/A-Video-Element-With-Three-Card-Overlays-Using-CSS.png?w=1920&amp;ssl=1 1920w" sizes="(max-width: 1024px) 100vw, 1024px" data-recalc-dims="1">
  <figcaption>A Video Element With Three Card Overlays Using CSS</figcaption>
</figure>

## See Also

- [How To Create a Full-Width Video Background With CSS](https://appcode.app/how-to-create-a-full-width-video-background-with-css/)
- [How To Create an HTML Carousel](https://appcode.app/how-to-create-an-html-carousel/)
- [How To Create a Stacked Card Hover Effect Using CSS](https://appcode.app/how-to-create-a-stacked-card-hover-effect-using-css/)
- [How to Center DIV Elements or Nested Elements](https://appcode.app/how-to-center-div-elements-or-nested-elements/)
