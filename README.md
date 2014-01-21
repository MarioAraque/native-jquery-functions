Native jQuery functions
=======================

I think there are many developers who don’t realize that most of the jQuery methods they use have native equivalents that require the same or only a slighter larger amount of code to use. 

Here are a series of code samples showing some popular jQuery functions along with their native counterparts.

Table of content

* [Selectors](#selectors)

<a name="selectors"></a>
Selectors
=========

1. Get all divs on a page. Valid for all html tags

```
/* jQuery */
$('div');

/* Native equivalent */
document.getElementsByTagName('div');
```
2. Get elements by class

```
/* jQuery */
$('.class-name');

/* Native equivalent */
document.querySelectorAll('.class-name');

/* Another faster native equivalent */
document.getElementsByClassName('class-name');
```
3. Get elements by CSS selector

```
/* jQuery */
$('.my-class .my-second-class');

/* Native equivalent */
document.querySelectorAll('.my-class .my-second-class');
```
4. Get first element by CSS selector

```
/* jQuery */
$('.my-class').get(0);

/* Native equivalent */
document.querySelector(".my-class");
```
