---
layout: post
category: posts
title:  "Oileus - A small frametype for JavaScript"
date:   2015-02-15 11:16:25 +0530
tagline: "Built first javascript framework to write application centric code"
permalink: /post/oileus-a-small-framework-for-javascript/
---
Oileus is small framework and prototype for JavaScript, so called FrameType. This I have written for using in my web applications at core engine of client-side logic. Once I said about something, the construction of this tinny frametype was started at the same time, and time by time code was being re-factored.

This frametype will give you a way to write your code in Object Oriented manner. When I said this it doesn't mean that it's going to give you the concept of class, object, inheritance but my intention to say that statement was that you can divide your code in such simple part which will give you following benefits of OOP style coding.

1. Class based writing
2. Easy to debug
3. Write things which make sense

If we talk a bit about design pattern, it follows VCRM - (View Controller and Remote Model) which has very minor differences from MVC design pattern. Here the controller and view resides at client side and if we look about models, it usually resides at remote location. If we look the architecture of this frametype we'll get local controller, local view but remote models.

It's made on the top of [jQuery](http://jquery.com/) which is mainly designed for maintaining the large blocks of code into simple and manageable code. It comes with simple improvement to the HTML tags, so you can do much more things without writing a bit of JavaScript. :)

There are many popular framework and libraries of JavaScript, you can easily use all those with the Oileus. And currently the dependency of Oileus is on jQuery, which was really a great contribution towards JavaScript by [John Resig](http://en.wikipedia.org/wiki/John_Resig).

Oileus is made on the philosophy that let the programmers write logical code which should solve the problem rather than repetitive code. Here is the list what can be done by Oileus frametype -

1. Manage your code, effectively
2. Single page application
3. If you want to play with ajax(the son of Oileus)
4. Playing with events
5. Use your creativity to draw a dash

Here few things are there, which is common in each web application like Oileus forms, links, activo and many more. Which makes application writing very easy and maintainable. Oileus is an opensource frametype, you can get the code from [github](https://github.com/codingdash/Oileus), and you can use it for free or you can improve. If you find anything to contribute you can do pull request on github. Also if you have any suggestions, it's welcomed at oileus[at]codingdash.com

Want to read about how to use it with your application? Browse a small documentation [here](http://oileus.codingdash.com/).

Happy coding :)