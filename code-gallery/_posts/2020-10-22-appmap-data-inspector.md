---
layout: post
title:  "AppMap data inspector"
author: Dustin Byrne
permalink: /code-gallery/:title/
category: gallery
featured: true
thumb: /code-gallery/assets/img/appmap-data-inspector-thumb.jpg
image: /code-gallery/assets/img/appmap-data-inspector.png
excerpt_separator: <!--more-->

---

This proof of concept analyzes data snapshots captured in an appmap file. It
surfaces useful insights about how the data is used, where it’s stored and what
it may contain. In short, it shows you how you’re handling various kinds of data
within your application.

<!--more-->

This project attempts to identify the following:
- Sensitive values such as passwords and auth tokens
- Encrypted values such as password hashes
- Unencrypted values which should ideally be encrypted
- Data persisted within a database
- Data provided by a user, such as an HTTP request parameter
- Personally identifiable information such as social security numbers or email addresses
- Data logged to `stdout`

A single data object can have many of these identifiable “traits”. In fact, the
most useful insights come from a combination of traits. For example, personally
identifiable information appearing in application logs or sensitive data that
persists in a database unencrypted. Try it out with your own data!

{: .btn.btn-primary}
[Check out the live demo &raquo;](https://appmap-data-inspector.netlify.app/?url=https%3A%2F%2Fapp.land%2Fapi%2Fscenarios%2Ffbc57147-b947-4423-bd60-ef0d3369726d)

## Components used
This example uses appmap data captured from a live application via an AppMap
recording client. Clients are available both for [Ruby](https://github.com/applandinc/appmap-ruby)
and [Java](https://github.com/applandinc/appmap-java).

## Customizations
Data snapshot analysis performed in this demo is an experimental proof of
concept. It aggregates AppMap data from HTTP requests, SQL queries and function
call parameters to identify various traits detailed above.

## Data sources
The example uses AppMap data recorded from [Discourse](https://github.com/discourse/discourse),
an open source discussion platform written in Ruby. The data used in this
example was recorded from a Discourse test case using the [appmap-ruby](https://github.com/applandinc/appmap-ruby/)
client, and uploaded to the [AppLand sandbox](https://app.land). Because the
Discourse application is open source and public on AppLand, the recorded
scenario data is freely downloadable.

To obtain the download URL for any scenario, click Properties and then find the
Raw data link:

<img style="width: 420px; height: 291px;" src="/code-gallery/assets/img/raw-data-link.png">


## Related work
The AppLand sandbox hosts a number of AppMap recordings across many different
applications. Each individual recording, or “scenario”, has a visual
representation depicting both logic and data flow. Check out the example
Discourse data used in the demo on [AppLand](https://app.land/scenarios/fbc57147-b947-4423-bd60-ef0d3369726d#event=7).


[&laquo; Back to the code gallery](/code-gallery)
