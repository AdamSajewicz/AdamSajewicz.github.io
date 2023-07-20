---
title: "Another simple way to handle REST-Api tests without any test framework"
excerpt_separator: "<!--more-->"
categories:
  - Blog
tags:
  - REST Api
  - Java
  - HttpRequest
---

Today I wanted to implement yet another test within my REST-Assured framework, covering the "create a new booking" scenario.
That would be quite easy, having in mind that the framework I've already had is good enough to cover even more complex scenarios.
So I decided just the other way.
<!--more-->
Being a QA Automation Engineer is not always an easy job. Sometimes that person has to cope with more difficult tasks, 
a solution to which usually require learning a new techniques, and inventing something new. So that was my today's idea as well.
I am going to show how to handle a situation, where a QA has to write an automated test verifying a REST Api. But this time 
it will be a custom solution to this problem, not using any specific test framework.
<!--more-->
To do so, I decided to use the <code>java.net.http.*</code> libraries. 
In general, there are many other approaches to achieve the same goal as well, like <code>org.apache.httpcomponents</code>. 
This time however let's stick to the java.net solution, since it's a java's bundled one library, and one of the most basics.
The Apache's solution is more robust lib, and it's worth to be a matter of another separate article, the more that I have been working 
actively with it in one of my previous jobs.
<!--more-->
To start with, I've already prepared a simple repo with the complete solution. Here is the link:
[Simple REST Api Framework](https://github.com/AdamSajewicz/SimpleRestApiTestFramework). The problem I am going to address 
there is to create a simple tests which is checking the API for creating a new booking, 
which is described there: [Restful-booker CreateBooking](https://restful-booker.herokuapp.com/apidoc/index.html#api-Booking-CreateBooking).
<!--more-->
In order to do so, I am using the <code>java.net.http</code> components, together with <code>com.google.gson</code> library, 
used to transform a simple POJO classes into Json payload, and vice-versa. The idea was to create a POJO Booking object I wanted to create,
transform it into a Json payload, call the webservice, get a HttpResponse and transform it back to a Booking object in order to
assert some values on the created Booking.
<!--more-->
So, first of all I created a POJO Booking object:

<script src="https://gist.github.com/AdamSajewicz/4e89163fd4e5f701b4f6efda153a36c7.js"></script>

And of course, a BookingDates object as well:

<script src="https://gist.github.com/AdamSajewicz/ed4c992f66e18eb55fdd927f136c3f39.js"></script>

These objects are models on which the Gson library will generate a JSON payload needed for the webservice call.
So converting the model into the JSON is super-simple:

<script src="https://gist.github.com/AdamSajewicz/e2b9670c3b2436d6303b8a1106bbe7cb.js"></script>

The bookingObject there has just been created with the Builder pattern, according to the Booking POJO.
<!--more-->
The next step is to create an HTTP request (so define the URI, the headers e.t.c), and the HTTP client itself. I've done this by:

<script src="https://gist.github.com/AdamSajewicz/8bb47a36dd309cae673975d707cb12bd.js"></script>

Having this all in place, it's time to send the request. This is done by calling:

<code>HttpResponse<String> httpResponse = httpClient.send(httpRequest, HttpResponse.BodyHandlers.ofString());</code>

In this call, the HttpResponse<String> and the corresponding HttpResponse.BodyHandlers.ofString() simply means 
that we're expecting a response to be a String.

So far so good. Now I have a Response object. To check the response status code the command <code>httpResponse.statusCode()</code>
can be used. The response's body is of course in the JSON format (according to the specified Content-Type header above). 
So to convert the JSON back to the Booking Object, the Gson is useful again:

<code>BookingResponseObj bookingResponse = gson.fromJson(httpResponse.body(), BookingResponseObj.class);</code>
<!--more-->
Depending on the project's needs, any further assertions, or processing can be done using either the original JSON response's body,
OR the Booking POJO object. In terms of JSON, another library can be used in assertions: JsonPath, but this is also a good topic for 
yet another separate article.

<!--more-->
To wrap things up: in this article I showed that in simple cases there is no need to have any specialized test framework,
to write automated REST Api tests. In Java there is bundled a nice support for Http-calls, and there are libraries to easily
convert POJO classes to JSON back and forth. 

In further articles I will also focus on the following topics:

- Assertions (different types, main providers)
- JsonPath
- Another library for handling the HTTP requests: <code>org.apache.commons.httpclient</code>, which is sometimes claimed to be the best one in such situations.
