---
title: "Finished the first version of Postman collection"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - Webservices
  - RESTful
  - Postman 
---

I have just finished the Postman collection with automated tests of my webservice app. It consists of requests which are performing CRUD operations, however they are automated, with variables, pre-request scripts and of course with test scripts.
<!--more-->
The workflow I'm using there is quite simple:

- Authenticate
- Create
- Get a list of consultants
- Get a single consultant
- Update the consultant
- Remove the consultant

Due to the fact, that I created the collection for presentation purposes, I'm using there a bunch of Postman's features. First of all I created an environment. For now there is only the Localhost one, but I'm going to extend it by a cloud-hosted one. I'm using environment variables to automatically store Authorization token, as well as baseUrl. There are pre-requests scripts and test scripts as well. Apart from that, I'm using ```pm.setNextRequest()``` construct, asynchronous requests via pm API, Lodash functions and more.  
<!--more-->
All this allowed me to produce a pretty nice Collection. You can see and review it in the following Gist:
<script src="https://gist.github.com/AdamSajewicz/1b619f2f38914d01f71ea202bf09e8f2.js"></script>

<!--more-->
Next steps would be just to deploy the app on a cloud platform, maybe the AWS, and then create another Postman's environment. That way I would show other skills, like familiarity with AWS, ability to deploy apps, manage the app on AWS cloud, using Terraform etc.
<!--more-->
To be honest, by completing the Postman collection I have opened an ocean of possibilities. Please stay tuned, because there will be a lot more stuff waiting for publication and for your review.

