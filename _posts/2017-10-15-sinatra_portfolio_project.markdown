---
layout: post
title:      "*Updated* Sinatra Portfolio Project"
date:       2017-10-15 15:10:19 -0400
permalink:  sinatra_portfolio_project
tags: sinatra ruby-on-rails
---

This project was a huge reminder in **nested forms** and **helper methods**. While coding my todo app, I was wondering if I could put a form within a form to create a list of items. When I looked back at previous lessons, I was reminded of nested forms. After creating a list with one item, the next challenge was persistence and connecting an item to a list and user correctly. Tux was utilized a lot in order to get this right. I did this by having
```
<form method="post" action=“/items/new/<%=@list.id%>”>
```
and
```
ListItem.create(:description => params[:description], :word_number => params[:word_number], :list_id => params[:id])
```
The second most important component was helpers methods. They were utilized in the controller and views by displaying certain elements only if a user was logged in. Although the controller didn’t allow users to modify other users’ lists, the helper method of logged_in? made the app more user friendly by having less buttons unnecessarily.

As with my previous project, I created the app by asking myself what’s the MVP right now.  That meant creating my database and model configurations first, followed by controller and views. I also purposely did not create all the CRUD erb forms as I wanted something with less links and a smaller user path. Ultimately, a better iteration of this project would be coupled with AJAX to make requests without reloading the page or redirecting elsewhere.

*Update #2*

Going through [RailsGuides](http://guides.rubyonrails.org/association_basics.html) and refactoring, I have integrated the following: `new` instead of `create` and `dependent: :destroy`.

I originally has static error messages since my controllers were creating models. `Model.create` doesn't let me know if I have validations failing. So I implemented `Model.new` with `Model_Instance.save`.  `new ` instantiates objects but doesn't save them. `save` returns true or false depending on whether the Model validations passed or failed. Although both `create` and `new` do not allow bad data to pass due to Model validations, `new` coupled with `save`allows for dynamic error messages.

I also added `dependent: :destroy` to my List Model as I was only deleting lists but not the associated objects, ListItem instances.

So my advice would be to read over RailsGuides on Association Basics to make use of ActiveRecord in your Sinatra project.
