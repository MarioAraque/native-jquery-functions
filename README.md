Native jQuery functions
=======================

I think there are many developers who don’t realize that most of the jQuery methods they use have native equivalents that require the same or only a slighter larger amount of code to use. 

Here are a series of code samples showing some popular jQuery functions along with their native counterparts.

Table of contents
================

* [Broser support](#support)
* [Selectors](#selectors)
* [DOM Manipulation](#dom)
* [Events](#events)
* [AJAX](#ajax)
* [Moving into DOM](#moving)

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

```javascript
/* jQuery */
$('div');

/* Native equivalent */
document.getElementsByTagName('div');
```
* Get elements by class

```javascript
/* jQuery */
$('.class-name');

/* Native equivalent */
document.querySelectorAll('.class-name');

/* Another faster native equivalent */
document.getElementsByClassName('class-name');
```
* Get elements by CSS selector

```javascript
/* jQuery */
$('.my-class .my-second-class');

/* Native equivalent */
document.querySelectorAll('.my-class .my-second-class');
```
* Get first element by CSS selector

```javascript
/* jQuery */
$('.my-class').get(0);

/* Native equivalent */
document.querySelector(".my-class");
```
* Get element by id

```javascript
/* jQuery */
$('#some-id');

/* Native equivalent */
document.getElementById('some-id');
```

<a name="dom"></a>
DOM Manipulation
================

* Append HTML elements

```javascript
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

```javascript
/* jQuery */
$('body').prepend("<div id='div-id'></div>");

/* Native equivalent */
var newDiv = document.createElement("div");
newDiv.id = "div-id";
document.body.insertBefore(newDiv, document.body.firstChild);
```
* Manipulate CSS classes

```javascript
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

```javascript
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

* Clone element

```javascript
/* jQuery */
var elementCloned = $('.some-class').clone();

/* Native equivalent */
var elementCloned = document.querySelector('.some-class').cloneNode(truecli);
```

* Set Attributes to element

```javascript
/* jQuery */
$('.some-class').attr('data-attr', 'attr');

/* Native equivalent */
document.querySelector('.some-class').setAttribute('data-attr', 'attr');
```

* Remove Attributes to element

```javascript
/* jQuery */
$('.some-class').removeAttr('data-attr');

/* Native equivalent */
document.querySelector('.some-class').removeAttribute('data-attr');
```

* Get Attributes to element

```javascript
/* jQuery */
console.log($('.some-class').attr('title'));

/* Native equivalent */
console.log(document.querySelector('.some-class').getAttribute('title'));
```

<a name="events"></a>
Events
======

* Document Ready

```javascript
/* jQuery */
$(document).ready(function() {
  // Some stuff
});

/* Native equivalent */
document.addEventListener("DOMContentLoaded", function() {
  // Some stuff
}, false);
```

* Event listeners

```javascript
/* jQuery */
$(someElement).on('click', function(){
  console.log('click');
});

/* Native equivalent */
someElement.addEventListener("click", function() {
  console.log('click');
}, false);
```

<a name="ajax"></a>
AJAX
====

```javascript
/* jQuery */
$.ajax({
	url: "url",
	type: "POST",
	data: "a=1&b=2&c=3",
	success: function(response) {
		console.log(response);
	}
});

/* Native equivalent */
var r = new XMLHttpRequest(); 
r.open("POST", "url", true);
r.onreadystatechange = function () {
	if (r.readyState != 4 || r.status != 200) return; 
	console.log(r.responseText);
};
r.send("a=1&b=2&c=3");
```

<a name="moving"></a>
Moving into DOM
===============

* Get parent node

```javascript
/* jQuery */
$('.some-class').parent();

/* Native equivalent */
document.querySelector('.some-class').parentNode;
```

* Get the next node

```javascript
/* jQuery */
$('.some-class').next();

/* Native equivalent */
document.querySelector('.some-class').nextSibling;
```

* Get the previous node

```javascript
/* jQuery */
$('.some-class').prev();

/* Native equivalent */
document.querySelector('.some-class').previousSibling;
```

* Get the first child element

```javascript
/* jQuery */
$('.some-class').find('>:first-child');

/* Native equivalent */
document.querySelector('.some-class').children[0];
```

* Get the last child element

```javascript
/* jQuery */
$('.some-class').find('>:last-child');

/* Native equivalent */
document.querySelector('.some-class').lastElementChild;
```
