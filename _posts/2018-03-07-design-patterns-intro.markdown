---
layout: post
title:      "Design Patterns: Intro"
date:       2018-03-07 17:18:11 -0500
permalink:  design_patterns
tags: design
---
In web design, I have mostly used the Model-View-Controller pattern and wanted to learn about other design patterns.

## Factory
Creational: objects

This is arguably not a pattern but still important due to encouraging DRY code. Isolate the creation of an object from the code - not dependent on an instance of an object as there is always a factory coming out with objects. In JavaScript, my constructor has typically been included in an closure. However, the Factor pattern encapsulates the constructor in one place that only refers to classes.

## Singleton
Creational: objects

This pattern has one global instance of a class but with access to that one instance. Due to warnings about having global variables and interfering with unit testing, Singleton is not liked as much as other patterns.

## Resources
I highly recommend [this resource](https://www.tutorialspoint.com/design_pattern/index.htm) for coding samples and greater details on a variety of design patterns.
