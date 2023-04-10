---

title: How To Handle Form Data With jQuery
taxonomy:
    category: jQuery
post_date: 2022-03-01 02:54:39

---

The article demonstrates how to handle and validate a few types of form inputs with jQuery before sending the data to a server.

Forms are a common feature of webpages.<sup id="cite_ref-1"><a href="#cite_note-1">[1]</a></sup> They commonly provide services such as authenticating users via login and registration, collecting feedback, checking out for purchasing products, searching, profiles, adding descriptions, setting usernames, and any other implementations you can imagine.<sup id="cite_ref-2"><a href="#cite_note-2">[2]</a></sup> 

In the sections below we'll cover a step-by-step breakdown installing jQuery, performing operations to collect data from the form input fields as variables, validating data is the correct type using by using a regular expression (regEx), and returning an error message if a field input is an invalid type whenever the form is submitted. The form used is an account registration example that will include the name, email, and password fields.

## Contents

## Installing jQuery

First, in order to use jQuery we need to add it to a webpage. There are multiple ways to include jQuery.<sup id="cite_ref-3"><a href="#cite_note-3">[3]</a></sup>  We will being adding the jQuery library with a file hosted on a Content Delivery Network (CDN) in the `<head>` element of the website markup. 

*Note:* If you already have the jQuery library hosted on a server, skip this step and include the library via a script tag pointed at the https location of the file.

A script element can be used to add a JavaScript file from a remote source such as a CDN to your webpage.<sup id="cite_ref-4"><a href="#cite_note-4">[4]</a></sup> This file is hosted on cdn.js. Add this element before the closing `</head>` tag.

```javascript
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.4/jquery.min.js"></script>
```

To specify a different version of jQuery you can change the version in the URL.<sup id="cite_ref-5"><a href="#cite_note-5">[5]</a></sup> 

```javascript
https://cdnjs.cloudflare.com/ajax/libs/jquery/{version number}/jquery.min.js
                                              ^
                                              | - Library version
```

## **Form markup**

<figure class="wp-block-image size-large"><img loading="lazy" width="1024" height="402" src="https://appcode.app/wp-content/uploads/2022/03/Basic-Form-Handling-With-jQuery-1024x402.png" alt="Basic Form Handling With jQuery" class="wp-image-9180" srcset="https://appcode.app/wp-content/uploads/2022/03/Basic-Form-Handling-With-jQuery-1024x402.png 1024w, https://appcode.app/wp-content/uploads/2022/03/Basic-Form-Handling-With-jQuery-300x118.png 300w, https://appcode.app/wp-content/uploads/2022/03/Basic-Form-Handling-With-jQuery-768x302.png 768w, https://appcode.app/wp-content/uploads/2022/03/Basic-Form-Handling-With-jQuery-1536x603.png 1536w, https://appcode.app/wp-content/uploads/2022/03/Basic-Form-Handling-With-jQuery.png 1920w" sizes="(max-width: 1024px) 100vw, 1024px"><figcaption>Basic Form Handling With jQuery</figcaption></figure>

A form requires HTML when using markup.<sup id="cite_ref-6"><a href="#cite_note-6">[6]</a></sup> The HTML below is the markup of our form which tells the browser which input fields, labels, buttons, and attributes should be included.<sup id="cite_ref-7"><a href="#cite_note-7">[7]</a></sup>

```markup
<div id="container">
  <div class="form-container">
    <form id="signup_form" method="post" action="#">
      <h1>Create Account</h1>
      <span>with your name, email, and password.</span>
      <input id="name" type="text" placeholder="Name" />
      <input id="email" type="email" placeholder="Email" />
      <input id="password" type="password" placeholder="Password" />
      <button>Sign Up</button>
    </form>
  </div>
  <div class="overlay-container">
    <div class="overlay">
      <div class="overlay-panel">
        <h1>Welcome Back!</h1>
        <p>To manage your content login with your credentials.</p>
        <button id="signIn">Sign In</button>
      </div>
    </div>
  </div>
</div>
```

## Form styles

