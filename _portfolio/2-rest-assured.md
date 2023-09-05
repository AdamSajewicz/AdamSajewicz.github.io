---
title: "Sample REST-Assured Project"
header:
  teaser: assets/images/REST-assured.png
---

Apart from the Selenium project, I have created an API-testing framework. I am using REST-Assured there, and a few related libraries. 
Within the framework I use for instance: 
* JSONObjectBuilder
* RequestSpecBuilder
* Java LTS version (17)
* Separation the test scenarios from the framework itself.

What is interesting within this project, I have prepared two 'types' of tests there. One support a simple test cases,
validating only one thing, one result parameter. The other allow a tester to create more robust test cases, where for instance
a response from one webservice call have to use the output from the other. As an example you may imagine a situation,
where in order to retrieve a certain value you must call for an authentication token first.

As a "system under tests" I used a simple demo RESTful webservice, which is under the link: https://restful-booker.herokuapp.com.
>Restful-booker is a Create Read Update Delete Web API that comes with authentication features and loaded with a bunch of bugs for you to explore. The API comes pre-loaded with 10 records for you to work with and resets itself every 10 minutes back to that default state. Restful-booker also comes with detailed API documentation to help get you started with your API testing straight away.

When using my RESTAssuredFromScratch framework, the tester is able to write very clean and easy to understand test cases like that:

<script src="https://gist.github.com/AdamSajewicz/6adfb9762e69f3690d680a96a30c9c44.js"></script>

If only you like the way I am writing the tests, please feel free to contact me over the phone or via email. I can create such framework for your company as well
