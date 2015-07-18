---
title: HTTP Query String Parameters
layout: post
summary: A basic overview of HTTP Query String Parameters.
tags: HTTP, REST, BLACK BOX
---

## Understanding Parameters

### Introduction

While this discussion will focus primarily on defining what parameters are, how they're generated and passed from the _client_ to the _server_, I'll also attempt to cover, in brief, some of the related or ancillary topics as well.  I encourage those that are interested in learning more about the underlying processes to visit the links embedded throughout this post.  Most of them point to either [Wikipedia](http://en.wikipedia.org/wiki/Internet_protocol_suite) or to documentation provided by the various standards bodies like the [Web Consortium](http://www.w3.org).  They likely give a more nuanced introduction to these topics and also have plenty of additional information and resources available to peruse.

In addition, I feel that it's important to distinguish between what parameters are, _independently_ of how they are used once received by the _server_.  While most [web frameworks](http://en.wikipedia.org/wiki/Web_framework) or [domain-specific languages](http://en.wikipedia.org/wiki/Domain-specific_language), `DSL`s, will [parse](http://en.wikipedia.org/wiki/Parsing) the incoming string of characters in conceptually similar ways, there will undoubted be some discrepancies in how the resulting data is formatted and made available for use by the developer.

So, while some examples have been included that are specific to _Rails_ and _Sinatra_, in general, this post will strive to discuss parameters outside of any one specific implementation.

===

### What are Parameters?  What purpose do they serve?

It's important to understand that, conceptually, _parameters_ are a tool.  They provide developers with a way of enabling end users to interact with a given website, be it a service or application, in a more dynamic way. That interaction might take the form of requesting specific information _of_, or passing data to be used and stored _by_ the website in question.

As such, each developer decides, based on the type of service or application they are building, what the parameters are.  They decide what information will be requested from the user and how that information will be used by their specific service or application.  A simple search query is one example, posting a message to a blog is another.

The term _parameter_ refers to the pieces of associated data, `name | value` pairs, that originate on the _client_, and are passed to the _server_. Once generated, there are two ways that parameters are transmitted from _client_ to _server_, either within the [_query string_](http://en.wikipedia.org/wiki/Query_string) of a [`URI` / `URL`](http://en.wikipedia.org/wiki/Uniform_resource_identifier) through an `HTTP` `GET` request, or as part of the body of an `HTTP` [`POST` request](http://en.wikipedia.org/wiki/HTTP_POST).

===

### How are they generated?

The definition above likely raises some additional questions.

* How are parameters actually created?
* What is meant by _associated data_?
* What does a parameter look like in practice?

Since parameters are data and often represent information that the developer needs the user of her website or service to provide, they are typically created using an [`HTML` form](http://www.w3schools.com/html/html_forms.asp).  Every `HTML` form contains _fields_, places for users to enter data, and typically those _fields_ are explicitly _named_.  The relationship between the `name` of the field and its contents, the `value` of the data entered, represents the association mentioned above.

For example, this is what the `HTML` code for a basic form might look like.  It's here, within the `input` _attribute_ that the `name` of each field is set.

![HTML-Form-Code](http://cl.ly/image/000o2C0C1o1w/Params_HTML_Form.jpg "Basic-HTML-Form")

**Please Note**

It's important to distinguish between the _label_ given to a form field and the `name` _attribute_.  The _label_ is a more general, superficial term and does not effect the relationship between the `name` and the `value` of the parameter being generated.

That said, the resulting form would look like this.

![Form-Example](http://cl.ly/image/2W1e3n2V1I3c/Params_Basic_Form.jpg "Basic-Form")

When this form is submitted, each corresponding `name | value` pair will be passed from the _client_ to the _server_.

Each of these associated pieces of data, each `name | value` pair, is a _parameter_.

How they are sent and what they look like once received by the _server_, is, in part, covered below.

===

### How are they sent? `HTTP` and the _Request_ / _Response_ Cycle

#### _Request_ / _Response_

The [Hypertext Transfer Protocol](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol), `HTTP`, defines, at a high level, how a _client_ and _server_ communicate over a network.  While there are other protocols that help facilitate this communication, such as [TCP/IP](http://en.wikipedia.org/wiki/Internet_protocol_suite), for our purpose, we'll limit the discussion to the messages passed via `HTTP` through a process called [_request_ / _response_](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Technical_overview).

The _request_ / _response_ cycle begins with the _client_ sending a [request message](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_message) to the _server_, and then waiting for the _server_ to [respond](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Response_message) with a message of its own.  Typically, the _client_ is requesting a resource of some kind, a web page or the results of a search query.  The _server_ will then respond, delivering the various resources that were requested.  The links above provide examples of what these messages look like and how the data is encoded, transmitted, and decoded at each end.

While all the information contained within each message serves an important function, the two most relevant for this discussion are the [request method](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods) and the Uniform Resource Locator or [`URI` / `URL`](http://en.wikipedia.org/wiki/Uniform_Resource_Identifier).  These two pieces of information define the nature of the request and the resource that is being interacted with.  When used in conjunction with `HTTP`, the `URI` / `URL` is often referred to as the web address.

**Please Note**

While outside the scope of this post, it's important to recognize that `URI`s provide a standardized way for different parts of a computing device to identify one another, thus enabling them to pass messages back and forth.  For more information on all the different types of `URI`s, check out [this link](http://en.wikipedia.org/wiki/URI_scheme#Official_IANA-registered_schemes).

#### Uniform Resource Locator, `URL`

The `URL` is the means by which users interact with a website.  They determine how resources are requested and specific behavior triggered.

But what is a resource?

Often it's a static file or web page.  That's probably the most common interpretation.  But resources are actually any addressable thing or bit of data, including the result of a search or the return value of a function.  The `URL` is the destination, the server endpoint, which, when used in conjunction with a block of code, enable the functionality of most of the web services and applications in use today.  So it's important to understand, or at least be aware, of what the individual parts of a `URL` represent in addition to how they work.

To begin with, `URL`s all share the same basic structure, which is determined by the type of resource they point to.

```
<scheme name> : <host or domain> / <hierarchical part> [ ? <query> ] [ # <fragment> ]
```

* The _scheme name_ is often a protocol, the communication method, such as, `http`, `ftp`, `ssh`, `mailto`, or `irc`.
* The _domain name_ or host is the address of the server where the individual resources reside.  Such as google.com, twitter.com, or en.wikipedia.org
* The _hierarchal part_ is appended to the host and resembles the file path often found in a Unix based OS. __/file/lives/here__
* The _query string_ follows the hierarchal part and always begins with a **"?"**.  The data following it is grouped by an **"="** and the `name` | `value` pairs are separated by an **"&"**.
* The _fragment_ follows the hierarchal part and always begins with a **"#"**.  It points to a specific location, often a section heading within a static file.

A `URL` formatted in conjunction with `HTTP` will include the first three components above and, possibly, a _query string_ or _fragment_.  Here's an example of a web address that includes a _query string_.

```
http://superwall.com/register?name=travis&city=San+Francisco&state=California
```

#### `HTTP` Methods

There are a number of different request methods defined within `HTTP` that govern how information is passed during the _request_ / _response_ cycle...how messages, and the data they contain, are passed.  These methods are often referred to as _verbs_ since their names typically correspond to the action they preform.  Two of the most common `HTTP` methods are `GET` and `POST`.

As its name implies, the `GET` method is used to request a specific [resource](http://www.w3.org/1999/05/WCA-terms/#PRIMITIVE). Any data associated with a `GET` request is represented in the `URL`.  Typically within the _hierarchal part_ or _path_.  When a user makes a specific request, a search for example, the information is [encoded](http://en.wikipedia.org/wiki/Percent-encoding) within the _query string_.

The messages sent via the `GET` method are intended to read, __not__ create, update, or destroy, the target resource. As such, a `GET` request cannot be used to alter or modify existing data on a _server_.  This makes it the most common type of request used on the web since most activity involves asking for and receiving a specific resource, often an individual webpage.

The [`POST` method](http://en.wikipedia.org/wiki/POST_(HTTP)), on the other hand, is used to create and, in conjunction with [`PUT` and `DELETE`]((http://en.wikipedia.org/wiki/RESTful#Applied_to_web_services)), modify or destroy existing data.  While not as common as the `GET` method, `POST` is the primary way developers enable users to interact with, and persist or store data using, web applications and services.


### Passing Parameters - the `HTTP` `GET` Method

Since we've already established what parameters are, associated pieces of data that originate on the _client_ and passed to the _server_, it's time to discuss how they get passed.  There are two common ways to transmit data from the _client_ to the _server_, an `HTTP` `GET` request and and `HTTP` `POST` request.

When passing data in conjunction with an `HTTP` `GET` request, the [_query string_](http://en.wikipedia.org/wiki/Query_string) portion of the `URL` is used as the mode of transport between _client_ and _server_.  As mentioned above, the _query string_ always begins with a __"?"__, followed by the `name | value` pairs of data.

Here's that example `URL` again.

```
http://superwall.com/register?name=travis&city=San+Francisco&state=California
```

The parameters being sent in this case are the three `name | value` pairs following the question mark, separated by an ampersand.

Itâ€™s worth mentioning again that _how_ this string of information is [parsed](http://en.wikipedia.org/wiki/Parsing) and formatted once received by the _server_, will differ based on the framework that was used when building the web application.

In a Ruby based web framework like _Rails_ or a _DSL_ like _Sinatra_, these `name | value` pairs are the same as `key | value` pairs, a `Hash`, and are often referred to as the `params hash`.

So the resulting `Hash` from the `URL` above might look like this.


```ruby
{"name"=>"travis"}, {"city"=>"san francisco"}, {"state"=>"california"}
```
**Please Note**

While outside the scope of this post, it's important to recognize and be aware that since the primary message associated with a `GET` request is the `URL` itself, data sent in this manner is visible during the transport process.  As such, it's generally best to avoid sending anything that might be considered sensitive via a `GET` request and instead use a `POST` request.

===

### Passing Parameters - the `HTTP` `POST` Method

Passing parameters via the `HTTP` `POST` method is similar to the `HTTP` `GET` method described above.  Instead of the data being passed to the _server_ as part of the `URL`, though, it's passed within the body of the `HTTP` request using `POST` and, of course, an `HTML` form.

Understanding the difference, the implications of how the information is passed, is important. As touched upon in the `HTTP` section above, there are inherent limitations on how request methods can be used.  The [`POST` method](http://en.wikipedia.org/wiki/RESTful#Applied_to_web_services) is for creating or adding new information to a website, service, or application.  It also enables, through the use of the `PUT` and `DELETE` methods, data to be updated or destroyed.

The developer decides what information will be added, the `name | value` pairs, when she creates the form.  Here again is the `HTML` code for a basic `POST` request.

![HTML-POST-Code](http://cl.ly/image/0y0t43400N1q/Params_HTML_POST.jpg "HTML-POST")

Here's what the resulting form would look like.

![Form-Example-Params](http://cl.ly/image/0L153n1G1z1W/Form_Params_Example.jpg "Form-Params")

The body of a `POST` request will look slightly different depending on the information being entered into the `HTML` form and, again, how that information is being used as defined within the application running on the _server_.

In the case of _Rails_ or _Sinatra_, the `name` of the various fields will correspond to the `key`. So "title", "description", and "created_by" are all `keys`.  The data entered into the form fields, "Wall of Super", "Here I describe super things.", and "Travis" are the `values`.

The resulting `key | value` pairs, the `params Hash`, might look like this when received by the server.

```ruby
{"wall"=>{"title"=>"Wall of Super", "description"=>"Here I describe super things.", "created_by"=>"Travis"}}
```

In this example, there are actually two hashes.  The first hash has a `key` of "wall", the `value` is the second `Hash` we just described.  Once submitted, this form would likely create a new "wall" record within the database, containing the data that corresponds to the various `key | value` pairs.

**Please Note**

As this example demonstrates, the data passed from _client_ to _server_ can become quite complex in nature.  One of the benefits of using the `HTTP` `POST` method is that the data being transmitted is carried within the body of the request.  This gives developers the freedom, or option at least, to obfuscate or hide what's being passed between _client_ and _server_.

===

### How are they used?  A Basic Example.

While largely outside the scope of this post, I wanted to provide a basic example of how parameters are often used.

Think for a moment about the Tweets you make or all the updates you post to your Facebook Timeline.  All the information you enter, through a web browser, a desktop or mobile app, must be passed on to appropriate server.  So the information leaves you and your _client_, transmitted via a form using an `HTTP` `POST` request, and ends up being received by a _server_ running proprietary software designed by the nice folks at Twitter or Facebook.

Once it arrives, all the data is parsed and formatted as a series of `key | value` pairs that are then acted upon in a way defined by the developers at Twitter or FB. They undoubtedly use the information in a myriad of ways but eventually it's inserted or added to a database and the results then displayed, in perpetuity. for all the world to see.

Or at least for your 4 followers and friends.

===

### Summary

What parameters are, (formatted data originating on the _client_), how they are generated and passed on to the _server_, (typically via an `HTML` form in conjunction with an `HTTP` method), is key to understanding their importance and the foundational role they play within a website, service, or application.   The examples above attempt to demonstrate that role and hint at what they make possible.

The implementation details, how parameters are used once they are received, parsed, and made available to the developer, is almost completely dependent on the web framework or DSL being used to create the website, service or application.  Put simply, how parameters are used within _Sinatra_ will be different than how they are used within _Django_. Which is why such discussions are best left for a later post.