Below is what the account creation form looks like without CSS styles.

<figure class="wp-block-image size-large"><img loading="lazy" width="1024" height="488" src="https://appcode.app/wp-content/uploads/2022/03/Form-Without-CSS-Styles-1024x488.png" alt="Form Without CSS Styles" class="wp-image-9184" srcset="https://appcode.app/wp-content/uploads/2022/03/Form-Without-CSS-Styles-1024x488.png 1024w, https://appcode.app/wp-content/uploads/2022/03/Form-Without-CSS-Styles-300x143.png 300w, https://appcode.app/wp-content/uploads/2022/03/Form-Without-CSS-Styles-768x366.png 768w, https://appcode.app/wp-content/uploads/2022/03/Form-Without-CSS-Styles.png 1338w" sizes="(max-width: 1024px) 100vw, 1024px"><figcaption>Form Without CSS Styles</figcaption></figure>


**Note**: Remember, the CSS is not fixed; you can customize the styles.

```css
* {
  box-sizing: border-box;
}

body {
  background: #f6f5f7;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  font-family: sans-serif;
  height: 100vh;
  margin: 0;
  background: linear-gradient(white, #d7d7d7);
}

h1 {
  margin: 0;
}

p {
  font-size: 14px;
  font-weight: 100;
  line-height: 20px;
  letter-spacing: 0.5px;
  margin: 20px 0 30px;
}

span {
  font-size: 12px;
}

button {
  border-radius: 20px;
  border: 1px solid #2b47ff;
  background-color: #2b49ff;
  color: #ffffff;
  font-size: 12px;
  font-weight: bold;
  padding: 12px 45px;
  letter-spacing: 1px;
  text-transform: uppercase;
  transition: transform 80ms ease-in;
  margin-top: 10px;
}

button:active {
  transform: scale(0.95);
}

button:focus {
  outline: none;
}

#signIn {
  background-color: transparent;
  border-color: #ffffff;
}

form {
  background-color: #ffffff;
  display: flex;
  justify-content: center;
  flex-direction: column;
  padding: 0 50px;
  height: 100%;
}

input {
  background-color: #eee;
  border: none;
  padding: 12px 15px;
  margin: 8px 0;
  width: 100%;
}

#container {
  border-radius: 10px;
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
  width: 750px;
  max-width: 100%;
  min-height: 480px;
  display: flex;
  overflow: hidden;
}

.form-container {
  width: 100%;
  height: 100%;
  order: 2;
}

.overlay-container {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.overlay {
  background: #ff416c;
  background: -webkit-linear-gradient(to right, #ff4b2b, #ff416c);
  background: linear-gradient(to right, #2b53ff, #0d2234);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 0 0;
  color: #ffffff;
  height: 100%;
  width: 200%;
}

.overlay-panel {
  display: flex;
  justify-content: center;
  flex-direction: column;
  height: 100%;
  width: 50%;
  padding: 0 40px;
}

.error {
  height: 20px;
  color: red;
  line-height: 20px;
  text-align: left;
  display: block;
  width: 100%;
}
```

After adding the CSS styles to your signup form, it should look similar but not identical to the image below as we removed some of the styles and HTML markup to simplify the demonstration.

<figure class="wp-block-image size-large"><img loading="lazy" width="946" height="589" src="https://appcode.app/wp-content/uploads/2022/03/Form-With-CSS-Styles.png" alt="Form With CSS Styles" class="wp-image-9186" srcset="https://appcode.app/wp-content/uploads/2022/03/Form-With-CSS-Styles.png 946w, https://appcode.app/wp-content/uploads/2022/03/Form-With-CSS-Styles-300x187.png 300w, https://appcode.app/wp-content/uploads/2022/03/Form-With-CSS-Styles-768x478.png 768w" sizes="(max-width: 946px) 100vw, 946px"><figcaption>Form With CSS Styles</figcaption></figure>

## jQuery form handling

After adding the styles and properties to the form, we need to add the jQuery functionality to start validating user input. 

The below code will add field validation and error handling to the form.

