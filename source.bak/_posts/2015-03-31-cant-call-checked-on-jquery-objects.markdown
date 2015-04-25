---
layout: post
title: "Apparently You Can't Call .checked On a jQuery Object"
date: 2015-03-31 22:46:07 -0400
comments: true
categories: javascript
---
Is the `.checked` property not working for you? It could be because you are using a jQuery object. You can't call `.checked` on a jQuery object.

Well, you can.

But if you do, you will lose 25 mintues to thinking that you must have a typo somewhere, and/or that you are just doing it wrong. And at the end of the 25 minutes, you will discover that you have two options: (1) use plain old vanilla JavaScript, or (2) use jQuery's `.get()` to retrieve the actual DOM object.

Thank the JavaScript deities for other programmers. After 25 minutes of thinking that I was taking crazy pills, <a href="http://stackoverflow.com/questions/3334935/checked-true-not-working-with-jquery-function" target="_blank">this Stack Overflow question</a> ended up saving me.

I knew this newfangled jQuery library was going to be trouble right from the start...
