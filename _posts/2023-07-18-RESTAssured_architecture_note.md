---
title: "Summary of the REST-Assured project"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - RESTAssured
  - Java
  - Architecture
---

Finally, I've implemented the missing part of the RestAssuredFromScratch project. From now on it is possible to write tests 
which have different RequestSpecification varying in each test methods. So for instance my framework supports a scenario like the following:

- authenticate (get a token needed within all the subsequent calls)
- get list of all my previous orders within a date range, and notice a particular orderId
- having this orderId, list all the items within this order
- pick one item from the order (an item I want to buy once again)
- using the itemID noted from the previous step, place a new order for that product
- check whether the order has been correctly added.

Despite the fact that it may break some best-practises (one test method depends on another), in some situations it might be useful.
<!--more-->
Here is also a summary of the conceptual work I have done. As mentioned earlier, I wanted to implement a support to two "types" of tests:

- simple "one test method per test class" tests
- "flexible" tests, with many test methods per class, each using a different endpoint, to support a scenario as above. 

The final class structure is presented in the UML below:

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/RAFS_architecture_UML.png" alt="UML diagram of the RESTAssuredFromScratch framework">

<!--more-->

As an interesting fact, I can also mention that I had to deal with a couple of problems which arose during the development. 
One of them is the fact, that the JsonPath syntax which is built-in the RESTAssured is de facto GPath syntax. So finally I was able 
to make the test flow work, however the whole topic: "Difference between JayWay's JsonPath and GroovyPath" is worth to have
a separate article on it.

<!--more-->

If only you wish to have such test framework created within your organization, please contact me via phone: **(+48)601647586**,
or email: **adam.saj@wp.pl**.
In case you would like to review the whole project, please let me know as well, with your GitHub username.
Then I will share the repo with you for your review.

<!--more-->

As usual, any comments, feedback, thumbs-up's, criticism are greatly welcomed.
<!--more-->
Stay tuned, I'm still developing the project, adding to it more and more features.