```javascript
$(document).ready(function () {
  
  $("#signup_form").submit(function (e) {
    e.preventDefault();    

    var name = $("#name").val();
    var email = $("#email").val();
    var password = $("#password").val();
    
    $(".error").remove();
    
    // Check the name length, return an error if field is empty.
    if (name.length < 1) {
      $("#name").after(
        '<span class="error">Name is required</span>'
      );
      return;
    }
    
    // Check the email length, return an error if the field is empty.
    // Also run a regex against the email to verify the value is an email.
    if (email.length < 1) {
      $("#email").after('<span class="error">Email is required</span>');
      return;
    } else {
      var regEx = /^([a-zA-Z0-9_\.\-\+])+\@(([a-zA-Z0-9\-])+\.)+([a-zA-Z0-9]{2,4})+$/;
      var validEmail = regEx.test(email);
      if (!validEmail) {
        $("#email").after('<span class="error">Enter a valid email</span>');
        return;
      }
    }
    
    // Check the length of the password value, if empty return an error. 
    if (password.length < 8) {
      $("#password").after(
        '<span class="error">Password must be at least 8 characters long</span>'
      );
      return;
    }
    
    // If form has been filled send the data to a server.
    // In this case we create an alert message
    alert(
      "Name : " +
      name +
      "\n" +
      "Email : " +
      email +
      "\n" +
      "DO SOMETHING WITH THE INFORMATION"
    );
  });
});
```

Let’s describe each part of the code using smaller blocks to understand what is happening within our jQuery code.

### On page load

The jQuery ready function executes the code to only after the DOM is ready in the browser.

```javascript
$(document).ready(function() {
 	//CODE HERE
});
```

### Intercepting the form submission

The form submit is triggered whenever the user clicks the submit button in the form. By using the jQuery `e.preventDefault()` function, the form is not sent to the server automatically, it cancels the default event by not triggering it.<sup id="cite_ref-8"><a href="#cite_note-8">[8]</a></sup> We could then submit it by using the `.submit()` function after successful validation.<sup id="cite_ref-9"><a href="#cite_note-9">[9]</a></sup>  This allows us modify or validate the form data before allowing the data to send. 

```javascript
$('#signup_form').submit(function(e) {
   e.preventDefault();
   //Form dating handling such as modifcation or validation
});
```

### Get fields as variables

The syntax below is the general format in jQuery to select an input value from specific input element.<sup id="cite_ref-10"><a href="#cite_note-10">[10]</a></sup> 

**Syntax**:

```javascript
var fieldName  = $('fieldCSSSelector').val();
```

Below, we use three variables, the `name`, `email`, and `password`. The value of these variables can be set from the input value of their respective fields by using the `.val()` function jQuery.<sup id="cite_ref-11"><a href="#cite_note-11">[11]</a></sup>

```javascript
var name = $("#name").val();
var email = $("#email").val();
var password = $("#password").val();
```

## Form validation

All of the markup, styles, and jQuery functionality is not fixed for the example we demonstrated. You can change the code to fit the needs of you or your organization. Let's go over validating fields and using error messages.

### Checking empty fields

We can use the length attribute to retrieve the character length of the input.<sup id="cite_ref-12"><a href="#cite_note-12">[12]</a></sup> The `name.length` combined with an if statement checks whether the user entered a name. If the user didn’t fill this field with at least 1 character it will show an error message, “Name is required”.

```javascript
// Check the name length, return an error if field is empty.
if (name.length < 1) {
  $("#name").after(
    '<span class="error">Name is required</span>');
  return
```

<figure class="wp-block-image size-large"><img loading="lazy" width="631" height="339" src="https://appcode.app/wp-content/uploads/2022/03/Checking-the-Password-Field-Is-Not-Empty-in-Forms-With-jQuery.png" alt="Checking the Password Field Is Not Empty in Forms With jQuery" class="wp-image-9173" srcset="https://appcode.app/wp-content/uploads/2022/03/Checking-the-Password-Field-Is-Not-Empty-in-Forms-With-jQuery.png 631w, https://appcode.app/wp-content/uploads/2022/03/Checking-the-Password-Field-Is-Not-Empty-in-Forms-With-jQuery-300x161.png 300w" sizes="(max-width: 631px) 100vw, 631px"><figcaption>Checking the Password Field Is Not Empty in Forms With jQuery</figcaption></figure>

