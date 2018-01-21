---
layout: post
title:      "Fetch API and Asynchronous JS "
date:       2017-11-30 18:26:57 -0500
permalink:  fetch_api_and_asynchronous_js
tags: javascript
---


I currently have the following React component
```
callApi = () => {
    console.log('a')
    const credentials = {
      user_id: JSON.parse(localStorage.getItem('user')).id
    }
    const request = new Request(API_URL+'images', {
      method: 'POST',
      headers: new Headers({
        'Content-Type': 'application/json'
      }),
      body: JSON.stringify({image: credentials})
    });
     fetch(request)
      .then(response => {
        console.log('b')
        return response.json()
      })
      .then(data => console.log('c',data))
      console.log('d')
      console.log('e')
  }

render() {
  return (
    <div>
      <Button onClick={ this.callApi }>Call Api</Button>
    </div>
  )
}
```
which results to this when clicked:

![](https://i.imgur.com/B5XJz6n.png)

`console.log('d')` and `console.log('e')` fire off before the fetch() request finishes. Synchronous code would have each line of code run in order as soon as the previous line executed. However, asynchronous code, the fetch API in this case, does not pause data. Instead, the chained .then() functions run async actions in sequence once the server responds.

The Fetch API takes in a path with optional settings, `const request`, and returns a promise, *an object representing the eventual completion or failure of an asynchronous operation.* The response from this promise is utilized by .then() and .catch() for error handling.

Overall, I would definitely recommend extra reading for understanding asynchronous code as it's crucial with JS requests.
