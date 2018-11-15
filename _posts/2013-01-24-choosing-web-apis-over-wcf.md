---
id: 72
title: choosing web apis over wcf
date: 2013-01-24T23:43:37+00:00
author: Hasan Ali Karaca
layout: post
guid: http://hasanalikaraca.com/?p=72
permalink: /2013/01/choosing-web-apis-over-wcf/
sfw_pwd:
  - LG5jOVJ1q77Z
categories:
  - Uncategorized
layout: post
---

{{ page.title }}
================

>   * If your intention is to create services that support special scenarios – one way messaging, message queues, duplex communication etc, then you’re better of picking WCF
>   * If you want to create services that can use fast transport channels when available, such as TCP, Named Pipes, or maybe even UDP (in WCF 4.5), and you also want to support HTTP when all other transports are unavailable, then you’re better off with WCF and using both SOAP-based bindings and the WebHttp binding.
>   * If you want to create resource-oriented services over HTTP that can use the full features of HTTP – define cache control for browsers, versioning and concurrency using ETags, pass various content types such as images, documents, HTML pages etc., use URI templates to include Task URIs in your responses, then the new Web APIs are the best choice for you.
>   * If you want to create a multi-target service that can be used as both resource-oriented service over HTTP and as RPC-style SOAP service over TCP – talk to me first, so I’ll give you some pointers.

<a href="http://www.codeproject.com/Articles/341414/WCF-or-ASP-NET-Web-APIs-My-two-cents-on-the-subjec" target="_blank">source</a>
 