The `email.length` if statement checks whether the user entered his email correctly. If the user didn’t fill this field it will show an error message.

```javascript
// Check the email length, return an error if the field is empty.
if (email.length < 1) {
   $("#email").after('<span class="error">Email is required</span>');
   return;
}
```

<figure class="wp-block-image size-large"><img loading="lazy" width="672" height="334" src="https://appcode.app/wp-content/uploads/2022/03/Checking-the-Email-Field-Is-Not-Empty-in-Forms-With-jQuery.png" alt="Checking the Email Field Is Not Empty in Forms With jQuery" class="wp-image-9175" srcset="https://appcode.app/wp-content/uploads/2022/03/Checking-the-Email-Field-Is-Not-Empty-in-Forms-With-jQuery.png 672w, https://appcode.app/wp-content/uploads/2022/03/Checking-the-Email-Field-Is-Not-Empty-in-Forms-With-jQuery-300x149.png 300w" sizes="(max-width: 672px) 100vw, 672px"><figcaption>Checking the Email Field Is Not Empty in Forms With jQuery</figcaption></figure>

Addionally we use the length on the password variable. `password.length` also checks whether a user skipped the password field. The code will show an error message if the password field is less than 8 characters.

```javascript
// Check the length of the password value, if empty return an error.
if (password.length < 8) {
  $("#password").after('<span class="error">Password must be at least 8 characters long</span>'
);
  return;
}
```

<figure class="wp-block-image size-large"><img loading="lazy" width="738" height="378" src="https://appcode.app/wp-content/uploads/2022/03/Checking-the-Password-Field-Is-Valid-in-Forms-With-jQuery.png" alt="Checking the Password Field Is Valid in Forms With jQuery" class="wp-image-9176" srcset="https://appcode.app/wp-content/uploads/2022/03/Checking-the-Password-Field-Is-Valid-in-Forms-With-jQuery.png 738w, https://appcode.app/wp-content/uploads/2022/03/Checking-the-Password-Field-Is-Valid-in-Forms-With-jQuery-300x154.png 300w" sizes="(max-width: 738px) 100vw, 738px"><figcaption>Checking the Password Field Is Valid in Forms With jQuery</figcaption></figure>

### Validate an email address

The **regEx** variable is regular expression to match an email address. There are several variations of the regular expression online.<sup id="cite_ref-13"><a href="#cite_note-13">[13]</a></sup> This expression matches an email address format which allows us to check the validity of input in the email field. 

```javascript
var regEx = /^([a-zA-Z0-9_\.\-\+])+\@(([a-zA-Z0-9\-])+\.)+([a-zA-Z0-9]{2,4})+$/;
```

Using `regEx.test()` returns a Boolean value if there is a match.<sup id="cite_ref-14"><a href="#cite_note-14">[14]</a></sup> The variable `validEmail` will be `false` if the email address is invalid.

```javascript
var validEmail = regEx.test(email);
```

The `!validEmail` if statement checks the Boolean value of the variable. If the variable if `false`, it will show an error message.

```javascript
// Also run a regex against the email to verify the value is an email.
if (!validEmail) {
   $("#email").after('<span class="error">Enter a valid email</span>');
   return;
}
```

### Error messages

We also remove  all prior error messages from the form if the user has already clicked submit once. The `.remove()` jQuery function removes HTML elements.<sup id="cite_ref-15"><a href="#cite_note-15">[15]</a></sup> 

```javascript
$(".error").remove();
```

## Sending form data

In the last section of the jQuery code, you see an alert function containing the name and the email variable. Usually, this section would prepare and send the form data, and the data is typically sent to a server that handles the new user registration.

