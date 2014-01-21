Native jQuery functions
=======================

I think there are many developers who don’t realize that most of the jQuery methods they use have native equivalents that require the same or only a slighter larger amount of code to use. 

Here are a series of code samples showing some popular jQuery functions along with their native counterparts.

Table of content
================

* [Broser support](#support)
* [Selectors](#selectors)

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
