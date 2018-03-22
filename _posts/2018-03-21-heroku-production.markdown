---
layout: post
title:      "Troubleshooting Heroku Deployment, Part II"
date:       2018-03-21 21:34:11 +0000
permalink:  heroku_production
tags: heroku
---
![](https://www-assets0.herokucdn.com/assets/platform/diagram-1468b013f73d655d92a827440969487d64c2e469398cd01783101bf79d18ab8a.png)

Circling back to my [frontend React project with a Rails backend](https://github.com/IsabelVazquez/React-Redux), I was alerted that no images were able to be seen or saved. Here's what I did to solve this problem.

1. Pull the latest code from the Heroku repository to my local copy and ran `npm start`.
2. Since I could sign-in from both development and production environments, the Rails backend was sending and receiving requests. However, `MenuItem` and `DropdownButton` from Bootstrap were not letting me see the menu on either environment. While this is still a problem, I ended up adding `display: block` to `.dropdown-menu` to make image requests to the backend.
3. I also re-stylized the footer and vote button as the heart glyphicon was not supported anymore. While some things were moderately fixed, other elements were finally given a proper upgrade.
4. At a certain point, the development environment was rendering as intended. Once deployed to Heroku, the production environment remained unchanged.
5. I ended up altering the Rails backend to accept any origins, not just `localhost:3000` and the original Heroku URL, and deploying a new Heroku site with the same frontend code. This did end up showing the same site I was seeing in my local copy.
6. Lastly, I set up a [maintenance page](https://devcenter.heroku.com/articles/maintenance-mode) on the old site with [the new working site](https://imgurtest.herokuapp.com/).

Although I'm glad that I found some solution to at least show the code live, I am concerned about future deployments not rendering correctly. However, this quickfix is one way to continue coding and demonstrating the project.
