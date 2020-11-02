---
layout: post
title:  "Querying data in AppMaps"
author: Alan Potter
permalink: /code-gallery/:title/
category: gallery
featured: true
thumb: /code-gallery/assets/img/appmap-query.png
image: /code-gallery/assets/img/appmap-query.png
excerpt_separator: <!--more-->
---

The AppMap framework includes JavaScript code which creates data structures that extract
and simplify AppMap data.

<!--more-->

This example shows how to create a representation of the code flow in an AppMap, use it to
create nodes in a graph database, and query the database to find classes that don't call
methods in other classes.

<script id="asciicast-368789" src="https://asciinema.org/a/368789.js" async></script>

{: .btn.btn-primary}
[Check out the code &raquo;](https://gist.github.com/apotterri/5d4014f47e3dbd4c000ec4920835280a)

## Components used

This examples uses the
[`CallTree`](https://github.com/applandinc/appmap-models/blob/master/src/callTree/callTree.js)
model, which is available in the open source
[appmap-models](https://github.com/applandinc/appmap-models) project.

## Customizations

In this example, a `CallTree` is created for each AppMap file provided on the command
line. The `CallTree` is flattened into an array. Each array element contains information
about a method call: the class that contains the method, and an array of methods called by
that method (child methods).

For each element in the flattened array, a node in a graph database is created for the
containing class. For each element in the array of child methods, an edge is created from the new
node to a node for the class of the child method.

The example requires a [neo4j](https://neo4j.com) instance to be available.

## Data sources

The examples uses AppMap data recorded from the tests for the open source application
[Discourse](https://github.com/discourse/discourse), "A platform for community
discussion". The recordings were created using the
[appmap-ruby](https://github.com/applandinc/appmap-ruby) client. Since the Discourse
application is open source and public on AppLand, the recorded scenario data can be freely
downloaded from scenarios in the application.

To obtain raw scenario data, visit the the [AppLand sandbox](https://app.land/), view the
[public applications](https://app.land/explore), and click on the Discourse application.

From the application page, choose a scenario:

<img style="width: 420px; height: 291px;" src="/code-gallery/assets/img/appmap-query-scenario.png">

Open the properties for the scenario:

<img style="width: 420px; height: 291px;" src="/code-gallery/assets/img/appmap-query-scenario-props.png">

Download the data:

<img style="width: 420px; height: 291px;" src="/code-gallery/assets/img/appmap-query-download.png">

Downloading several sets of data will make the query results more interesting.

## Related work
The scenarios of applications in the [AppLand sandbox](https://app.land) each contain a Timeline view, showing the
call sequence contained in the AppMap data.

[&laquo; Back to the code gallery](/code-gallery)
