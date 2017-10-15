---
layout: post
title:      "Sinatra Portfolio Project"
date:       2017-10-15 19:10:18 +0000
permalink:  sinatra_portfolio_project
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