```javascript
 // If form has been filled send the data to a server.
 // In this case we create an alert message
 alert(
   "Name : " +
   name +
   "\n" +
   "Email : " +
   email +
   "\n" +
   "DO SOMETHING WITH THE INFORMATION"
 );
```

<figure class="wp-block-image size-large"><img loading="lazy" width="1024" height="576" src="https://appcode.app/wp-content/uploads/2022/03/Sending-Form-Data-Using-jQuery-1024x576.png" alt="Sending Form Data Using jQuery" class="wp-image-9178" srcset="https://appcode.app/wp-content/uploads/2022/03/Sending-Form-Data-Using-jQuery-1024x576.png 1024w, https://appcode.app/wp-content/uploads/2022/03/Sending-Form-Data-Using-jQuery-300x169.png 300w, https://appcode.app/wp-content/uploads/2022/03/Sending-Form-Data-Using-jQuery-768x432.png 768w, https://appcode.app/wp-content/uploads/2022/03/Sending-Form-Data-Using-jQuery-1536x864.png 1536w, https://appcode.app/wp-content/uploads/2022/03/Sending-Form-Data-Using-jQuery.png 1920w" sizes="(max-width: 1024px) 100vw, 1024px"><figcaption>Sending Form Data Using jQuery</figcaption></figure>

After validating form data, it is typically sent to be processed somewhere such as a server.<sup id="cite_ref-16"><a href="#cite_note-16">[16]</a></sup> There are several ways to process user-provided data such as using Ajax,<sup id="cite_ref-17"><a href="#cite_note-17">[17]</a></sup> an XMLHttpRequest,<sup id="cite_ref-18"><a href="#cite_note-18">[18]</a></sup> FormData with a form element,<sup id="cite_ref-19"><a href="#cite_note-19">[19]</a></sup> `.post()` jQuery function,<sup id="cite_ref-20"><a href="#cite_note-20">[20]</a></sup> and many other ways.

## See also

- [Form Examples](/css-form-examples-and-code/)
- [jQuery Ajax Contact Form](/how-to-create-a-jquery-ajax-contact-form-in-php/)
- [Creating a Basic Web Form](/creating-a-basic-web-form-with-css-in-minutes/)

