---
title: "My work samples"
header:
  teaser: assets/images/unsplash-gallery-image-1-th.jpg
---

I prepared also a simple version of the API-testing framework, using REST-Assured framework, and a few related libraries. Within the framework I use for instance: 
* JSONObjectBuilder
* RequestSpecBuilder

To make the test setup a little bit easier. Within this project I will support 2 types of tests. I call them 'global', and 'indyvidual':
* 'Global' - tests, where the tester will have one global RequestSpecification for the entire test-class. There will not be any possibility to amend them within the class - all test-methods will have the same (paths, headers etc).
* 'Local' - where there will be possibility to define different RequestSpecification per indyvidual test method within test class. I see this helpful in a scenario, where one call can consume an output from another, with different for instance: request type, or path.
* 
Here is the [link](https://github.com/AdamSajewicz/RESTAssuredFromScratch "REST-Assured project built from scratch")

As a "system under tests" I used a simple demo RESTful webservice, which is under a link: https://restful-booker.herokuapp.com.
