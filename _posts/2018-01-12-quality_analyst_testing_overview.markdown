---
layout: post
title:      "Quality Analyst/Testing Overview"
date:       2018-01-12 13:48:48 -0500
permalink:  quality_analyst_testing_overview
---


When coding, it’s important to be aware of what everyone does and a big part of the software development life cycle is testing. This is a broad overview of different types of testing and tools available. 

**Testing Pyramid**
![Ideally, testing will mostly be concentrated in low cost unit tests, followed by integration tests and very few functional tests. ](https://i2.wp.com/saeedgatson.com/wp-content/uploads/2015/10/idealautomatedtestingpyramid.png )

Unit tests are about testing the lowest possible “unit.” For example, let’s say  you were making a PB&J sandwich. Testing the creation of a sandwich at a low level requires you to check that you have all the ingredients. Unit tests typically check variable or function assertions (i.e. obj1.nil? is false).

Integration tests are about testing the interaction between “units.” This testing often involves input and output parameters with database, API, and other dependencies.

Functional tests are about testing the entire application from a user perspective. Functional questions involve successful requests, redirection, authentication, and appropriate user messages from end-to-end.

**Testing Quadrant**
![The testing quadrant can help teams think about their goals and what test types are conducive to those goals. ](http://lisacrispin.com/wp-content/uploads/2011/11/Agile-Testing-Quadrants.png )

**Tools**
* [Selenium IDE](http://www.seleniumhq.org/projects/ide/) - Although only available as a Firefox extension, Selenium IDE is GUI-oriented and can be used to automatically go through XPaths and confirm that links and targets work. If you’re not comfortable with writing tests, TDD, or code, you can easily tinker with it and get a sense of testing. 
* [Mind Maps](http://lisacrispin.com/wp-content/uploads/2011/02/ABFTestingMindmap.jpg) - I think these are great to use in an individual or group basis. They allow for easy, nimble participation and are a starting point for thinking of test scenarios. If coding or testing are not in your toolbox, mind maps are also a recommended introduction into testing. 
* [Postman](https://www.getpostman.com/ ) - This is great for testing and building API requests. I have definitely used this to confirm my understanding of API documentation and implement a request correctly. 
* [Selenium WebDriver](http://www.seleniumhq.org/projects/webdriver/) - I have not used WebDriver but constantly hear about it. 
* Pair programming - Different teams and projects vary on how testing and code is implemented but having other team members and testers pair up at any level of the testing pyramid is recommended. Both bring key perspectives in terms of prioritization, coverage, and edge cases. 

**Realities**
* Even if all tests pass, the application is not defect-free. 
* An application is never 100% tested and cost vs. value needs to be considered.
* Realistic data is often confidential and therefore hard to mimic. 

**Resources**
* [Lisa Crispin](http://lisacrispin.com/) - People always recommend her books and blog to learn more about testing. 
* [QAShahin](https://www.youtube.com/user/GlassBoxT ) - This YouTube channel is solely dedicated to QA content.
* [WaterMelon](https://watirmelon.blog/) - This blog provides in-depth content about testing that describes specific approaches and security concerns.


