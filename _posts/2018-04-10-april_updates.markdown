---
layout: post
title:      "C#/.NET and Heroku Updates"
date:       2018-04-10 14:02:11 +0000
permalink:  april_2018
tags: heroku NET-framework
---
![](https://www.howtogeek.com/wp-content/uploads/2016/05/net_top-650x300.png)
While I have no experience with a .NET stack, .NET is very prominent in the DFW tech market. Below are some keywords to know before diving into tutorials.
* C# - backbone for entire .NET development
* Entity Framework - Recommended ORM for .NET development
* ASP NET MVC - #1 web development framework for .NET developers

In response to my [Heroku troubleshooting post](heroku_production), I found the issue to be no support for Bootstrap's CSS and JavaScript that makes the [dropdown toggling possible](https://www.w3schools.com/bootstrap/bootstrap_dropdowns.asp). Locally, my application relied on the node_modules folder. However, once I added [CDN links](https://getbootstrap.com/docs/3.3/getting-started/) on the `public/index.html`, both Heroku and local versions worked.

This is a very short post given other priorities this month. However, I hope to at least share some coding bits and know-how in the future. 
