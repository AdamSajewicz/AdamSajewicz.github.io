---
title: "Deployment of a simple webapp on localhost - preparation"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Webservices
  - Deployments
  - Tomcat
---

Few days ago I got an idea to show how to automate API tests with Postman. However it sounds pretty obvious and not very complicated, I wanted it to be a more challenging project. I will try to deploy the app on at least two different environments, and use them to parametrize Postman's tests.
<!--more-->
That approach will require a certain preparation. First of all, I need the app itself. Then a webserver on which I could deploy the app. 
One of the environments on which I would like to install the app will be the Localhost. The second instance of the webservices I'd like to have deployed on AWS cloud. So from such 'easy' task as 'Postman automated tests' the idea has grown to almost an Epic.
<!--more-->
As the webapp I have chosen a simple webservice project available under [Basic-restful-webservices link](https://github.com/jgpreetham/basic-restful-webservices).
> The project contains RESTful web services example built using Jersey 2.17, and adheres to Level 3 of Richardson Maturity Model(Fully RESTful API). It includes such features as:
> * GET,POST,PUT,DELETE operations
> * Sub resources GET,PUT,POST,DELETE operations
> * HATEOAS support
> * Covers @PathParam, @Path, @Consumes, @Produces, @BeanParam, @Context, @QueryParam, @CookieParam, @HeaderParam etc
> 

<!--more-->
Having set all the plan, for the first step I've just done two of the most crucial elements of the requirements: 
* successfully built the app sourcecode
* installed and started the Apache Tomcat webserver.

<img src="{{ site.url }}{{ site.baseurl }}/assets/images/tomcat-local-homepage.png" alt="Tomcat running on localhost">

To make the server up and running I followed some guidelines found [here](https://linuxize.com/post/how-to-install-tomcat-10-on-ubuntu-22-04/?utm_content=cmp-true).

<!--more-->
In a next post I will present first test in Postman, calling the webservices against the app running locally.
