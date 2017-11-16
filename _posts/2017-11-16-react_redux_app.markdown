---
layout: post
title:      "React + Redux App"
date:       2017-11-16 05:49:10 +0000
permalink:  react_redux_app
---


When starting this React/Redux project, I first created static components that rendered successfully. Although this was not taking advantage of React’s abilities - much less Redux! - working with one static route and data was critical to creating this app.

Copied and pasted from the actual API, static data consisted of an array with 2 object images in my ImageReducer file. This was then passed onto the containers and components. Going through this [React and Redux tutorial](http://www.youtube.com/playlist?list=PL6gx4Cwl9DGBbSLZjvleMwldX8jGgXV6a), the concepts of action, reducer, state, and provider clicked. However, I found myself missing a crucial component: a conditional statement wrapping the .map function. Passing an example below as it was a significant roadblock. 

![](https://i.imgur.com/uOijBNf.jpg)

```
// must wrap .map block with conditional statement
    if (this.props.items) {
      const children = this.props.items.map((item) => (
        <Item key={item.id} item={item} />
      ));
      return (
        <div>
          <ItemList>
            {children}
          </ItemList>
        </div>
      );
    }
```

After setting up other React forms and components, I delved into setting up a Rails API. A critical tutorial that made me understand how to set up and connect the Rails API to the React/Redux app was [this](http://learnetto.com/tutorials/rails-5-api-and-react-js-tutorial-how-to-make-an-idea-board-app). I highly recommend it. Although the React app can call an external API such as Imgur's, you typically want to **make APIs on the backend as you can find security tokens in the source code of the browser in client JS code**. 

I still have some ways to go with this [project](http://github.com/IsabelVazquez/React-Redux), but I wanted to share my process and some incredible resources. 
