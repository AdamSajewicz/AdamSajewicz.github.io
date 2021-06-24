---
title: "Java Selenium project from the ground up"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Selenium
  - Java
  - TestNG
  - Page Object Model
---

Recently I made also some major updates to the *Selenium From Scratch* project. The changes include:
* few new test scenarios
* added the another level of pages (ParaBankPage.java), which contains just the frames and meus of the ParaBank. The menus are common across all other pages, so I extracted them to the separate class.
* Few *helper* methods like 'waitForPageToLoad', which contains checking whether the document is in 'Ready' state.
* a method for *fluentWait*
* a method for refreshing the page while waiting for an element to be visible.

Full source code of the project can be found there: [Selenium Project](https://github.com/AdamSajewicz/SeleniumFromScratch)

<!--more-->
