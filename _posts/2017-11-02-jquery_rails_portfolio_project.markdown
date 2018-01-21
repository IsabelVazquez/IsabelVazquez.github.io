---
layout: post
title:      "JQuery/Rails Portfolio Project"
date:       2017-11-02 16:22:04 -0400
permalink:  jquery_rails_portfolio_project
tags: ruby-on-rails jquery javascript
---


When starting this part of the [Rails project](https://github.com/IsabelVazquez/recipe-app), I appended the HTML from the partials or forms to the show and index pages. While this utilizes JQuery, it falls short of creating stable data in the JSON format. APIs utilize JSON format instead of HTML because of the access and logic with hashes. By accessing hashes of recipe and item data, I was then able to create Javascript Model Objects.
```
// JS Model Object
function Item(item) {
  this.id = item.id
  this.name = item.name
  this.measurement = item.measurement
  this.quantity = item.quantity
}
// Prototype method
Item.prototype.formatItem = function() {
  let recipeHTML = `<li data-id=${this.id}>${this.quantity} ${this.measurement} - ${this.name}</li>`
  return recipeHTML
}
```
Once JSON responses were translated into JS model objects, side effects were the next priority. Rendering data with clicks sans page refresh meant that a lot of attribute values needed to prevent duplication and be replaced. The has-many relationship between Recipe and Items on the recipe page kept rendering the same instance of Items with repeated clicks. I also ended up seeing all the items of previous recipes when sifting through the recipes. Therefore, on both Recipes and Items.js files, the href attribute of “See The Items” link was altered to have no value or the value of `${nextRecipeId}/items`.

Although I implemented the requirements twice, once with appending HTML and then with JSON responses and JS Model objects, I’m glad to have grown more comfortable with jQuery and interactive websites.
