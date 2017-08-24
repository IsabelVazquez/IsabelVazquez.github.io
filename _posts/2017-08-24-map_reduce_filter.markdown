---
layout: post
title:  "Map, Reduce, Filter?"
date:   2017-08-24 04:54:59 +0000
---


![](http://api.ning.com/files/-3i3rVffQH2bautHoYhtuyn-BhEFBMR3TNXJzACS9ATLysgH7VID6G3-DRqv65rcjsIwZ7riHJZ9rtS9XGWzIc326dpaeNvF/bor55.PNG) Let's say that we have an array of vegetables that we want to use for our sandwich. Filter would make a new array of vegetables that we do like. Map would be the chopping that happens to each vegetable. Reduce would adding all the ingrediants to one sandwich or value. However, our original array of vegetables would remain the same. Below are some examples of the copying and manipulation of arrays through map, filter, and reduce methods.

```
var numbers = [1, 2, 3, 4];

var doubledNumbers = numbers.map(n => n * 2); // [ 2, 4, 6, 8 ]

var evenNumbers = numbers.filter(n => n % 2 === 0); // [ 2, 4 ]

var total = numbers.reduce((acc, cur) => acc + cur, 0); // 10

```

To expand more on the reduce method above, the acc accumulates all of the values added in our function and with the initial value of 0. Cur is then numbers[0] or 1. However, if no initial value is given, acc is the first value, numbers[0], and val is the next value. With this in mind, reduce can change immutable data structures from an array to an object, **both different variables**! 

```
var indexedNumbers = numbers.reduce(function(acc, val, index) {
  acc[index] = val;
  return acc;
}, {}); // { 0: 1, 1: 2, 2: 3, 3: 4 }
```

In the reduce example above, the initial value of acc is {} and we insert key-value pairings into this empty hash. 

The most important thing from this post is that all of these methods leave the original array *numbers* unaltered. 

Thanks to this [talk](https://www.youtube.com/watch?v=e-5obm1G_FY) for the sandwich metaphor and [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) for helping out with this post. 
