---
layout: post
title:      "Continuous Integration"
date:       2018-01-31 23:11:11 -0500
permalink:  continuous_integration
tags: continuous-integration travis-ci
---

I recently added Travis CI successfully to my static personal site.

This showed up multiple times on my CI build as I did not exclude vendor on my `_config.yml` file.

![Imgur](https://i.imgur.com/7yLPyJS.png)

I also ran my CI script locally while comparing to the Travis build. Once I excluded vendor, both builds showed the following errors with internal scripts on HTML files. I ended up modifying the htmlproofer constructor to only check problems with external references: `bundle exec htmlproofer --assume-extension --external_only --only-4xx --http-status-ignore "403,429" ./_site`

![Imgur](https://i.imgur.com/5LBnyj8.png)

17th time is the charm!

![Imgur](https://i.imgur.com/vyfPlqO.png)

Continuous integration is the immediate and daily integration of code into one shared repository that involves developers checking-in before sending the code to an automated build, often with testing suites included. The CI server then follows the build scripts and goes green for passing or red for failing, complete with log messages.

On my personal site, I am the sole developer and do not have tests at the moment or any formal check-in process. But I enjoyed bringing Travis CI to my repository because I
* got a brief introduction to CI practices
* became acquainted with writing scripts, thanks to [this documentation on Jekyll](https://jekyllrb.com/docs/continuous-integration/travis-ci/)
* was introduced to checking the DNS, site build, and HTML files automatically

Cheers to good developer practices and happy coding!
