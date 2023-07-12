---
title: "Selenium Project Review"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Selenium
  - Java
  - TestNG
---

I'd like to summarize the results of my recent work on the Selenium project here.
<!--more-->
Since it's creation in 2020 it has got a significant review and refactoring. I migrated it to the latest Java LTS (17),
bumped up most of its libraries, applied the Selenium's 4 WebDriverManager. In addition, I changed the project's structure.
Previously, the whole project, as a test project was in the module 'tests'. That was since this main scope was just 
tests the webapplication deployed completely independently. There were no 'production' code.
<!--more-->
In the new approach, I split the project between the 'main' and 'test' modules. The 'main' one contains abstract classes
and base classes used by tests. For instance a class that allows to switch fluently between the test steps and assertion methods.
On the other hand, the module 'tests' there are all the classes (Tests, Pages, Assertions) which implement the test scenario
itself.
<!--more-->
By this split I handled the separation between the test framework, and the tests scenarios using this framework.
<!--more-->
Let's focus a little bit more on the 'tests' module. Thanks to the Page Object Model, and the method chaining (I call it 'Fluent Interface')
I enabled the possibility to extract and separate three types of objects:
- tests classes (with the postfix 'Test' in their name),
- page classes (postfix: 'Page'),
- assertions (postfix: 'PageAssertions').
In such test framework, test classes might have a package structure following the business logic, and the client's needs. 
On the other hand, pages and assertions can follow the structure of the pages which exist in the application. Here is just one
important remark: since each Page class can have its own Assertions class, their structure must be the same 1:1.
<!--more-->
Thanks to that approach, the tests are very readable / understandable, and their extension modification is extremely easy.
A sample test looks like the following:
<img src="{{ site.url }}{{ site.baseurl }}/assets/images/sfs-example.png" alt="Example Test in the SeleniumFromScratch framework">
<!--more-->
If you would like to have a similar framework in your project, please don't hesitate to contact me;
- phone: (+48) 601647586
- email: adam.saj@wp.pl
<!--more-->
You can also review all other pages from this site, where I present myself a little bit deeper, and also present some of the other projects I lead.
