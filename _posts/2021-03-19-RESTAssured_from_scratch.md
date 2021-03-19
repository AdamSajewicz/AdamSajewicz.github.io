---
title: "Java Selenium project from the ground up"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - RESTAssured
  - Java
  - TestNG
---


Today I finished a simple project with REST-Assured. It's not only a demo presenting my approach to the API testing with this framework, but maybe a base for other projects. Maybe for instance: REST-Assured with Serenity, maybe: adding REST-Assured module to the Selenium project, or: a fundamental for a project where I could present usage of mocking external services, like: WireMock. 

<!--more-->

As a "system under tests" I used the **RESTful booker** project. More info you may found [here](https://restful-booker.herokuapp.com)

<!--more-->

Within this project I used:
* **RequestSpecBuilder**
* **JSONObjectBuilder**
* **Fluent Interface** design pattern
* **TestNG** as a test management framework


<!--more-->


The source code you may find on [my GitHub](https://github.com/AdamSajewicz/RESTAssuredFromScratch)
