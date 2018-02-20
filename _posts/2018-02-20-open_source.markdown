---
layout: post
title:      "A Beginner’s Guide to Contributing to Open Source "
date:       2018-02-20 11:50:11 -0500
permalink:  open_source
tags: open-source ruby-on-rails
---
![](https://i.imgur.com/CdZTO5o.png)
After having my first merged pull request, I wanted to share my experience for anyone looking into open source or building their skills. For me, contributing to open source was a better opportunity to continue coding without building a portfolio project from scratch. I wanted the chance to understand other people’s code and see how I could contribute. Ruby is the first coding language that clicked and while I haven’t touched Rails in a few months, I wanted to see how quickly it could come back to me.

## Resource
I am thankful for this Twitter bot [first-timers-only](https://twitter.com/first_tmrs_only) where I found a Rails repository with well-documented issues.

## Advice
*  **Always find and read a contributing guide**

Although GitHub repositories likely have a license and an openness to contributions, I would recommend finding one with explicit instructions and an active community. This makes claiming an issue, setting up your developer environment, and responding to code changes smoother.
*  **Pick a repository in your strongest language**

There is confidence when reading other people’s code and understanding what they are trying to do. But if you’re up for a challenge, definitely go for repositories with languages you would like to learn. In this case, first-timer-only issues are highly recommended.
* **`git remote add <name> <remote_url>` and `git pull <remotename> <branchname>`**

After forking and cloning, `origin` is set up to your `USERNAME\REPOSITORY`. This means that any time you call `git pull`, you are comparing your local copy to your GitHub copy. It’s good practice to `git pull` before working on your local copy. But in order to work with the latest code from the actual repository, I set up a remote and pulled from that remote’s master branch.
* **Ask questions**

Becoming more familiar with the requirements and testing suite is crucial. I now ask before diving into issues with assumptions. See if the repository has active project managers. They are often familiar with the repository’s requirements and foster good coding practices.

## Next Steps
I’m currently tackling another first-timer issue as my pull request needs changes. Due to my positive experience, I am also starting a non-first-timer issue soon. Happy coding!
