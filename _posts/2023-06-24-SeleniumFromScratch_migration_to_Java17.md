---
title: "Selenium From Scratch project upgrade to Java 17"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Selenium
  - Java
  - TestNG
---

Today's a big moment for the **Selenium From Scratch** project: the big update.
I've wanted to upgrade it somehow for a long time. Having considered a few options, whether to do it using a step-by-step approach,
or maybe only to a certain Java's release I decided to go for **maximum** strategy. This mean to rebuild it with the newest possible 
libraries.
<!--more-->
I have chosen **Java 17** (Coretto), which is the current LTS java's version. Other dependencies were upgraded as well:
* Selenium -> to version 4.10.0
* TestNG -> to version 7.8.0
* REST-Assured -> to version 5.3.1
Interesting fact I've learned during the upgrade is that Lombok library is now bundled with the IDE itself, so no need to install 
any special plugin for that (I'm using IntelliJ 2023.1.2)
<!--more-->
As usual with such upgrades, not all things went as smoothly as planned. The most weird problem I've encountered was the
Annotation Processor, and the compilation message:

    <code>[WARNING] Supported source version 'RELEASE_6' from annotation processor 
        ...
        less than -source '17'
    </code>
Even after following the solution instructions from this article at [Bealdung](https://www.baeldung.com/lombok-ide#intellij-apt) 
haven't made things better. The generated getters still were unrecognized by the IDE. In my case, the following actions helped:
1. Invalidate caches in the IDE,
2. Build the project anew,
3. Go to any of the not-working getters, hover on it, and from the 'quick-fix' menu choose <code>add Lombok to classpath</code>
After this, all somehow has clicked and I got a successful build.
<!--more-->
Please stay tuned and observe my project under the link: [Selenium From Scratch](https://github.com/AdamSajewicz/SeleniumFromScratch).
There will be a major changes soon.
