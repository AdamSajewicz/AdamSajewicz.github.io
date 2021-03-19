Finally I finished the base of the Selenium project. It's a sample project presenting my way of creating a suite of automated tests. 

<!--more-->

As a "system under tests" I used the **ParaBank** project. It's a kind of test-bank. It's not a real bank, just a demo. More info you may found [here](https://parabank.parasoft.com/parabank/about.htm)

<!--more-->

Within this project I used:
* **Page Object Model** design pattern
* **Page Factory** design pattern
* **Fluent Interface** design pattern
* **TestNG** as a test management framework
* Reading test configuration from an XML file
* Separate **Page** classes and **Assertions** classes
* Easy switching from Page to it's asertions

<!--more-->

Here is a screenshot taken from the first run of the "ParaBankLoginTest"

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/paraBankHomePage-testRun.png" alt="ParaBankLoginTest run screenshot">

And that is how it looks like from the JntelliJ's console perspective:

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/paraBankHomePage-console.png" alt="ParaBankLoginTest run console">

<!--more-->

The source code you may find on [my GitHub](https://github.com/AdamSajewicz/SeleniumFromScratch)