## References
<ol>
	<li id="cite_note-1"><span class="cite-backlink"><b><a href="#cite_ref-1" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite>Wikimedia Foundation. (2023, March 23) <a rel="nofollow" href="https://en.wikipedia.org/wiki/HTML_form">HTML form</a>. <i>Wikipedia</i>. Retrieved <span>April 10,</span> 2023</span>.</cite></li>
	<li id="cite_note-2"><span class="cite-backlink"><b><a href="#cite_ref-2" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Baker, K. (2022, September 14).
  <a rel="nofollow" href="https://blog.hubspot.com/marketing/web-forms">Web forms: The ultimate guide</a>. <i>HubSpot Blog</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-3"><span class="cite-backlink"><b><a href="#cite_ref-3" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Educative Answers Team. (2020, August 13).
  <a rel="nofollow" href="https://www.educative.io/answers/what-are-the-different-ways-to-add-jquery-to-our-webpages">What are the different ways to add jQuery to our webpages</a>? <i>Educative</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-4"><span class="cite-backlink"><b><a href="#cite_ref-4" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Staff. (2017, October 24).
  <a rel="nofollow" href="http://web.simmons.edu/~grabiner/comm244/weeknine/including-javascript.html">Including JavaScript In Your Page</a>. <i>Simmons University</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-5"><span class="cite-backlink"><b><a href="#cite_ref-5" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >community wiki. (2012, February 5).
  <a rel="nofollow" href="https://stackoverflow.com/questions/9151861/updating-jquery-version">Updating jQuery version</a>. <i>Stack Overflow</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-6"><span class="cite-backlink"><b><a href="#cite_ref-6" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Refsnes Data. (2000, June 20).
  <a rel="nofollow" href="https://www.w3schools.com/html/html_forms.asp">HTML Forms</a>. <i>w3schools</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-7"><span class="cite-backlink"><b><a href="#cite_ref-7" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Ohans Emmanuel. (2021, July 30).
  <a rel="nofollow" href="https://blog.logrocket.com/how-browser-rendering-works-behind-scenes/">How browser rendering works - behind the scenes</a>. <i>LogRocket Blog</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-8"><span class="cite-backlink"><b><a href="#cite_ref-8" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >OpenJS Foundation. (2010, May 22).
  <a rel="nofollow" href="https://api.jquery.com/event.preventdefault/">event.preventDefault()</a>. <i>jQuery</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-9"><span class="cite-backlink"><b><a href="#cite_ref-9" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >OpenJS Foundation. (2010, May 22).
  <a rel="nofollow" href="https://api.jquery.com/submit/">.submit()</a>. <i>jQuery</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-10"><span class="cite-backlink"><b><a href="#cite_ref-10" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Staff. (2015, August 28).
  <a rel="nofollow" href="https://www.tutorialsteacher.com/jquery/jquery-selectors">JQuery selectors</a>. <i>TutorialsTeacher</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-11"><span class="cite-backlink"><b><a href="#cite_ref-11" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Staff. (2015, August 15).
  <a rel="nofollow" href="https://www.javatpoint.com/jquery-val">JQuery .val()</a>. <i>JavaTpoint</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-12"><span class="cite-backlink"><b><a href="#cite_ref-12" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Staff. (2021, May 15).
  <a rel="nofollow" href="https://www.tutorialspoint.com/jquery-length-property">Jquery Length Property</a>. <i>Tutorials Point</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-13"><span class="cite-backlink"><b><a href="#cite_ref-13" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Millner, R. (2008, August 18).
  <a rel="nofollow" href="https://www.wired.com/2008/08/four-regular-expressions-to-check-email-addresses/">Four regular expressions to check email addresses</a>. <i>Wired</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-14"><span class="cite-backlink"><b><a href="#cite_ref-14" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Staff. (2011, October 13).
  <a rel="nofollow" href="https://www.w3resource.com/javascript/object-property-method/regexp-test.php">JavaScript test() method : Regexp Object</a>. <i>w3resource</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-15"><span class="cite-backlink"><b><a href="#cite_ref-15" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >GeeksforGeeks. (2019, February 13).
  <a rel="nofollow" href="https://www.geeksforgeeks.org/jquery-remove/">JQuery: Remove()</a>. <i>GeeksforGeeks</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-16"><span class="cite-backlink"><b><a href="#cite_ref-16" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Michaelscharnagl. (2021, November 29).
  <a rel="nofollow" href="https://web.dev/learn/forms/form-element/">Use forms to get data from users</a>. <i>web.dev</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-17"><span class="cite-backlink"><b><a href="#cite_ref-17" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >EDUCBA. (2022, July 26).
  <a rel="nofollow" href="https://www.educba.com/jquery-ajax-formdata/">JQuery ajax formdata: How does ajax formdata work in jQuery</a>. <i>EDUCBA</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-18"><span class="cite-backlink"><b><a href="#cite_ref-18" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Wikimedia Foundation. (2005, May 7).
  <a rel="nofollow" href="https://en.wikipedia.org/wiki/XMLHttpRequest">XMLHttpRequest</a>. <i>Wikipedia</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-19"><span class="cite-backlink"><b><a href="#cite_ref-19" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >Ilya Kantor. (2021, June 22).
  <a rel="nofollow" href="https://javascript.info/formdata">Formdata. The Modern JavaScript Tutorial</a>. <i>javascript.info</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
	<li id="cite_note-20"><span class="cite-backlink"><b><a href="#cite_ref-20" aria-label="Jump up" title="Jump up">^</a></b></span>&nbsp;<cite >freeCodeCamp.org. (2021, April 28).
  <a rel="nofollow" href="https://www.freecodecamp.org/news/jquery-ajax-post-method/"> JQuery Ajax Post method</a>. <i>freeCodeCamp</i>.
  Retrieved <span>April 10,</span> 2023</span>.
</cite></li>
</ol>
