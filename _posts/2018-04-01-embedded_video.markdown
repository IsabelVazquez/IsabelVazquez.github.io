---
layout: post
title:      "Embedded Video in Background"
date:       2018-04-01 18:34:11 +0000
permalink:  embedded_video
tags: design ux
---
![](https://premium.wpmudev.org/wp-content/uploads/2011/03/oembed-thumb-1470x940.png)
When thinking about design, I’ve noticed that websites are implementing animation and movement. An introductory step into implementing more movement is having an embedded video on a web page. I have modified the code below but wanted to share how to overlay text on a background video.

```
<header>
  <div class="navbar">
    <a class="navbar-brand" href="#">
      <img src="img/example.png" width="40" height="40" class="d-inline-block align-top" alt="Logo">
    </a>
  </div>

  <div class="vimeo-wrapper">
    <iframe src="https://player.vimeo.com/video/VimeoNumber?background=1&autoplay=1&loop=1&byline=0&title=0"
   frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
  </div>

  <div class="overlay">
    <h1>Sample Text</h1>
    <img src="img/image.png" class="img-thumbnail" alt="Image" />
    <a href="#" class="btn btn-warning btn-lg">Learn today</a>
  </div>
</header>
```

Below is the CSS to achieve a clean design and responsiveness.
```
/* Footer/Navbar: Video */
.vimeo-wrapper {
   position: relative;
   top: 0;
   left: 0;
   width: 100%;
   height: 485px;
   z-index: -1;
   pointer-events: none;
   overflow: hidden;
}
.vimeo-wrapper iframe {
   width: 100vw;
   height: 56.25vw; /* Given a 16:9 aspect ratio, 9/16*100 = 56.25 */
   min-height: 100vh;
   min-width: 177.77vh; /* Given a 16:9 aspect ratio, 16/9*100 = 177.77 */
   position: relative;
   top: 50%;
   left: 50%;
   transform: translate(-50%, -50%);
}

/* Footer/Navbar: Overlay */
.overlay {
  background: rgba(0,0,0,0);
  position: absolute;
  top: 0; right: 0; bottom: 0; left: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index:1;
}
.overlay h1 {
  color: #ffc800;
  font-size: 55px;
}
.overlay .img-thumbnail {
  max-width: 200px;
  border: none;
  background: none;
  background-color: none;
  border-color: none;
}
```

A future iteration of such a web page would implement visual transitions between sections like this [website](http://taotajima.jp/).
