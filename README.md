Native jQuery functions
=======================

I think there are many developers who don’t realize that most of the jQuery methods they use have native equivalents that require the same or only a slighter larger amount of code to use. 

Here are a series of code samples showing some popular jQuery functions along with their native counterparts.

Table of content
================

* [Broser support](#support)
* [Selectors](#selectors)
* [DOM Manipulation](#dom)

<a name="support"></a>
Browser support
===============

* IE9+
* Firefox 3.5+
* Firefox Mobile
* Opera 9+
* Opera Mobile
* Safari 4+
* Chrome 1+
* iPhone and iPad iOS1+
* Android 2.1+

<a name="selectors"></a>
Selectors
=========

* Get all divs on a page. Valid for all html tags

```
/* jQuery */
$('div');

/* Native equivalent */
document.getElementsByTagName('div');
```
* Get elements by class

```
/* jQuery */
$('.class-name');

/* Native equivalent */
document.querySelectorAll('.class-name');

/* Another faster native equivalent */
document.getElementsByClassName('class-name');
```
* Get elements by CSS selector

```
/* jQuery */
$('.my-class .my-second-class');

/* Native equivalent */
document.querySelectorAll('.my-class .my-second-class');
```
* Get first element by CSS selector

```
/* jQuery */
$('.my-class').get(0);

/* Native equivalent */
document.querySelector(".my-class");
```

<a name="dom"></a>
DOM Manipulation
================

* Append HTML elements

```
/* jQuery */
$('body').append("<div id='div-id'></div>");

/* Native equivalent */
document.body.innerHTML += "<div id='div-id'></div>";

/* Much better native equivalent */
var newDiv = document.createElement("div");
newDiv.id = "div-id";
document.body.appendChild(newDiv);
```

* Prepend HTML elements

```
/* jQuery */
$('body').prepend("<div id='div-id'></div>");

/* Native equivalent */
var newDiv = document.createElement("div");
newDiv.id = "div-id";
document.body.insertBefore(newDiv, document.body.firstChild);
```

* Manipulate CSS classes

```
//Default variable
var element = document.querySelector(".element");

//Check if element has some class
/* jQuery */
if($(element).hasClass("new-class")){}

/* Native equivalent */
if(element.classList.contains("new-class"))

//Add class
/* jQuery */
$(element).addClass('new-class');

/* Native equivalent */
element.classList.add("new-class");

//Remove class
$(element).reveceClass('new-class');

/* Native equivalent */
element.classList.remove("new-class");

```

* Manipulate CSS properties

```
//Default variable
var element = document.querySelector(".element");

/* jQuery */
$(element).css({
  width: '200px',
  height: '250px',
  background: 'solid 1px red'
});

/* Native equivalent */
element.style.width = '200px';
element.style.height = '250px';
element.style.background = 'solid 1px red';
```
